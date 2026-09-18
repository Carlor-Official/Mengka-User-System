# 萌卡 NT 用户系统 v2.1.0

## 发布内容

- 正式提供 Windows AMD64、Linux AMD64 和 Linux ARM64 三个平台的原生 IPC 外发包。
- 使用框架 `native-ipc-v1` 接入，声明并验证 46 个框架动作。
- 最低支持萌卡 NT `2.4.1`，插件由框架负责导入、启动、停止和数据目录管理。
- 外发包仅包含平台原生程序与 `mengka-plugin.json`，不包含源码、配置、用户数据、数据库、日志或密钥。

## 下载与安装

请下载与运行环境完全匹配的包：

- Windows AMD64：`mengka-user-system-2.1.0-managed-native-windows-amd64.zip`
- Linux AMD64：`mengka-user-system-2.1.0-managed-native-linux-amd64.tar.gz`
- Linux ARM64：`mengka-user-system-2.1.0-managed-native-linux-arm64.tar.gz`

同时下载对应的 `*-native.json` 和 `SHA256SUMS.txt` 校验文件完整性，然后在萌卡 NT 的「插件 → 插件导入」中手动上传。框架不会从官网自动下载或更新该插件。

Linux 包要求 GLIBC 2.28 及以上和系统标准 C++ 运行库，不支持 musl/Alpine。升级前请停止插件并完整备份 `data` 目录；导入新包时保留原数据库和主密钥。
