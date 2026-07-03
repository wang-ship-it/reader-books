# APK 更新文件

把新版 APK 放在这个目录，并确保 `../app-update.json` 里的 `apkUrl` 指向它。

推荐正式分发时使用 release 签名 APK，例如：

```text
apk/app-release.apk
```

当前 App 内置的检查地址是：

```text
https://wang-ship-it.github.io/reader-books/app-update.json
```
