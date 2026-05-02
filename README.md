# PrivacyCapsule-src

```code
请用 C++ 实现一个 Windows 10/11 桌面隐私提示工具，常驻系统托盘，检测摄像头、麦克风、位置是否被应用使用，并尽量显示应用名或来源。  
当检测到隐私权限被使用时，在屏幕底部居中弹出一个精致的无边框胶囊悬浮窗，类似 Dynamic Island。  
悬浮窗使用 Win32 API 实现，样式包含 WS_POPUP、WS_EX_TOPMOST、WS_EX_TOOLWINDOW、WS_EX_LAYERED、WS_EX_NOACTIVATE，可选 WS_EX_TRANSPARENT 鼠标穿透。  
悬浮窗高度约 56px，圆角半径约 28px，深色半透明/Acrylic/Blur 质感，柔和阴影，无标题栏、不进任务栏、不抢焦点。  
内容包含权限图标和提示文字，例如“微信正在使用麦克风”“Teams 正在使用摄像头”“某个应用正在使用位置信息”。  
实现入场动画：350ms，上浮、淡入、缩放 0.92→1.0，带弹簧感；内容变化时宽度平滑过渡 250ms。  
实现退场动画：220ms，淡出、轻微缩小、向下移动，结束后隐藏窗口。  
监听模块包含 MicrophoneMonitor、CameraMonitor、LocationMonitor，麦克风优先使用 Core Audio API 获取活动 session 和进程名。  
摄像头和位置监听可使用 Windows API、设备状态、隐私状态、事件日志或可扩展接口实现，无法识别应用时显示“某个应用”。  
提供系统托盘菜单：设置、测试悬浮窗、开启/关闭摄像头监听、开启/关闭麦克风监听、开启/关闭位置监听、开机自启、退出。  
实现简洁美观的设置界面，支持开关监听项、启用/禁用悬浮窗、动画、模糊效果、鼠标穿透、显示应用名称。  
支持用户自定义提示文案模板，如“{app} 正在使用麦克风 / 摄像头 / 位置信息”。  
设置界面提供测试按钮：测试麦克风、测试摄像头、测试位置、多权限同时提示。  
代码需模块化设计：App、TrayManager、FloatingCapsuleWindow、PrivacyMonitor、SettingsWindow、SettingsStorage。  
要求支持高 DPI、多显示器、配置持久化，并提供可编译运行的完整 C++ 示例代码。
```

Inspiration source: voice-input-src
