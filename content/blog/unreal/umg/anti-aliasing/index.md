+++
title = "UMG 抗锯齿"
date = 2025-08-16

[extra]
section_path = "blog/unreal/umg/_index.md"

[taxonomies]
tags = ["UMG", "anti-aliasing", "ue"]
+++


## 视口内的UI

默认不抗锯齿

### 方案1

美术资产自带抗锯齿效果

### 方案2

#### 单个图片

将单个图片放入材质中，这样就会有抗锯齿处理。
如果因为图片旋转而边缘有台阶式锯齿，需要在材质中旋转。

#### 多个UI控件

使用RetainerBox组件。
这个组件内部使用FWidgetRenderer，将子组件渲染到一个RT上。之后在材质中使用。
如此实现了抗锯齿。

## 场景中UI

使用UWidgetComponent
也使用了FWidgetRenderer, 因此是有抗锯齿的。
