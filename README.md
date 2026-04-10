## 🛠 开发者协作规范 (Collaboration Guide)

为了确保代码对比（Diff）的准确性及仓库的整洁，请所有开发者在提交代码前务必遵循以下流程：

### 1. 环境准备与项目初始化
本仓库已配置标准 `.gitignore`。在开始开发前，请确保你的本地环境**绝不**将 `__pycache__`、`venv` 或 `.idea/.vscode` 提交至 Git 索引。

**如果你的分支出现了大量非代码文件的变动，请执行以下清理指令：**
```bash
# 移除已追踪的缓存文件（不会删除本地物理文件）
git rm -r --cached .
# 重新按照 .gitignore 规则添加文件
git add .
git commit -m "chore: 按照.gitignore规范清理仓库"
```

### 2. 标准协作流程：基于“共同祖先”开发
为避免出现“全量新增（All New Files）”的对比错误，请务必从主仓库派生分支，严禁在独立的本地仓库中自行 `git init` 后再强行合并。



**推荐操作步骤：**
1. **同步主仓库最新代码：**
   ```bash
   git checkout main
   git pull origin main
   ```
2. **创建功能分支：**
   ```bash
   git checkout -b feature-你的功能名
   ```
3. **开发并提交：**
   ```bash
   git add .
   git commit -m "feat: 描述你的改动"
   ```
4. **推送到远程：**
   ```bash
   git push origin feature-你的功能名
   ```
