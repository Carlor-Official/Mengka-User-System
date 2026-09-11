# 萌卡NT用户系统 2.0.9

- 修复同 QQ 的 Android 已在线时，Linux 免扫码登录仍因二维码响应格式误判而被取消的问题；用户端和管理端同时修复。
- 严格校验 Linux 二维码生成结果，避免将生成失败或状态查询响应用于 Android 授权；保留缓存登录及账号归属校验。
- 补充框架 v2.1.5 的 Linux 托管运行要求与启动报错处理说明。

## 升级说明

保留原有 2.x 配置、数据库和主密钥，无需删除或重新登记账号。独立部署可从 v2.0.8 的在线更新入口升级；手动升级前停止插件并备份数据。

框架 v2.1.5 的 Linux 托管模式要求框架以 root 系统服务运行，并安装 `bubblewrap`、`util-linux` 及提供 `useradd` 的系统软件包。出现 `isolated managed plugins require the framework system service to run as root` 表示框架启动身份不符合要求，插件尚未启动；请按[框架托管说明](https://github.com/Carlor-Official/Mengka-NT/blob/v2.1.5/docs/managed-plugins.md#linux-托管运行环境)处理。托管在线更新同时要求对应插件版本已通过市场审核。

提供 Windows AMD64、Linux AMD64、Linux ARM64 独立部署包及对应托管包。
