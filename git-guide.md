# Git 常用命令指南

## 一、配置与查看

| 命令 | 作用 |
|------|------|
| `git remote` | 列出远程仓库名称 |
| `git remote -v` | 显示远程仓库详细地址（fetch/push URL） |
| `git branch` | 列出所有本地分支，`*` 标记当前分支 |
| `git status` | 查看当前工作区状态（哪些文件被修改/暂存） |
| `git log` | 查看提交历史 |

## 二、分支操作

| 命令 | 作用 |
|------|------|
| `git checkout <分支名>` | 切换到指定分支 |
| `git checkout -b <新分支名>` | 创建并切换到新分支 |
| `git checkout -b <本地分支> origin/<远程分支>` | 基于远程分支创建本地分支并切换 |

## 三、日常三步曲

```bash
git add .              # 将所有修改添加到暂存区
git commit -m "说明"   # 提交到本地仓库
git push               # 推送到远程仓库
```

- `git add <文件名>` 可以只暂存指定文件
- `git commit -m` 的 `-m` 是 message 的意思，后面跟提交说明
- 不加 `-m` 会打开编辑器写提交信息

## 四、拉取更新

| 命令 | 作用 |
|------|------|
| `git pull` | 从远程仓库拉取最新代码并合并到当前分支 |

## 五、整体工作流程

```
拉代码 → 改代码 → 暂存 → 提交 → 推送
 pull     编辑     add   commit   push
```

## 六、常见问题

1. **`git pull` 报错 "no such ref was fetched"** — 远程还没有该分支，先 push 一次即可。
2. **`git commit` 打开了编辑器** — 没加 `-m` 参数，建议始终用 `git commit -m "说明"`。
3. **`git push` 显示 "Everything up-to-date"** — 远程已经是最新的，无需推送。
4. **`nothing to commit, working tree clean`** — 没有修改过的文件，无法提交。
