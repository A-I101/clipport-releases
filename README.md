# ClipPort · Android 安装包

跨设备剪贴板同步 —— 在一台设备上复制，在另一台上粘贴。内容离开设备前始终端到端加密。

这个仓库**只存放安装包**，源码不在这里。目前提供 Android 版；macOS 版正在准备中，iOS 版尚未发布。

---

## ⬇️ 下载

用**手机浏览器**打开下面的链接，直接下载安装包：

**[ClipPort-universal.apk](https://github.com/A-I101/clipport-releases/releases/latest/download/ClipPort-universal.apk)**

一个包通吃所有机型，不用挑架构。历史版本见
[Releases 页面](https://github.com/A-I101/clipport-releases/releases)。

## 安装步骤

1. 用手机浏览器下载上面的 APK。
2. 点开下载好的文件。系统会提示不允许安装未知应用 —— 按提示进入设置，
   给**你正在用的这个浏览器或文件管理器**打开「允许安装未知应用」，再返回继续安装。
3. Play 保护机制可能提示这是未经 Play 扫描的应用，选择「仍然安装」。
4. 首次打开需要用 Google 账号登录。

升级到新版本时直接覆盖安装即可，不用先卸载。

**系统要求：** Android 7.0（API 24）及以上。

## 校验安装包

每个 Release 都附带 `SHA256SUMS.txt`。把它和 APK 放在同一个目录里，在电脑上核对：

```bash
sha256sum -c SHA256SUMS.txt      # macOS 上若没有这个命令：shasum -a 256 -c SHA256SUMS.txt
```

## 已知限制

- **同步走加密云中继。** 内容在设备上完成端到端加密后才上传，服务器只能看到密文；
  目前**没有**局域网直连模式。
- **Android 端只支持 Google 账号登录。**
- **这是直装版**，签名与将来上架 Google Play 的版本不同。届时若要改从 Play 安装，
  需要先卸载本版本 —— 本地剪贴板历史会一并清除。
- 应用内更新提示暂未实现，新版本请回本页面下载。

## 隐私

剪贴板内容在离开设备前即被端到端加密（X25519 密钥交换 + ChaCha20-Poly1305），
中继服务器无法解密。完整隐私政策见
[这里](https://gist.github.com/Antony138/db96d8b5b1d8fc76bbe1a7a2a7d5bd29)。

## 反馈

用得不顺、崩溃、翻译错误 —— 都欢迎开 [Issue](https://github.com/A-I101/clipport-releases/issues)。

---

## English

ClipPort is a cross-device clipboard: copy on one device, paste on another.
Everything is end-to-end encrypted before it leaves your device.

This repo hosts **the Android binary only** — the source lives elsewhere, and there
is no iOS release yet.

**Download:** [ClipPort-universal.apk](https://github.com/A-I101/clipport-releases/releases/latest/download/ClipPort-universal.apk)
— one build for every device. Older versions are on the
[Releases page](https://github.com/A-I101/clipport-releases/releases).

**Install:** open the downloaded file, allow "install unknown apps" for the browser
or file manager you used, then continue. Play Protect may warn that the app was not
scanned by Play — choose "Install anyway". Sign-in requires a Google account.
Requires Android 7.0 (API 24) or newer. Upgrades install over the top; no uninstall
needed.

**Heads-up:** these builds are signed with our own key, not Google Play's. If you
later switch to a Play install you will have to uninstall this one first, which
clears the local clipboard history. Sync currently goes through an encrypted cloud
relay; there is no LAN-direct mode yet.

Verify a download with `sha256sum -c SHA256SUMS.txt` (or `shasum -a 256 -c` on macOS).
[Privacy policy](https://gist.github.com/Antony138/db96d8b5b1d8fc76bbe1a7a2a7d5bd29) ·
[Report an issue](https://github.com/A-I101/clipport-releases/issues)
