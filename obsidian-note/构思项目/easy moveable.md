# Inspect

继承 Layer => Boundary. 

## 选项

`new Inspect(target: HTMLElement, options?: Option)`

Option:

+ moveable = true; 
+ rotatable = true;
+ resizable = true;

创建

+ 创建时候, 判断target的 $inspectId. 获取到, 抛出异常. 

## 属性

+ 结构化的属性
+ options: cloneDeep init options. 
+ moveable, rotatable....
+ destroy
+ ~~get group: () => string[]~~
+ layer?: Layer. 图层. jsonSchema 是没有的. 
  + getter
  + 从 manager.layerMap 获取
  + 如果没有则创建
+ layerName?: string. 图层名称
+ schema: 生成数据. GET
+ ~~generateHtml: 生成对应html.~~
+ structure: 转换成自身对应的Structure. 并在manager中记录.
+ toolBar: ToolBar. `new ToolBar(target: HTMLElement)`

## 样式

+ 外部包围一个BOX; 
+ 头部一个工具栏;
+ 盒子应该是 overflow: hidden;

## 头部工具栏

+ 组件名称
+ 上一级
+ 删除
+ 扩展其他功能
	+ 组件属性

## 结构化 & 可拖拽区域

这个可以实现拖拽到内部. 内部容器? 

### 方法

+ children.
+ appendChildren.
+ removeChildren.
+ parent: Inspect.



+ prev: 上一级
+ ~~structure: 调用对应静态方法~~
## Layer

同级合并. 

继承 Boundary.

Inpect 的分组. 1 -> 多.

+ 一个分组对应多个 inspect.
+ 一个 inspect 可以有多个分组.

~~层级关系: 暂无.~~

创建的时候, 判断是否已经存在. 存在抛出异常. 创建成功, 在 manager.layerMap 添加. 

### 属性

+ _lock: @default false;
+ name: string;

+ lock: () => void;
+ unlock: () => void;
+ group: Inpect[];
+ merge(...otherInspect)
  + otherInspect 不能有 layer. 
  + 已经有 layer. 先解锁, 图层总去除自身. 
+ remove: (inspect) => void; 去除掉某个 inspect
+ delete: 删除图层以及地下的所有的 inspect. 

## Boundary

显示边界. 

`new Boundayr(visible?: boolean)`

+ boundaries: HTMLElement[]; 4个边界线. 
+ _selected = false;
+ select: () => void: 选中当前. 
+ _visible = false;
+ hide
+ show
+ container: Option.target. HTMLElement.
+ destroy: 销毁注册的事件. 例如: target 属性变化, 触发boundaries更新. 
  + *https://juejin.cn/post/7025435825319968798*

## ToolBar

+ container
+ extendsControl: () => HTMLElement: 工具栏添加元素.  
+ destroy: 销毁相关事件. 

## Moveable

## 属性

+ inspect
+ moveTo(point)

## 事件

+ move.start
+ move.move
+ move.end



## Resizable

option

+ ~~maxWidth~~
+ ~~maxHeight~~

## 属性

+ controls
  + 在 Inspect 的 boundaries 上创建. 
  + 在 4个 角创建. 

## 事件

+ resize.start
+ resize.move
+ resize.end



## Rotatable

+ controls
  + 在 topLine 中创建, 并绝对定位. 

## 事件

+ rotate.start
+ rotate.move
+ rotate.end

# Manager

单一实例, 直接暴露出去.

在DOM上暴露Inspect.id. 

+ eventBus
+ layerMap<name, layer>

+ select(id)
+ multiple = false; 是否多选.
+ get(id | DOM) => Inspect. 
+ root: Inspect[]. 根元素
+ structure:All () => Structure: 获取所有结构.
  + uniq(layer.children.map(o => o.layer)).map(o => o.structure)
+ inspectWeakMap<container: HTMLElement, schema>
+ ~~onStructureChange: (schema) => void;~~
+ remove
+ destroyAll
+ create: 创建 Inpect 实例. 
  + 选项
    + selector: 选择器. 
    + layer?: boolean | LayerOption. 是否创建图层. 默认 ture
    + inspectOption?:  InspectOption. 修改Inspect参数. 
+ createLayer: 创建图层. 
+ merge(inspect, inspect, ...): 合并图层. 2个甚至多个. 
+ canMerge: (inspect, inspect, ...) => boolean; 是否能合并图层. 
  + 必须2者都没有图层
  + 都是同一级(即inspect.parent相同).



# Stack

如何实现 上一步下一??????

模仿 bpmnjs 的方式???

+ 合并操作?



# Event

自定义

+ structure.change
+ inspect.select
+ inspect.destory
+ ~~layer.merge~~
+ layer.change
+ ~~layer.remove~~
+ ~~layer.lock.change~~

# 问题

1. 先确定有没有层级关系. 
   1. 安装目前的场景, 是没有层级关系的. 
   2. 如果有层级关系, 交互是怎么样的. 
   3. 图层如果有层级是不能合并非同级的. 



