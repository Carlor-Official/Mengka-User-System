# 萌卡用户系统插件

萌卡 NT 的独立用户体系插件，提供统一登录与管理员/用户权限隔离、QQ 账号、节点协议绑定、套餐、卡密、订阅、订单、支付、公告和等级任务。

> 本仓库仅用于发布正式外发包和版本说明，不提供插件源码，也不包含运行配置、用户数据、数据库、日志或密钥。

## 下载

请从 [GitHub Releases](https://github.com/Carlor-Official/Mengka-User-System/releases/latest) 下载与系统架构对应的外发包：

当前版本：**2.0.7**，推荐配合萌卡 NT **2.1.1 或更新版本** 使用。详细变更与升级说明见 [v2.0.7 版本说明](release-notes-v2.0.7.md)。

| 平台 | 外发包 | 启动入口 |
| --- | --- | --- |
| Windows AMD64 | `mengka-user-system-*-windows-amd64.zip` | `scripts/start-windows.cmd` |
| Linux AMD64 | `mengka-user-system-*-linux-amd64.tar.gz` | `scripts/start-linux.sh` |
| Linux ARM64 | `mengka-user-system-*-linux-arm64.tar.gz` | `scripts/start-linux.sh` |

下载后可使用同一 Release 中的 `SHA256SUMS.txt` 校验文件完整性。不同系统和架构的外发包不能混用。

## 使用要求

- 先升级萌卡 NT 2.0.9 或更新版本；插件服务不绑定节点，账号操作由框架按照 `self_id + client_type` 路由到账号自己的登录节点。
- 插件通过框架服务 Token 认证后可直接调用管理 API，不需要“系统管理”开关或 action 授权清单。
- 独立部署可选择正向或反向 WS，填写地址、端口与 Token，首次启动创建自己的管理员。市场自动部署由框架分配连接，支持 SSO 快捷初始化管理员。
- 独立部署时将 `config.example.yaml` 复制为 `config.yaml`，填写监听地址与连接信息。市场安装包含 `managed`，由框架自动配置；管理入口和用户门户均支持 HTTP / HTTPS、IP / 域名。
- 从 2.x 更新：停止插件并备份配置和整个 `data` 目录，替换程序与启动脚本，保留原数据库和主密钥。
- 从 1.x 升级：必须使用独立新目录和全新的 `data/user-system-v2.db`，不读取、迁移或修改 1.x 旧库，旧配置不能直接复用。
- `data` 目录包含插件数据库和本地主密钥，升级前必须完整备份，且不得公开分享。主密钥用于解密配置及卡密，不能丢失。
- 首次安装后配置节点与协议绑定及付费套餐；卡密只能为付费套餐生成。

等级加速与框架共享开关、计划和数据，由框架执行定时任务。旧插件计划保留供核对，不自动覆盖框架计划，也不再由插件执行；升级后请核对计划并按需保存。

外发包不包含预置用户、订单、支付配置或框架登录数据。完整安装、升级和兼容说明以各版本 Release 正文为准。
