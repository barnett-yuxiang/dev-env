# Git

git + ssh

## SSH

```bash
ssh-keygen -t ed25519 -C "<EMAIL>" -f ~/.ssh/id_ed25519_github
ssh-keygen -t ed25519 -C "<EMAIL>" -f ~/.ssh/id_ed25519_codeup
```

### `~/.ssh/config`

```shell
# GitHub
Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_github
    IdentitiesOnly yes
    AddKeysToAgent yes
    UseKeychain yes

# Alibaba Cloud Codeup
Host codeup.aliyun.com
    HostName codeup.aliyun.com
    User git
    IdentityFile ~/.ssh/id_ed25519_codeup
    IdentitiesOnly yes
    AddKeysToAgent yes
    UseKeychain yes

# 阿里云 ECS（广州），托管个人主页
Host website-guangzhou
    HostName <PUBLIC_IP>
    User root
    IdentityFile ~/.ssh/sophia-ssh.pem
    IdentitiesOnly yes
    Port 22
    ServerAliveInterval 60
    ServerAliveCountMax 10

# 阿里云 ECS（马来西亚），OpenClaw 节点
Host openclaw-malaysia
    HostName <PUBLIC_IP>
    User ecs-user
    IdentityFile ~/.ssh/kamakura_claw-ssh.pem
    IdentitiesOnly yes
    Port 22
    ServerAliveInterval 60
    ServerAliveCountMax 10
```

- `IdentitiesOnly yes`：只用指定的 key，避免 agent 里其它 key 抢先认证失败。
- `AddKeysToAgent` / `UseKeychain`：macOS 专有，从钥匙串取 passphrase 并自动加入 agent。
- `ServerAliveInterval 60`：远程主机保活，防止空闲断连。

## 常用命令

### 1. 清理仓库

```bash
# 看仓库占了多大
git count-objects -vH

# 打包松散对象、清掉不可达对象
git gc

# 更彻底（慢，偶尔跑一次就行）
git gc --aggressive --prune=now
```

### 2. 按更新时间列出分支

```bash
git for-each-ref --sort=-committerdate refs/heads/ refs/remotes/ \
  --format='%(committerdate:relative)|%(refname:short)|%(authorname)|%(contents:subject)' \
  | column -t -s'|'
```
