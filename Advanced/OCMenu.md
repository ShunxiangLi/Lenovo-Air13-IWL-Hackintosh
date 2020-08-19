# OpenCore 菜单

- 怎么隐藏菜单 ？
  - Config.plist - Misc - Boot
    - `ShowPicker		Boolean		NO`
- 单 ESP 分区菜单看不到 Windows 怎么办 ？
  - Config.plist - Misc - Security
    - `ScanPolicy		Number		0`  ( 自定义必须包含 ESP )
  - Config.plist - Misc
    - BlessOverride  ( 覆盖替换掉 Windows 的 BOOTx64.efi 情况下, 需要在此指定 Windows 引导 )
      - `Item0		<String>	\EFI\Microsoft\Boot\bootmgfw.efi`
- 怎么临时开启 -V 模式 ？
  - Config.plist - Misc - Boot
    - `PollAppleHotKeys		Boolean		YES` 
  - 对小新 Air13IWL 来说 , 开机前按住 ESC 键 , 显示菜单后按下 CMD + V 然后选择 MacOS 即可
- 怎么让 MacOS 成为 OC 默认引导系统 ？
  - 方法1 : OC 0.5.4 版本之后打开下列开关 , 在引导菜单使用 Ctrl + Index 或 Ctrl + Enter 设置默认项
    - Config.plist - Misc - Security
      - `AllowSetDefault		Boolean		YES`
  + 方法2 : 对于支持原生 NVRAM 机型 , 在 `系统偏好设置 - 启动磁盘` 选择对应的卷宗重启即可