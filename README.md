\# Framer JS



\[toc\]



\#\# Project

\`\`\`

 \# 文件分享时显示信息

 Framer.Info =

 title: ""

 author: "lyujie"

 twitter: ""

 description: ""

 \# Import file "Sketch"

 sketch = Framer.Importer.load\("imported/Sketch@1x"\)

 \# 设定全局图层引用，可省略每次引用时的前缀

 Utils.globalLayers\(sketch\)

\`\`\`

---

\#\#

 Base

\#\#\#

 Vairable

\`\`\`

 \# 设置色彩变量

 colorA = '\#ffffff'

 \# 设置背景色并引用变量

 backgroundA = new BackgroundLayer

 backgroundColor: colorA

\`\`\`

\#\#\#

 Layer

\`\`\`

 \# Create a layer

 layerA = new Layer

 x: 0, y: 0, width: 100, height: 100

 \# Layer name

 layerA = new Layer

 layerA.name = "button"

\`\`\`

\#\#\#

 属性

\`\`\`

 \# 方法1

 layerB = new Layer

 backgroundColor: "\#2dd7aa",

 width: 60, height: 60,

 scale: 1, borderRadius: 3

 \# 方法2

 layerB.borderRadius = 3

 layerB.rotation = 45

 layerB.originX = 0

 layerB.originY = 1

 layerB.orginZ = 1

 layer.perspective = 100

 layerB.opacity = 0.8

 layerB.scale = 0.8

 layerB.visible = false

 layerB.clip = true

 layerB.ignoreEvents = true

\`\`\`

\#\#\#

 3D

\`\`\`

 \# Enable flat on its children

 layerA = new Layer

 width: 200

 height: 200

 x: 100

 y: 100

 clip: false

 flat: true

 \# Rotate horizontally

 layerA.rotationX = 45

 \# With flat enabled, adjusting z has no effect

 layerB = new Layer

 parent: layerA

 z: 25

\`\`\`

\#\#\#

 位置

\`\`\`

 \# Properties of layerA

 \# x:40, y:40, width:80

 layerB.x = layerA.x \# 40

 layerB.x = layerA.minX \# 40

 layerB.x = layerA.maxX \# 120

 \# The x value of the center

 layerB.x = layerA.midX \# 80

 \# The y value of the center

 layerB.y = layerA.midY \# 80

 \# Center

 layerA.center\(\)

 \# Center horizontally

 layerA.centerX\(\)

 \# Center vertically

 layerA.centerY\(\)

\`\`\`

\#\#\#

 层级

\`\`\`

 \# 方法1

 layerA = new Layer

 layerB = new Layer

 parent:layerA

 \# 方法2

 layerB.superLayer = layerA

 layerA.addSubLayer\(layerB\)

 layerA.addChild\(layerB\)

 layerA.removeChild\(layerB\)

 \# index

 layerA.index = 2

 layerB.index = 1

\`\`\`

\#\#\#

 图层类型

\`\`\`

 layerA = new Layer

 images : "image/pic.png"

 layerB = new Layer

 video :"video.mp4"

 layerC = new Layer

 layerC.html = "hello"

 \# hosted image

 layerA.image = "https://framerjs.com/logo.png"

\`\`\`

---

\#\#

 状态

\#\#\#

 添加状态

\`\`\`

 \# The default state

 layerA = new Layer

 opacity : 1

 \# A new state titled "fade"

 layerA.states.add

 fade:

 opacity: 0

 \# 待动画过渡的状态转变

 layerA.states.switch\("fade"\)

 \# Switch states without animation

 layerA.states.switchInstant\("fade"\)

 \# 示例

 \# Add states

 layerA.states.add

 second:

 scale: 0.75

 third:

 rotation: 90

 scale: 1

 \# Toggle states on tap

 layerA.onTap -

&gt;

 layerA.states.next\(\)

\`\`\`

\#\#\#

 编辑状态

\`\`\`

 \# Remove second state

 layerA.states.remove\("second"\)

 \# Override third states

 layerA.states.add

 third:

 blur: 10

\`\`\`

\#\#\#

 动画状态切换

\`\`\`

 \# 通过动画过渡变换到状态stateA

 layerA.animate\("stateA"\)

 \# 直接变换到stateA，不带动画效果

 layerA.stateSwitch\("stateA"\)

 \# 在stateA和stateB之间互相转换

 layerA.stateCycle\("stateA", "stateB"\)

\`\`\`

\#\#

 Other

\#\#\#

 for in 循环

\`\`\`

 layer = \[\]

 layerColors = \["\#333", "\#666", "\#999"\]

 for i in \[0..3\]

 layer\[i\] = new Layer

 x: 0

 y: 0

 backgroundColor: layerColors\[i\]

\`\`\`

\#\#\#

 Utils

\`

Utils.modulate\(\)

\`

 是Framer提供的范围转换函数

\`\`\`

 \# 当scroll纵向移动的距离scrollY在0到500范围内等比例转换到0到1内，true表示超出部分使用边界值

 layer.opacity = Utils.modulate\(scroll.scrollY, \[0, 500\], \[0,1\], true\)

 \# Output: 0.6

 \# 随着滑动时改变位置

 layer.y = Utils.modulate\(scroll.scrollY, \[0,500\], \[150,80\], true\)

 \# 当滚动到顶部时，显示内容，否则不显示

 if\(scroll.scrollY

&gt;

500\)

 layer.html = "title"

 else layer.html = ""

\`\`\`

\#\#\#

 SVG

\`\`\`

 \# 放在文件头部

 {SVGLayer} = require "SVGLayer"

 layer = new SVGLayer

 width: 24

 height: 24

 x: 0, y: 0

 strokeLinecap: "round"

 strokeWidth: 2

 fill: "white"

 direction: "backward"

 stroke: "black"

 dashOffset: 0

 parent: like

 path: '

&lt;

path d="M11.7500177,5.43145751 C13.9078864,1.28932188 18.2236238,1.28932188 20.3814924,3.36038969 C22.5395025,5.43145751 22.5395025,9.57359313 20.3814924,13.7157288 C18.8709985,16.8223305 14.9868914,19.9289322 11.7500177,22 C8.51314394,19.9289322 4.62889547,16.8223305 3.11840152,13.7157288 C0.960532827,9.57359313 0.960532827,5.43145751 3.11840152,3.36038969 C5.27627021,1.28932188 9.59214898,1.28932188 11.7500177,5.43145751 Z"

&gt;

&lt;

/path

&gt;

'

\`\`\`

\#\#\#

 FlowComponent



\`\`\`

 layerA = new Layer

 layerB = new Layer

 \# 设定初始屏

 flow = new flowComponent

 flow.showNext\(layerA\)

 \# 监听事件

 layerA.onClick -

&gt;

 flow.showNext\(layerB\)

 \# 返回上一屏幕

 layerB.onClick -

&gt;

 flow.previous\(\)

 \# 切换方式

 flow.showNext\(\)

 flow.showOverlayTop\(\)

 flow.showOverlayRight\(\)

 flow.showOverlayBottom\(\)

 flow.showOverlayLeft\(\)

 \# 固定顶部

 flow.header\(layer\)

 \# 固定底部

 flow.footer\(layer\)

\`\`\`

