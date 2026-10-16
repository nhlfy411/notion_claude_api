# notion_claude_api

HARLEY 实时光线步进（Raymarching）演示。用 WebGL 着色器在浏览器里实时渲染，不需要安装任何依赖。

## 在线预览

- 首页：https://nhlfy411.github.io/notion_claude_api/
- 展示页：https://nhlfy411.github.io/notion_claude_api/showcase.html

## 页面说明

- **`index.html`（首页）**：动画作为背景，中间是 HARLEY 标题和「进入展示 →」按钮。
- **`showcase.html`（展示页）**：完整的展示页，带形态名称和帧率显示。左上角可以返回首页。

## 三种形态

1. 液态金属 · METABALLS：几个融球平滑地融合在一起
2. 极小曲面 · GYROID：陀螺极小曲面做成的镂空球壳
3. 双螺旋环 · TWISTED TORUS：扭成双螺旋的圆环

形态每 8 秒自动切换一次，切换时会平滑过渡。

## 操作

- 拖动：旋转视角（松手后带惯性）
- 轻点：切换到下一个形态

## 技术要点

- 用全屏三角形加片元着色器做 SDF 光线步进
- 用 smooth min 融合几个形态，形态之间做插值过渡
- 加了菲涅尔反射、环境光遮蔽、发光、星空背景
- 用 ACES 色调映射，加了暗角和胶片颗粒
- 分辨率会根据帧率自动调整，手机上也能流畅运行
