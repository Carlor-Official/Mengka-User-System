# 萌卡NT用户系统

萌卡 NT 用户管理插件，提供 QQ 管理、商品套餐、用户等级、余额与佣金、支付、卡密、提现及分站功能。

## 下载

当前版本：**3.0.6**，最低框架版本：**2.5.3**。

查看 [更新日志](release-notes-v3.0.6.md)，从 [GitHub Release](https://github.com/Carlor-Official/Mengka-User-System/releases/tag/v3.0.6) 下载对应系统的安装包。

| 系统 | 安装包 |
| --- | --- |
| Windows AMD64 | `mengka-user-system-3.0.6-managed-native-windows-amd64.zip` |
| Linux AMD64 | `mengka-user-system-3.0.6-managed-native-linux-amd64.tar.gz` |
| Linux ARM64 | `mengka-user-system-3.0.6-managed-native-linux-arm64.tar.gz` |

## 安装与更新

- 在框架「插件 → 插件导入」上传对应系统的安装包。
- 已安装 3.0.4、3.0.5 可进入插件「系统设置 → 检查版本更新」在线更新。
- 升级前备份完整数据目录和主密钥，导入更新时保留原数据。
- 旧 2.x 版本需先完成数据迁移，不能直接覆盖升级。
- Linux 系统要求 GLIBC 2.28 及以上。

## 使用说明

用户通过框架地址下的 `/user/` 访问。管理员可从框架打开管理端，也可使用框架管理员账号登录。

3.0.6 支持零元商品免费领取、按 QQ 限购一次，以及分类自定义卡密。免费体验在登录成功后开始计时。

首次导入遇到入口配置提示，请查看 [导入说明](release-notes-v3.0.1.md#首次导入提示入口未配置)；遇到加密密钥权限提示，请查看 [处理方法](import-key-permissions.md)。
