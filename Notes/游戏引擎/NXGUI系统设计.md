2022-10-20, 11:18
Status: #note
Tags: #ui #netease

---
# NXGUI系统设计

什么是3D-UI： 3D Render pipline， Next-Gen GUI

渲染
-   NXGui系统，自己不做渲染，可渲染节点生成渲染管线所需要的 RenderNode
-   Canvas -> n * Widget，允许使用多个 Canvas，比较轻的概念，仅表示一些 Widget 是一组的，和标注位置
-   精确控制 UI 层级，和场景树层级解耦
-   Core -> World -> NXGUI -> Widgets
-   对象：组件化，类似 Unity

事件系统
-   参考 Cocoa 底层事件处理机制，捕获，目标，冒泡
-   EventHandler，多个事件处理组件处理一个事件
-   手势识别器

动画
	Timeline， Tag 标签系统，Goto  Stop 等语义

布局
	类似 Unity，QT