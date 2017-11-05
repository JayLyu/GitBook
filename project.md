## 基础



### Vairable 变量

设置色彩变量

```js
 colorA = '#ffffff'
```

设置背景色并引用变量

```js
 backgroundA = new BackgroundLayer
 backgroundColor: colorA
```



### Layer 图层

Create a layer

```js
layerA = new Layer
    x: 0, y: 0, width: 100, height: 100
```



Layer name

```js
layerA = new Layer

layerA.name = "button"
```



### 属性

方法1

```js
 layerB = new Layer
 backgroundColor: "#2dd7aa",
 width: 60, height: 60,
 scale: 1, borderRadius: 3
```

方法2

```js
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
```

### 

### 3D

Enable flat on its children

```js
layerA = new Layer

    width: 200

    height: 200

    x: 100

    y: 100

    clip: false

    flat: true
```

Rotate horizontally

```js
 layerA.rotationX = 45
```

With flat enabled, adjusting z has no effect

```js
layerB = new Layer
    parent: layerA
    z: 25
```



### 位置

```js
# Properties of layerA
# x:40, y:40, width:80

layerB.x = layerA.x # 40
layerB.x = layerA.minX # 40
layerB.x = layerA.maxX # 120

# The x value of the center
layerB.x = layerA.midX # 80

# The y value of the center
layerB.y = layerA.midY # 80

# Center
layerA.center()

# Center horizontally
layerA.centerX()

# Center vertically
layerA.centerY()
```



### 层级

```js
# 方法1
layerA = new Layer
layerB = new Layer
parent:layerA

# 方法2
layerB.superLayer = layerA
layerA.addSubLayer(layerB)
layerA.addChild(layerB)
layerA.removeChild(layerB)

# index
layerA.index = 2
layerB.index = 1
```

### 

### 图层类型

```js
layerA = new Layer
images : "image/pic.png"
layerB = new Layer
video :"video.mp4"
layerC = new Layer
layerC.html = "hello"
 
# hosted image
layerA.image = "https://framerjs.com/logo.png"
```



