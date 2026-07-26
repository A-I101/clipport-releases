# ClipPort · 安装包下载

跨设备剪贴板同步 —— 在一台设备上复制，在另一台上粘贴。内容离开设备前始终端到端加密。

这个仓库**只存放安装包**，源码不在这里。目前提供 Android 和 macOS 版；iOS 版尚未发布。

---

## ⬇️ 下载

| 平台 | 下载 | 系统要求 |
| --- | --- | --- |
| **Android** | [ClipPort-universal.apk](https://github.com/A-I101/clipport-releases/releases/latest/download/ClipPort-universal.apk) | Android 7.0（API 24）及以上 |
| **macOS** | [ClipPort.dmg](https://github.com/A-I101/clipport-releases/releases/latest/download/ClipPort.dmg) | macOS 10.15（Catalina）及以上，Apple 芯片与 Intel 通用 |

历史版本见 [Releases 页面](https://github.com/A-I101/clipport-releases/releases)。

## 安装

### Android

1. 用**手机浏览器**打开上面的 APK 链接下载。
2. 点开下载好的文件。系统会提示不允许安装未知应用 —— 按提示进入设置，
   给**你正在用的这个浏览器或文件管理器**打开「允许安装未知应用」，再返回继续安装。
3. Play 保护机制可能提示这是未经 Play 扫描的应用，选择「仍然安装」。

升级到新版本时直接覆盖安装即可，不用先卸载。

### macOS

1. 下载 DMG，双击打开，把 ClipPort 拖进「应用程序」文件夹。
2. 首次打开时系统会问一句「这是从互联网下载的应用，确定要打开吗」，点「打开」即可。

安装包已经过 Apple 公证（Developer ID 签名 + notarization + stapling），
**不需要**右键绕过 Gatekeeper，也不用去「安全性与隐私」里放行。

## 登录方式

| 平台 | Google | Apple |
| --- | --- | --- |
| Android | ✅ | — |
| macOS | ✅ | ❌ |

macOS 版**只支持 Google 账号登录**。「通过 Apple 登录」需要一项 Apple 只发放给
Mac App Store 应用的权限，本页面的直装版拿不到，所以按钮已隐藏而不是留着报错。
如果你的账号是用 Apple ID 注册的，暂时无法在 macOS 版上登录。

## 校验安装包

每个 Release 都附带 `SHA256SUMS.txt`（Android）和 `SHA256SUMS-macos.txt`（macOS）。
和安装包放在同一目录里核对：

```bash
sha256sum -c SHA256SUMS.txt          # macOS 上若没有这个命令：shasum -a 256 -c ...
```

## 已知限制

- **同步走加密云中继。** 内容在设备上完成端到端加密后才上传，服务器只能看到密文；
  目前**没有**局域网直连模式。
- **Android 直装版**的签名与将来上架 Google Play 的版本不同。届时若要改从 Play 安装，
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

This repo hosts **the binaries only** — the source lives elsewhere, and there is
no iOS release yet.

| Platform | Download | Requires |
| --- | --- | --- |
| **Android** | [ClipPort-universal.apk](https://github.com/A-I101/clipport-releases/releases/latest/download/ClipPort-universal.apk) | Android 7.0 (API 24)+ |
| **macOS** | [ClipPort.dmg](https://github.com/A-I101/clipport-releases/releases/latest/download/ClipPort.dmg) | macOS 10.15 (Catalina)+, universal (Apple silicon + Intel) |

**Android:** open the downloaded file, allow "install unknown apps" for the browser
or file manager you used, then continue. Play Protect may warn that the app was not
scanned by Play — choose "Install anyway". Upgrades install over the top.

**macOS:** open the DMG and drag ClipPort to Applications. The build is signed with a
Developer ID certificate, notarized by Apple and stapled, so the first launch only
asks the standard "downloaded from the Internet" question — no right-click bypass and
no trip to System Settings.

**Sign-in:** Google works everywhere. Sign in with Apple is unavailable in the macOS
build — the entitlement is only granted to Mac App Store apps — so the button is
hidden rather than left to fail. An account created with an Apple ID cannot sign in
on macOS for now.

**Heads-up:** the Android builds here are signed with our own key, not Google Play's.
If you later switch to a Play install you will have to uninstall this one first, which
clears the local clipboard history. Sync currently goes through an encrypted cloud
relay; there is no LAN-direct mode yet.

Verify a download with `sha256sum -c SHA256SUMS.txt` (or `shasum -a 256 -c` on macOS).
[Privacy policy](https://gist.github.com/Antony138/db96d8b5b1d8fc76bbe1a7a2a7d5bd29) ·
[Report an issue](https://github.com/A-I101/clipport-releases/issues)
