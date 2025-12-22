# 🎄 Xmas Dream - 梦幻圣诞树

一个基于 **React Three Fiber** 和 **MediaPipe** 的交互式 3D 圣诞树项目，提供鼠标交互和 AI 手势控制两种模式。

![Preview](https://img.shields.io/badge/status-active-success.svg)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

## ✨ 特性

### 🎨 定制版 (Custom Edition)
- 📸 **照片上传** - 将您的照片作为装饰挂在圣诞树上
- 🎨 **主题切换** - 4 种预设主题（经典金、冰雪、梦幻粉、复古风）
- 🎨 **自定义配色** - 自由调整树叶、灯光、背景颜色
- 💌 **祝福卡片** - 创建个性化的圣诞祝福
- 📷 **贺卡分享** - 一键保存您的贺卡
- 🎵 **背景音乐** - 沉浸式圣诞氛围

### 🤚 手势版 (Gesture Mode)
- 🧠 **AI 手势识别** - 基于 Google MediaPipe Hand Landmarker
- ✊ **握拳/捏合** - 粒子聚拢成圣诞树
- ✋ **张开手掌** - 粒子向四周炸开
- 👋 **左右移动** - 控制场景旋转角度（高灵敏度）
- 📹 **实时预览** - 右下角显示摄像头镜像画面
- 🎯 **光标跟随** - 自定义光标跟随手指移动

## 🚀 在线体验

访问以下链接即可体验：

- 🏠 **入口页面**: [https://yourusername.github.io/xmas-dream/](https://yourusername.github.io/xmas-dream/)
- 🎨 **定制版**: [https://yourusername.github.io/xmas-dream/xmas-custom.html](https://yourusername.github.io/xmas-dream/xmas-custom.html)
- 🤚 **手势版**: [https://yourusername.github.io/xmas-dream/xmas-gesture.html](https://yourusername.github.io/xmas-dream/xmas-gesture.html)

## 🛠️ 技术栈

- **React 18.2** - UI 框架
- **Three.js 0.160** - 3D 渲染引擎
- **React Three Fiber 8.15** - React 的 Three.js 渲染器
- **@react-three/drei** - Three.js 辅助工具库
- **@react-three/postprocessing** - 后期处理效果（Bloom、Vignette、Noise）
- **MediaPipe Hand Landmarker** - Google AI 手势识别
- **Tailwind CSS** - 样式框架
- **Babel Standalone** - 浏览器端 JSX 转译

## 📦 本地运行

由于这是纯静态 HTML 项目，您只需：

1. **克隆仓库**
   ```bash
   git clone https://github.com/yourusername/xmas-dream.git
   cd xmas-dream
   ```

2. **启动本地服务器**
   ```bash
   # 使用 Python
   python -m http.server 8000
   
   # 或使用 Node.js
   npx serve
   ```

3. **访问浏览器**
   ```
   http://localhost:8000
   ```

## 🎮 使用指南

### 定制版操作
1. 上传您的照片（支持多张）
2. 点击 "ENTER" 进入场景
3. 选择预设主题或自定义配色
4. 填写祝福卡片内容
5. 点击圣诞树切换 TREE/EXPLODE 模式
6. 点击照片放大查看
7. 使用顶部工具栏截图/播放音乐

### 手势版操作
1. 点击 "启动手势控制"
2. 允许摄像头权限
3. 等待 AI 模型加载完成
4. 使用以下手势：
   - **握拳** → 粒子聚拢成树
   - **张手** → 粒子炸开 + 允许旋转
   - **手掌左右移动** → 旋转场景

## 📁 项目结构

```
xmas-dream/
├── index.html          # 入口页面（选择模式）
├── xmas-custom.html    # 定制版（照片、配色、卡片）
├── xmas-gesture.html   # 手势版（AI 交互）
└── README.md           # 项目说明
```

## 🎨 主题预设

| 主题 | 背景 | 树叶 | 装饰 | 灯光 |
|------|------|------|------|------|
| **Classic Gold** | 深红 | 深绿 | 金色 | 金黄 |
| **Frozen** | 深蓝 | 冰蓝 | 银白 | 冰白 |
| **Dreamy Pink** | 深粉紫 | 粉色 | 淡紫 | 粉红 |
| **Vintage** | 棕黑 | 棕红 | 米黄 | 橙黄 |

## 🔧 自定义开发

### 修改粒子数量
在 `xmas-custom.html` 或 `xmas-gesture.html` 中修改：

```javascript
const COUNT_LEAVES = 6000;  // 树叶数量
const COUNT_DECOR = 500;    // 装饰数量
const COUNT_RIBBON = 800;   // 丝带数量
```

### 调整手势灵敏度
在 `xmas-gesture.html` 中修改：

```javascript
handRotRef.current = (0.5 - lm[0].x) * 6;  // 最后的系数控制旋转速度
```

### 更改主题配色
在 `xmas-custom.html` 的 `PRESETS` 对象中添加新主题。

## 🌟 性能优化

- 使用 `InstancedMesh` 渲染 7000+ 几何体，保持 60fps
- Bloom 效果优化阈值，避免过曝
- MediaPipe 使用 GPU 加速
- 动态 LOD（Level of Detail）管理

## 🐛 已知问题

- Safari 可能不支持 MediaPipe，建议使用 Chrome/Edge
- 手势模式需要良好的光照环境
- 首次加载需要下载约 8MB 的 AI 模型

## 📄 License

MIT License - 自由使用、修改、分发

## 🙏 致谢

- [Three.js](https://threejs.org/) - 强大的 3D 库
- [React Three Fiber](https://docs.pmnd.rs/react-three-fiber/) - 优雅的 React 集成
- [MediaPipe](https://developers.google.com/mediapipe) - Google AI 手势识别
- [Tailwind CSS](https://tailwindcss.com/) - 高效的样式框架

## 📮 联系方式

如有问题或建议，欢迎：
- 提交 [Issue](https://github.com/yourusername/xmas-dream/issues)
- 发送邮件至：your.email@example.com

---

⭐ 如果您喜欢这个项目，请给一个 Star！

Made with ❤️ during Christmas 2025 🎄

