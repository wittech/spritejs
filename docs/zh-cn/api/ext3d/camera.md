<style>
  sub > em {
    font-size: 12px;
    margin-right: 10px;
  }

  h5 {
    padding-top: 10px;
    border-top: dashed 1px #ddd;
  }
</style>

## Camera <sub>_extends_</sub> [Group3d](zh-cn/api/ext3d/group3d)

Camera是相机类，支持透视和正交两种投影模式。

### constructor(gl, attrs)

构造函数

### Attributes

| 属性名 | 继承 | 属性类型 | 默认值 | 说明 |
| --- | --- | --- | --- | --- |
| near | | number | 0.1 | 近景视野 |
| far | | number | 100 | 远景视野 |
| fov | | number | 45 | 视野角度 |
| aspect | | number | 1 | 宽高比 |
| top | | number | undefined | 正交相机视锥顶面位置 |
| right | | number | undefined | 正交相机视锥右面位置 |
| bottom | | number | undefined | 正交相机视锥底面位置 |
| left | | number | undefined | 正交相机视锥左面位置 |
| mode | | enum{perspective,orthographic} | perspective | 正交相机或透视相机 |
| x | Node3d | number | 0 | 元素 X 轴坐标 |
| y | Node3d | number | 0 | 元素 Y 轴坐标 |
| z | Node3d | number | 0 | 元素 Z 轴坐标 |
| pos | Node3d | Array | [0, 0, 0] | [x, y, z] 简写 |
| rotateX | Node3d | number | 0 | 绕 X 轴旋转 |
| rotateY | Node3d | number | 0 | 绕 Y 轴旋转 |
| rotateZ | Node3d | number | 0 | 绕 Z 轴旋转 |
| rotate | Node3d | Array | [0, 0, 0] | [rotateX, rotateY, rotateZ] 简写 |
| scaleX | Node3d | number | 1 | 绕 X 轴旋转 |
| scaleY | Node3d | number | 1 | 绕 Y 轴旋转 |
| scaleZ | Node3d | number | 1 | 绕 Z 轴旋转 |
| scale | Node3d | Array | [1, 1, 1] | [scaleX, scaleY, scaleZ] 简写 |
| raycast | Node3d | string | undefined | 碰撞检测的模式，默认检测bounds，如果设为sphere则进行球形检测 |
| visibility | Node3d | enum | enum{visible,hidden} | 元素是否可见 |
| id | Node | string | '' | 设定元素的ID |
| name | Node | string | '' | 设定元素的name |
| className | Node | string | '' | 设定元素的className |
| display | Node | string | '' | 设定元素的可见性 |
| pointerEvents | Node | string | visible | 同CSS的pointerEvents |

### Properties

##### _readonly_ projectionMatrix

投影矩阵

##### _readonly_ projectionViewMatrix

相机矩阵与投影矩阵相乘

##### _readonly_ viewMatrix

相机矩阵

##### _readonly_ worldPosition

相机在layer空间的位置

#### _继承自Group3d_

##### _readonly_ childNodes

children的别名

##### _readonly_ children

子元素

##### _readonly_ meshes

当前元素和它的子孙元素的Mesh对象列表。

#### _继承自Node3d_

##### _readonly_ body

当前元素的Mesh或Transform对象。

##### _readonly_ isVisible

元素是否可见。

##### _readonly_ localMatrix

当前元素的变换矩阵。

##### _readonly_ matrix

localMatrix的别名。

##### _readonly_ mesh

当前元素的Mesh对象，如果没有，返回null

##### _readonly_ modelViewMatrix

经过相机换算后的变换矩阵。

##### _readonly_ normalMatrix

法向变换矩阵，一个3X3的矩阵，用来计算光照。

##### _readonly_ renderMatrix

相对于layer的变换矩阵。

##### _readonly_ worldMatrix

renderMatrix的别名。

##### _readonly_ zDepth

元素相对z轴的深度。

#### _继承自Node_

##### _readonly_ ancestors

返回当前元素的祖先元素列表。

##### _readonly_ animations

返回当前元素执行中的所有动画。

##### _readonly_ layer

返回当前绘制上下文中的Layer对象。

##### _readonly_ parent

返回当前对象的父对象。

##### _readonly_ renderer

返回当前绘制上下文中的渲染对象。

##### _readonly_ zOrder

返回当前对象被添加到对象树上的次序。

##### attributes

返回当前元素的属性对象。

##### className

相当于 element.attributes.className

##### id

相当于 element.attributes.id

##### name

相当于 element.attributes.name

##### zIndex

相当于 element.attributes.zIndex

### Methods

##### frustumIntersects(node)

判断是否与元素外框相交

##### frustumIntersectsSphere(center, radius)

判断是否与元素或点以球形半径相交

##### _override_ lookAt([x, y, z])

让相机转向到对应的坐标所在的方向。

##### _override_ onPropertyChange(key, newValue, oldValue)

当元素属性值被改变时，执行的动作。

##### project(v)

将3D坐标投影到2D坐标。

##### unproject(v)

将2D坐标投影到3D坐标。

##### updateFrustum()

更新视锥体。

#### _继承自Group3d_

##### append(...els)

批量添加元素到group中。

##### appendChild(el)

将一个元素添加到group中。

##### cloneNode(deep = false)

Copy一个Group，如果deep为true，则同时复制Group中的子孙元素。

##### getElementById(id)

返回指定id的子元素。

##### getElementsByClassName(className)

返回指定className的子元素列表

##### getElementsByName(name)

返回指定name的子元素列表。

##### getElementsByTagName(name)

返回指定类型的子元素列表。

##### insertBefore(el, ref)

将指定元素插入到ref元素之前，如果ref为null，则将el添加到group末尾，如果ref不为null且不是group的子元素，抛出异常。

##### querySelctor(selector)

根据选择器返回指定的子元素。

##### querySelectorAll(selector)

根据选择器返回所有匹配的子元素列表。

##### replaceChild(el, ref)

将ref元素用新的el元素替代。如果ref元素不在当前group中，则抛出异常。

##### removeAllChildren()

将group的所有子元素移除。

##### removeChild(el)

将指定元素移出group。

##### setResolution({width, height})

设置元素的上下文分辨率。

#### _继承自Node3d_

##### _override_ connect(parent, zOrder)

当元素被添加到对象树上时，该函数被调用，parent和zOrder被赋给元素。

##### _override_ disconnect()

当元素从对象树上移除时，该函数被调用，parent和zOrder属性被移除。

##### setBody(body, update = true) 

设置元素的Mesh对象。

##### traverse(callback) 

遍历当前元素和所有的子孙元素。

##### updateMatrix() 

更新matrix。

##### updateMatrixWorld(force = false)

更新worldMatrix。

#### _继承自Node_

##### activateAnimations() {

激活元素上正在执行的所有动画。

##### addEventListener(type, listener, options = {})

注册事件监听器。

##### animate(frames, timing)

执行动画。

##### attr(...args)

读取或批量设置属性。

##### cloneNode()

Copy整个元素。

##### deactivateAnimations()

停止元素上正在执行的所有动画。

##### dispatchEvent(event)

转发一个自定义事件。

##### dispatchPointerEvent(event)

转发一个鼠标或触屏事件。

##### forceUpdate()

强制重绘画布。

##### getAttribute(key)

读取元素属性值。

##### getListeners(type, {capture = false} = {})

获取事件监听器。

##### getOffsetPosition(x, y)

将相对于Layer的指定[x, y]坐标变换为相对于当前元素的坐标，以锚点为原点。

##### getResolution()

获取元素的上下文分辨率。

##### isPointCollision(x, y)

判断事件坐标是否与元素相交。

##### setAttribute(key, value)

设置元素属性值。

##### setMouseCapture()

捕获鼠标。

##### setResolution({width, height})

设置元素的上下文分辨率。

##### releaseMouseCapture()

释放鼠标。

##### remove()

将元素从parent上移除。

##### removeAttribute(key)

移除元素属性值，恢复为默认值。

##### removeEventListener(type, listener, options)

移除事件监听器。

##### transition(sec, easing = 'linear')

创建过渡动画。