# QStart 加密策略仓库

Mac 与 iPhone/iPad 的默认策略发布、同步仓库。

- 仓库：`hxfxjun/qstart_strategies`
- 分支：`main`
- 加密策略文件：`strategies/latest.enc.json`
- 公开配置清单：[qstart-cloud.json](qstart-cloud.json)

App 内已预置上述默认值；配置清单用于核对仓库约定。两端已有的自定义配置会保留。

## 首次发布与同步

1. 使用 Mac QStart 1.6.0，在设置的「GitHub · 加密策略发布」确认仓库和分支，设置并保存加密口令。写入可使用本机已登录的 gh，或具有该仓库 Contents 读写权限的 GitHub 令牌。
2. 在策略管理保存策略，点击「发布到 GitHub」，准备并确认发布。首次成功发布会创建 `strategies/latest.enc.json`；只有该文件存在后，iOS 才能同步策略。
3. 在 iPhone/iPad 设置中保存与 Mac 相同的加密口令。当前仓库公开，读取无需 GitHub 令牌。点击「从 GitHub 同步策略」。

此仓库仅保存客户端加密后的策略。口令、解密密钥、模型 API Key、执行主机令牌和账户数据不上传。策略使用 AES-256-GCM 认证加密；仓库、分支和文件路径参与认证，不能通过复制密文到其他仓库更改配置。

公开配置清单不包含策略内容，也不替代加密发布。客户端根据 App 内保存的仓库配置访问 GitHub，策略在本机解密。执行与通知仍需连接 Mac 或独立执行主机，GitHub 不运行生产策略。
