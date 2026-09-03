# 萌卡用户系统插件

萌卡 NT 的独立用户体系插件，提供用户端、管理端、QQ 账号、设备指纹、节点、商品、卡密、订单、支付、等级加速和邮件服务等功能。

> 本仓库仅用于发布正式外发包和版本说明，不提供插件源码，也不包含运行配置、用户数据、数据库、日志或密钥。

## 下载

请从 [GitHub Releases](https://github.com/Carlor-Official/Mengka-User-System/releases/latest) 下载与系统架构对应的外发包：

当前版本：**1.0.2**，配合萌卡 NT 1.9.8 或更高版本使用。详细变更见 [v1.0.2 版本说明](release-notes-v1.0.2.md)。

| 平台 | 外发包 | 启动入口 |
| --- | --- | --- |
| Windows AMD64 | `mengka-user-system-*-windows-amd64.zip` | `scripts/start-windows.cmd` |
| Linux AMD64 | `mengka-user-system-*-linux-amd64.tar.gz` | `scripts/start-linux.sh` |
| Linux ARM64 | `mengka-user-system-*-linux-arm64.tar.gz` | `scripts/start-linux.sh` |

下载后可使用同一 Release 中的 `SHA256SUMS.txt` 校验文件完整性。不同系统和架构的外发包不能混用。

## 使用要求

- 使用萌卡 NT 1.9.8 或更高版本提供的 `system_management` 服务权限及配套管理 API。
- 在框架服务列表中开启“系统管理插件”；框架会自动授权所需 action。随后配置框架分配的服务 Token 与服务 ID。
- 首次运行前将 `config.example.yaml` 复制为 `config.yaml`，按实际环境填写监听地址、框架地址和端口。
- `data` 目录包含插件数据库和本地主密钥，升级前必须完整备份，且不得公开分享。

外发包不包含预置用户、订单、支付配置或框架登录数据。完整安装、升级和兼容说明以各版本 Release 正文为准。
