# filesystem-index-for-agents

# 仓库使用说明

---

## 0. 一句话

所有改动走分支 + PR。

---

## 1. 仓库基本事实

| 项 | 值 |
|---|---|
| 仓库 | `https://github.com/KG-Group-01/filesystem-index-for-agents` |
| 归属 | 组织 `KG-Group-01`（组员平权） |
| 默认分支 | `main`（唯一长期分支） |
| 规模 | 6 人 |

---

## 2. 现在生效的规则

| 规则 | 意味着什么 |
|---|---|
| **必须开 PR 才能进 `main`** | 你的改动必须先推到一个分支，再开 PR。直接推 `main` 会被拒 |
| **0 人批准即可合并** | 你自己就能合自己的 PR。 |
| **合并后自动删分支** | 合完你的远程分支就消失了 |

---

## 3. 流程示例

```bash
# 1. 第一次工作先clone仓库到本地,后续不需要
# git clone https://github.com/KG-Group-01/filesystem-index-for-agents.git
# cd filesystem-index-for-agents

# 2. 开工前先同步
git switch main && git pull

# 3. 开分支（命名：谁/干什么）
git switch -c w3/version-edges

# 4. 写东西，然后提交
git add <具体文件>          # 别用 git add -A 除非你确认过改了哪些
git commit -m "feat(w3): 建版本边"

# 5. 推分支（注意：推的是分支，不是 main）
git push -u origin w3/version-edges
```

6. 打开 GitHub，点 **Compare & pull request**，填模板
7. 等检查（有了 CI 之后），点 **Squash and merge**
8. 分支自动删除，回到第 3 步做下一件事

### 提交信息格式

```
类型(范围): 说明
```

类型用：`feat` / `fix` / `docs` / `eval` / `refactor` / `chore`等

例：

```
feat(w2): 扫盘支持排除规则
docs: 补充索引 schema 说明
eval(w5): 加三档基线对比脚本
```

---

## 4. 安全

仓库是公开的, 这三类东西**永远不进仓库**：

1. **密钥**：API key、token、cookie、`.env`、含 `mykey` 的文件
2. **真实语料**：别人的文件内容、任何授权目录里的实际数据
3. **个人绝对路径**：`/Users/xxx/...`、本机目录结构、带用户名的路径