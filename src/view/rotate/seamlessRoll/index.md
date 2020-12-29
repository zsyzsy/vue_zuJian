|  参数   | 描述  | 默认值  | 类型  |
|  ----  | ----  | ----  | ----  |
| step  | 数值越大速度滚动越快	 | 1	 | Number	 |
| limitMoveNum  | 开启无缝滚动的数据量 | 	5 | Number	 |
| hoverStop  | 是否启用鼠标hover控制 | 	true | Boolean	 |
|  direction | 方向 0 往下 1 往上 2向左 3向右	 | 1	 | Number	 |
| openTouch  | 移动端开启touch滑动	 | true	 | 	Boolean |
| singleHeight  | 单步运动停止的高度(默认值0是无缝不停止的滚动) direction => 0/1	 |    0	 | 	Number |
|  singleWidth | 	单步运动停止的宽度(默认值0是无缝不停止的滚动) direction => 2/3 | 	0    | Number	 |
|  waitTime | 单步停止等待时间(默认值1000ms)	 | 1000	 | 	Number |
| switchOffset  | 左右切换按钮距离左右边界的边距(px)		 | 	30 | Number	 |
|  autoPlay | 是否自动播放使用switch切换时候需要置为false		 | true	 | Boolean	 |
|  switchSingleStep | 手动单步切换step值(px)		 | 134	 | Number	 |
| switchDelay  | 	单步切换的动画时间(ms) | 400	 | Number	 |
| switchDisabledClass  | 不可以点击状态的switch按钮父元素的类名		 | disabled	 | String	 |
|  isSingleRemUnit | 	singleHeight and singleWidth是否开启rem度量	 | false	 | Boolean	 |