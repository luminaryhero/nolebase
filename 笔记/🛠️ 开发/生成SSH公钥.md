---
tags:
  - ssh公钥
status: 已完成
---
# 生成SSH公钥

1. **打开终端**（Linux/macOS）或者 **Git Bash**（Windows）。

2. **使用 ssh-keygen 命令生成 SSH 密钥对**。在终端或 Git Bash 中输入以下命令：
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```
按照提示完成三次回车，即可生成 ssh key。通过查看 `~/.ssh/id_ed25519.pub` 文件内容，获取到你的 public key

3. **获取生成的 SSH 公钥**。可以使用以下命令查看生成的 SSH 公钥内容：
```bash
cat ~/.ssh/id_rsa.pub
```

4. **使用 SSH 公钥**。将复制的 SSH 公钥粘贴到需要使用 SSH 认证的地方，例如远程服务器的 `~/.ssh/authorized_keys` 文件中，或者添加到代码托管平台（如 GitHub、GitLab）的 SSH 设置中。