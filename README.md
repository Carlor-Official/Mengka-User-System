# 萌卡用户系统插件

萌卡 NT 的原生 Go 用户体系插件，提供 QQ、等级折扣、商品套餐、余额与佣金、分站、支付、卡密、提现及系统配置。通过框架官方 IPC/API 载入和获取节点、登录及等级任务能力，不修改框架。

本仓库只提供外发成品包和版本说明，不包含插件源码、运行配置、用户数据或密钥。

## 下载

当前正式版本：**3.0.0**，最低框架为官方萌卡 NT **2.5.3**。请阅读 [3.0.0 版本与升级说明](release-notes-v3.0.0.md)，再从 [GitHub Release](https://github.com/Carlor-Official/Mengka-User-System/releases/tag/v3.0.0) 下载对应平台包。

| 平台 | 外发包 |
| --- | --- |
| Windows AMD64 | `mengka-user-system-3.0.0-managed-native-windows-amd64.zip` |
| Linux AMD64 | `mengka-user-system-3.0.0-managed-native-linux-amd64.tar.gz` |
| Linux ARM64 | `mengka-user-system-3.0.0-managed-native-linux-arm64.tar.gz` |

在框架「插件 → 插件导入」上传对应包。`managed-native` 表示由框架托管启动的原生 IPC 包；每个平台只需一个包，没有另一套独立服务版。下载后按同一 Release 的 `SHA256SUMS.txt` 校验文件完整性。

## 使用与升级

- Go 程序内嵌前端，安装运行无需 Node、PHP、better-sqlite3 或 C++ 运行库。Linux 按 GLIBC 2.28 及以上兼容环境提供静态构建。
- 用户门户通过框架对外地址下的 `/user/` 访问。管理员使用框架 SSO 或统一登录页的框架管理员账号密码；按权限切换端视角，不公开管理数据。
- 插件不提供独立 SSL、域名、端口、令牌或反代配置，站点域名字段仅作业务资料。
- **旧 2.x Node 数据库不能直接覆盖升级。** 停止插件并备份整个数据目录及主密钥，旧库需先完成单独迁移和账目核对；未完成迁移的环境继续使用原版本。当前迁移工具并非通用生产迁移工具，外发包也不附带自动迁移程序。
- 全新安装使用空数据目录；已验证的 Go schema 5 数据库及原主密钥可保留数据更新。检测到未迁移旧库时程序拒绝初始化，保护旧数据。
- 商户支付、QQ 登录/离线/等级执行、SMTP/OAuth 需在各自真实服务环境核验。微信当前提供 Native 扫码；外部商户自动退款不作为本版功能。框架未接入托管更新时使用手动导入。

所有安装、兼容、数据迁移和回退限制以对应版本说明为准。发布外发包不表示已替用户部署或完成真实业务验收。
