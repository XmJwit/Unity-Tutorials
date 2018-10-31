# 发光材质
虽然预计算实时GI不支持区域光源，但使用“Emissive Materials（发光材质）”仍然可以实现类似的柔和照明效果。与区域光源一样，发光材料在其表面区域发光。它们有助于在场景中反射光线，并且在游戏过程中可以更改颜色和强度等相关属性。

“Emission”是Standard Shader（标准着色器）的属性，它允许场景中的静态对象发光。默认情况下，'Emission'的值设置为零。这意味着使用标准着色器指定材质的对象不会发出光。HDR颜色选择器可用于选择强度超过0-1范围的颜色，以创建类似于区域光源的明亮灯光效果。

发光材质没有范围值，但发出的光将以二次速率再次衰减。只有Inspector中标记为“Static”或“Lightmap Static”的对象才会接收发射。类似地，应用于非静态或动态几何体（例如角色）的发光材质将不会有助于场景照明。

然而，即使它们对场景照明没有贡献，发光数值在零以上的材质仍然会在屏幕上明亮地发光。通过从标准着色器的“Global Illumination（全局照明）”属性中选择“None”，也可以生成此效果。像这样的自发光材料是产生类似霓虹灯其他可见光源之类的效果的有用方式。

![](/Image/Graphics/Introduction/emissives_2.png)

*使用Unity标准着色器的“Emission”属性创建的简单霓虹灯效果。注意光照如何仍然被静态几何体遮蔽*

自发光材质仅直接影响场景中的静态几何体。如果您需要动态或非静态几何体（如字符）从发光材质中获取光线，则必须使用光探针（Light Probes）。在游戏过程中更改发光参数值将动态更新Light Probes，并直接在结果上看到变化。

[返回上一级](/Graphics/Introduction-to-Lighting-and-Rendering.md)

[返回主页](/README.md)