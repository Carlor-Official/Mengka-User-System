# 萌卡用户系统插件 v1.0.5

本版本是 v1.0.4 的当前契约修正版。v1.0.4 已产生下载，因此不覆盖同版本资产，使用新版本明确区分最终构建。

## 修复内容

- 账号离线通知设置只读取和提交框架 2.0.2 的 `offlineEnabled` 字段，删除旧 `emailEnabled` 回退逻辑。
- 外发包重新从最终私有源码构建，前端保持生产压缩且禁止 source map，服务端封装为 V8 字节码单体程序。
- Windows AMD64、Linux AMD64 与 Linux ARM64 包均重新执行源码防泄漏白名单审计和运行验证。

## 使用要求

- 必须配合萌卡 NT 2.0.2 使用。
- 服务配置不使用 `system_management`、`allowed_actions` 或旧 action/字段别名。
- 离线通知请求使用 `offlineEnabled`，旧 `emailEnabled` 不再受支持。

## 升级说明

从 v1.0.4 升级前，先停止插件并完整备份 `config.yaml` 与 `data` 目录。替换程序文件后保留原配置和数据库，再启动 v1.0.5。

外发包只包含压缩、去符号并封装为 V8 字节码的单体运行程序及必要部署文件；不包含 TypeScript/Vue 源码、源码映射、`src`、`dist`、`node_modules`、独立 Node.js 环境、数据库、运行配置、日志、密钥或 Git 元数据。
