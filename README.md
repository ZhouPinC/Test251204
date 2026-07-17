# Android Voice Wave Test

一个使用 Kotlin 实现的 Android 音频波形实验项目，用于比较模拟正弦波输入与真实麦克风振幅输入的可视化效果。

## 功能

- 自定义 `VoiceWaveView` 实时绘制滚动波形。
- 默认以正弦波生成测试数据，便于无麦克风环境调试。
- 可切换到 `MediaRecorder` 振幅采集模式。
- 以约 20 ms 间隔刷新波形数据。
- 处理 Android 麦克风运行时权限。

## 技术栈

- Kotlin
- Android SDK 36，最低支持 Android 7.0（API 24）
- Java 11 / JVM 11
- AndroidX、Material Components 与 ConstraintLayout
- Gradle Kotlin DSL

## 目录结构

```text
Test251204/
|-- app/src/main/java/com/example/test/
|   |-- MainActivity.kt                 # 页面、权限和数据刷新
|   |-- util/AudioRecorderHelper.kt     # 麦克风振幅采集
|   `-- widget/VoiceWaveView.kt         # 自定义波形 View
|-- app/src/main/res/                   # 布局与主题资源
|-- gradle/                             # Version Catalog 与 Wrapper
`-- settings.gradle.kts
```

## 本地运行

1. 使用 Android Studio 打开仓库根目录。
2. 使用 JDK 11 或项目兼容的 Android Studio 内置 JDK 完成 Gradle 同步。
3. 连接 API 24 或更高版本的设备/模拟器并运行 `app`。

命令行构建：

```powershell
.\gradlew.bat assembleDebug
```

## 模式切换

`MainActivity.kt` 中的 `isTestMode` 默认为 `true`，此时显示模拟正弦波。将其设为 `false` 后，应用会请求麦克风权限并读取真实振幅。

## 状态

用于验证自定义波形绘制和录音采样的实验项目，尚未形成可发布产品。
