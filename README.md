# Test251204 — 语音波形可视化（Android 测试原型）

Android 端语音波形组件的独立测试项目，用 Kotlin 实现波形动画控件并进行性能压测。

## 功能

- 📊 实时音频波形条动画，无限向左滚动
- 🎛️ 支持纯正弦波测试模式（无需真实麦克风即可观察波形效果）
- 🎤 支持真实 `MediaRecorder` 麦克风音量采集
- ⚡ 20ms 刷新频率，高密度数据测试

## 核心组件

| 文件 | 说明 |
|------|------|
| `VoiceWaveView.kt` | 自定义 Canvas 波形条 View，支持滚动速度/颜色/圆角等参数 |
| `AudioRecorderHelper.kt` | MediaRecorder 音量采集封装 |
| `MainActivity.kt` | 测试入口，含正弦波 / 真实录音两种模式切换 |

## 运行

在 Android Studio 打开项目，Run 即可。`MainActivity` 中可通过 `isTestMode` 变量切换测试模式。

## 用途

本项目作为 **ZPC** 录音机和 **01**（Flutter VoiceWave）项目的 Android 端预研参考。