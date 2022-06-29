# playWebmForiOS
借鉴自github上另外一个大神的代码，本仓库比之更详尽一些，希望能够帮到对播放webm迷茫的朋友们

源库：https://github.com/dolphinsue319/KDAnimatedImage

第一步 运行KDAnimatedImageBuilder这个target，这个会执行对应Build Phases中的脚本打包出framework

可能会报错情况1

```
xcodebuild[22187:279813] Requested but did not find extension point with identifier Xcode.IDEKit.ExtensionSentinelHostApplications for extension Xcode.DebuggerFoundation.AppExtensionHosts.watchOS of plug-in com.apple.dt.IDEWatchSupportCore
xcodebuild[22187:279813] Requested but did not find extension point with identifier Xcode.IDEKit.ExtensionPointIdentifierToBundleIdentifier for extension Xcode.DebuggerFoundation.AppExtensionToBundleIdentifierMap.watchOS of plug-in com.apple.dt.IDEWatchSupportCore
```

报错的解决方案

Remove CommandLineTools

```
sudo rm -rf /Library/Developer/CommandLineTools
```

Reinstall CommandLineTools

```
xcode-select --install
```

Select CommandLineTools

```
sudo xcode-select -s /Library/Developer/CommandLineTools
```
参考：https://developer.apple.com/forums/thread/703233

可能报错情况2

需要注意demo的bundleID和framework的bundleId不能相同，否则的话，报错Unable to install “xxxx”

第二步 引入编译好的framework
