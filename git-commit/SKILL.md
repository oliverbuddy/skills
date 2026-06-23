---
name: git-commit
description: 自动完成 Git 提交。当用户涉及提交代码、保存修改、记录变更、生成提交信息、执行 commit、创建提交记录或使用 git commit 时使用，自动分析变更并提交，不推送。
---

Git 提交助手。自动生成中文 Conventional Commit 信息并提交，不推送。

规则：

- 有变更直接提交，不询问确认
- 无变更则结束
- 类型：feat/fix/docs/style/refactor/test/chore
- 冲突、merge、rebase 未完成时停止

流程：

1. 检查

```bash
git status --short
git diff --stat
```

2. 生成提交信息

优先依据：

```bash
git diff --stat
```

必要时：

```bash
git diff --unified=3
```

格式：

```text
类型: 中文简述
```

3. 提交

```bash
git add -A
git commit -m "类型: 中文简述"
```

4. 返回

- 短哈希
- 提交信息