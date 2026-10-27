# 萌卡NT用户系统

萌卡 NT 用户管理插件，提供 QQ 管理、商品套餐、用户等级、余额与佣金、支付、卡密、提现及分站功能。

## 下载

当前版本：**3.0.13**，最低框架版本：**3.0.2**。本版不兼容框架 2.x。

查看 [最新更新日志](release-notes/release-notes-v3.0.13.md) 或 [历史版本说明](release-notes/README.md)，从 [GitHub Release](https://github.com/Carlor-Official/Mengka-User-System/releases/tag/v3.0.13) 下载对应系统的安装包。

| 系统 | 安装包 |
| --- | --- |
| Windows AMD64 | `mengka-user-system-3.0.13-managed-native-windows-amd64.zip` |
| Linux AMD64 | `mengka-user-system-3.0.13-managed-native-linux-amd64.tar.gz` |
| Linux ARM64 | `mengka-user-system-3.0.13-managed-native-linux-arm64.tar.gz` |

## 安装与更新

- 先将框架升级至 3.0.2 或更新版本，再在「插件 → 插件导入」上传对应系统的安装包。
- 正常运行的插件可进入「系统设置 → 检查版本更新」在线更新。
- 旧插件无法启动时，直接在框架导入新版安装包并保留原数据，无需先卸载；导入后若显示已停止，点击启动。
- 升级前备份完整数据目录和主密钥，导入更新时保留原数据。
- 旧 2.x 版本需先完成数据迁移，不能直接覆盖升级。
- 升级后旧 QQ 记录若显示“待核对”，在管理端选择对应的当前协议账号，通过“核对迁移绑定”恢复关联，用户与业务历史保留。
- Linux 系统要求 GLIBC 2.28 及以上。

## 使用说明

用户通过框架 Web 地址下的 `/user/` 直接访问，无需先登录框架。域名反向代理应指向框架 Web 服务，不能指向插件管理网关。管理员可从框架打开管理端，也可使用框架管理员账号登录。

3.0.13 适配框架 3.0.2 的账号和等级任务管理，修复短信确认、免费体验授权同步与手机菜单，管理员可在账号配置中生成随机指纹。普通编辑保留原有指纹及登录缓存。

首次导入遇到入口配置提示，请查看 [导入说明](import-guide.md)；遇到加密密钥权限提示，请查看 [处理方法](import-key-permissions.md)。
