# 萌卡用户系统插件

萌卡 NT 的独立用户体系插件，提供管理员与用户独立登录、QQ 账号、节点协议绑定、套餐、卡密、订阅、订单、支付、公告和等级任务。

> 本仓库仅用于发布正式外发包和版本说明，不提供插件源码，也不包含运行配置、用户数据、数据库、日志或密钥。

## 下载

请从 [GitHub Releases](https://github.com/Carlor-Official/Mengka-User-System/releases/latest) 下载与系统架构对应的外发包：

当前版本：**2.0.0**，配合萌卡 NT **2.0.5** 使用。详细变更和破坏性升级说明见 [v2.0.0 版本说明](release-notes-v2.0.0.md)。

| 平台 | 外发包 | 启动入口 |
| --- | --- | --- |
| Windows AMD64 | `mengka-user-system-*-windows-amd64.zip` | `scripts/start-windows.cmd` |
| Linux AMD64 | `mengka-user-system-*-linux-amd64.tar.gz` | `scripts/start-linux.sh` |
| Linux ARM64 | `mengka-user-system-*-linux-arm64.tar.gz` | `scripts/start-linux.sh` |

下载后可使用同一 Release 中的 `SHA256SUMS.txt` 校验文件完整性。不同系统和架构的外发包不能混用。

## 使用要求

- 先升级萌卡 NT 2.0.5；插件服务不绑定节点，账号操作由框架按照 `self_id + client_type` 路由到账号自己的登录节点。
- 插件通过框架服务 Token 认证后可直接调用管理 API，不需要“系统管理”开关或 action 授权清单。
- 只配置一个框架服务的地址、端口与 Token；2.0.0 不再使用框架 SSO，首次启动由插件创建独立管理员。
- 首次运行前将 `config.example.yaml` 复制为 `config.yaml`，按实际环境填写监听地址、框架地址和端口。
- 必须使用全新的 `data/user-system-v2.db`。不读取、迁移或修改 1.x 旧库，旧配置不能直接复用。
- `data` 目录包含插件数据库和本地主密钥，升级前必须完整备份，且不得公开分享。主密钥用于解密配置及卡密，不能丢失。
- 首次安装后配置节点与协议绑定及付费套餐；卡密只能为付费套餐生成。

外发包不包含预置用户、订单、支付配置或框架登录数据。完整安装、升级和兼容说明以各版本 Release 正文为准。
