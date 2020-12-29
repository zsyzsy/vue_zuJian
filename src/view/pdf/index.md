# pdf预览

## 将pdf文件放在最外成的文件夹内
```html
  <div v-for="page in numPages" :key="page" style="display: block;width: 100%;">
          <img :id="'item_'+page" class="pdf-item" src="">
        </div>
    </div>
```
```css
<style lang="scss" scoped>
    .seamless-warp {
        height: 229px;
        overflow: hidden;
    }
</style>
```
```javascript
<script>
import PDFJS from "../../../public/static/pdfjs/build/pdf";
PDFJS.GlobalWorkerOptions.workerSrc =
  process.env.NODE_ENV === "production"
    ? "../static/pdfjs/build/pdf.worker.js"
    : "/static/pdfjs/build/pdf.worker.js";
const CMAP_URL =
  process.env.NODE_ENV === "production"
    ? "../static/pdfjs/web/cmaps/"
    : "/static/pdfjs/web/cmaps/";
export default {
  data () {
    return {
      // md: demo,
      scale: 0.5,
      numPages: 0
    }
  },
  mounted () {
    const files = `JVBERi0xLjQKJeLjz9MKMyA...`
    this.loadPdf(files)
  },
  methods: {
    // 预览pdf
    loadPdf (file) {
      // const file = this.dta()
      PDFJS.getDocument({
        data: window.atob(file),
        cMapUrl: CMAP_URL,
        cMapPacked: true
      }).promise.then((pdf) => {
        this.pdfDoc = pdf
        this.numPages = this.pdfDoc.numPages
        this.$nextTick(() => {
          this.renderPage(1)
        })
      })
    },
    // pdf页数
    renderPage (num) {
      const _this = this
      const contractId = this.contractId
      this.pdfDoc.getPage(num).then(function (page) {
        // let canvas = document.getElementById('the-canvas' + num)
        const canvas = document.createElement('canvas')
        const ctx = canvas.getContext('2d')
        const dpr = window.devicePixelRatio || 1
        const bsr =
          ctx.webkitBackingStorePixelRatio ||
          ctx.mozBackingStorePixelRatio ||
          ctx.msBackingStorePixelRatio ||
          ctx.oBackingStorePixelRatio ||
          ctx.backingStorePixelRatio ||
          1
        const ratio = dpr / bsr
        // var viewport = page.getViewport({scale: canvas.parentElement.offsetWidth / page.getViewport({scale: 1}).width})
        var viewport = page.getViewport({ scale: ratio })
        canvas.width = viewport.width * 1
        canvas.height = viewport.height * 1
        canvas.style.width = viewport.width + 'px'
        canvas.style.height = viewport.height + 'px'
        // ctx.setTransform(ratio, 0, 0, ratio, 0, 0)
        // console.log(viewport, ctx)
        var renderContext = {
          canvasContext: ctx,
          viewport: viewport
        }
        page.render(renderContext).promise.then((data) => {
          const img = document.getElementById(contractId + num)
          // console.log(canvas.toDataURL(), '===')
          // const srcData = canvas.toDataURL('image/jpeg')
          img.src = canvas.toDataURL()
        })
        if (_this.numPages > num) {
          _this.renderPage(num + 1)
        }
      })
    }
  }
}
</script>
```