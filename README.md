# 萌卡用户系统插件

萌卡 NT 的独立用户体系插件，提供用户端、管理端、QQ 账号、设备指纹、节点、商品、卡密、订单、支付、等级加速和邮件服务等功能。

> 本仓库仅用于发布正式外发包和版本说明，不提供插件源码，也不包含运行配置、用户数据、数据库、日志或密钥。

## 下载

请从 [GitHub Releases](https://github.com/Carlor-Official/Mengka-User-System/releases/latest) 下载与系统架构对应的外发包：

当前版本：**1.0.4**，配合萌卡 NT 2.0.1 使用。详细变更见 [v1.0.4 版本说明](release-notes-v1.0.4.md)。

| 平台 | 外发包 | 启动入口 |
| --- | --- | --- |
| Windows AMD64 | `mengka-user-system-*-windows-amd64.zip` | `scripts/start-windows.cmd` |
| Linux AMD64 | `mengka-user-system-*-linux-amd64.tar.gz` | `scripts/start-linux.sh` |
| Linux ARM64 | `mengka-user-system-*-linux-arm64.tar.gz` | `scripts/start-linux.sh` |

下载后可使用同一 Release 中的 `SHA256SUMS.txt` 校验文件完整性。不同系统和架构的外发包不能混用。

## 使用要求

- 使用萌卡 NT 2.0.1 提供的当前管理 API；插件通过框架服务 Token 认证后可直接调用，不需要“系统管理”开关或 action 授权清单。
- 配置框架分配的服务 Token 与服务 ID。插件管理端地址只用于管理员 SSO 和快捷入口，可以留空。
- 首次运行前将 `config.example.yaml` 复制为 `config.yaml`，按实际环境填写监听地址、框架地址和端口。
- `data` 目录包含插件数据库和本地主密钥，升级前必须完整备份，且不得公开分享。

外发包不包含预置用户、订单、支付配置或框架登录数据。完整安装、升级和兼容说明以各版本 Release 正文为准。
