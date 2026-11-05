# 萌卡NT用户系统

萌卡 NT 用户管理插件，提供 QQ 管理、商品套餐、用户等级、余额与佣金、支付、卡密、提现及分站功能。

## 下载

当前版本：**3.0.17**，最低框架版本：**3.0.8**。本版不兼容框架 2.x。

查看 [最新更新日志](release-notes/release-notes-v3.0.17.md) 或 [历史版本说明](release-notes/README.md)，从 [GitHub Release](https://github.com/Carlor-Official/Mengka-User-System/releases/tag/v3.0.17) 下载对应平台的安装包。

| 系统 | 安装包 |
| --- | --- |
| Windows AMD64／x86_64 | `mengka-user-system-3.0.17-managed-native-windows-amd64.zip` |
| Linux AMD64／x86_64 | `mengka-user-system-3.0.17-managed-native-linux-amd64.tar.gz` |
| Linux ARM64／AArch64 | `mengka-user-system-3.0.17-managed-native-linux-arm64.tar.gz` |

Windows 使用原生程序，无需 Docker；Linux 按 Docker Engine 架构选择安装包。

## 安装与更新

- 先将框架升级至 3.0.8 或更新版本，再在「插件 → 插件导入」上传对应平台的完整安装包。
- 在插件「系统设置 → 检查版本更新」查看新版，按页面提示进入框架管理完成更新。
- 旧插件无法启动时，直接在框架导入新版安装包并保留原数据，无需先卸载；导入后若显示已停止，点击启动。
- 升级前备份完整数据目录和主密钥，导入更新时保留原数据。
- 旧 Windows Docker 安装需先停止插件、导出并备份数据，再按框架流程迁移至原生运行，请勿直接删除旧数据。
- 旧 2.x 版本需先完成数据迁移，不能直接覆盖升级。
- 升级后旧 QQ 记录若显示“待核对”，在管理端选择对应的当前协议账号，通过“核对迁移绑定”恢复关联，用户与业务历史保留。

## 使用说明

用户通过框架 Web 地址下的 `/user/` 直接访问，无需先登录框架。域名反向代理应指向框架 Web 服务，不能指向插件管理网关。管理员可从框架打开管理端，也可使用框架管理员账号登录。

用户门户和统一登录地址支持自动识别、自定义及恢复默认，两处入口配置同步生效。

首次导入遇到入口配置提示，请查看 [导入说明](import-guide.md)；遇到加密密钥权限提示，请查看 [处理方法](import-key-permissions.md)。
