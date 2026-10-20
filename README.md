# 免费节点每日抓取并邮件推送

GitHub Actions 每天自动抓取 [yy1588133/proxy-pool](https://github.com/yy1588133/proxy-pool) 的 Clash YAML 与 V2Ray 节点，并以邮件附件发送。

## 使用前配置

1. 在仓库 **Settings → Secrets and variables → Actions** 中添加以下 Secrets：
   - `MAIL_USERNAME`：163 邮箱完整地址（例如 `yourname@163.com`）
   - `MAIL_PASSWORD`：163 邮箱的 **SMTP 授权码**（不是登录密码）
     - 获取方式：登录 163 邮箱 → 设置 → POP3/SMTP/IMAP → 开启 SMTP 并生成授权码

2. 确认收件人地址已在工作流中设置（当前为 `hhz12321@163.com`）。如需修改，编辑 `.github/workflows/fetch-free-nodes.yml` 中的 `to` 字段。

## 运行方式

- 定时：每天北京时间 08:00 自动运行
- 手动：在 Actions 页面选择该工作流 → Run workflow

## 注意事项

- 免费节点不稳定，仅供临时使用。
- 如需添加更多节点源，在抓取步骤中追加 `curl` 即可。
- 邮件以附件形式发送 `nodes.txt`。
