# 📐 数学建模资料仓库

## ⚠️ 注意事项（必读！！！）

1. **不要直接在 `main` 分支上修改任何文件！** `main` 分支仅由编程手统一整合后提交。
2. **每个人只在自己对应的分支上工作：**
   - 编程手 → `coding` 分支
   - 建模手 → `model` 分支
   - 论文手 → `thesis` 分支
3. **不要直接往最终版目录下放东西。** 每个人找到自己的文件夹，把资料放进自己的文件夹里。
4. **每次开始工作前，先 `git pull` 拉取最新内容，避免冲突。**
5. **提交信息要写清楚做了什么**，不要写"更新"、"修改"这种模糊的描述。
6. **最终由编程手统一整合各分支资料，合并到 `main` 分支后提交。**

---

## 🏗️ 仓库分支说明

| 分支名 | 用途 | 负责人 |
|--------|------|--------|
| `main` | 最终整合版本（不要直接修改） | 编程手整合 |
| `coding` | 编程相关代码与资料 | 编程手 |
| `model` | 建模思路、数学推导与模型文件 | 建模手 |
| `thesis` | 论文撰写、排版与参考文献 | 论文手 |

---

## 🚀 首次使用：克隆仓库

三个人都需要先把仓库克隆到本地（只需执行一次）：

```bash
git clone https://github.com/MitsukiCoffee/mathmodel.git
cd mathmodel
```

克隆完成后，切换到自己的分支即可开始工作（见下方各角色指南）。

---

## 👨‍💻 编程手操作指南（`coding` 分支）

### 1. 切换到自己的分支

```bash
git checkout coding
```

### 2. 日常工作流程

```bash
# ① 每次开始工作前，先拉取最新内容
git pull origin coding

# ② 在自己的文件夹中编写代码、整理资料
# ...正常工作...

# ③ 查看修改了哪些文件
git status

# ④ 添加修改的文件
git add .

# ⑤ 提交修改（写清楚做了什么）
git commit -m "添加了XX模型的Python求解代码"

# ⑥ 推送到远程仓库
git push origin coding
```

### 3. 整合各分支到 `main`（仅编程手操作）

比赛最终提交前，编程手需要将各分支的内容合并到 `main`：

```bash
# ① 切换到 main 分支
git checkout main

# ② 拉取最新的 main
git pull origin main

# ③ 合并建模手的内容
git merge model

# ④ 合并论文手的内容
git merge thesis

# ⑤ 合并自己的内容
git merge coding

# ⑥ 如果有冲突，手动解决后：
git add .
git commit -m "解决合并冲突"

# ⑦ 推送最终整合版本
git push origin main
```

> 💡 **提示：** 合并时如遇冲突，Git 会标记冲突文件，打开文件手动选择保留的内容即可。

---

## 📊 建模手操作指南（`model` 分支）

### 1. 切换到自己的分支

```bash
git checkout model
```

### 2. 日常工作流程

```bash
# ① 每次开始工作前，先拉取最新内容
git pull origin model

# ② 在自己的文件夹中整理建模思路、推导过程、模型文件等
# ...正常工作...

# ③ 查看修改了哪些文件
git status

# ④ 添加修改的文件
git add .

# ⑤ 提交修改（写清楚做了什么）
git commit -m "完成了问题一的灵敏度分析模型"

# ⑥ 推送到远程仓库
git push origin model
```

### 3. 建议存放的内容

- 数学模型推导文档（`.md` / `.pdf` / `.docx`）
- 建模思路与假设说明
- 模型参数与数据文件
- 模型验证与结果分析

---

## 📝 论文手操作指南（`thesis` 分支）

### 1. 切换到自己的分支

```bash
git checkout thesis
```

### 2. 日常工作流程

```bash
# ① 每次开始工作前，先拉取最新内容
git pull origin thesis

# ② 在自己的文件夹中撰写论文、整理参考文献等
# ...正常工作...

# ③ 查看修改了哪些文件
git status

# ④ 添加修改的文件
git add .

# ⑤ 提交修改（写清楚做了什么）
git commit -m "完成论文摘要和第一章引言部分"

# ⑥ 推送到远程仓库
git push origin thesis
```

### 3. 建议存放的内容

- 论文正文（`.tex` / `.docx`）
- 参考文献（`.bib` / `.pdf`）
- 论文中使用的图表
- 排版模板与格式文件

---

## 🔧 常用 Git 命令速查

| 命令 | 说明 |
|------|------|
| `git status` | 查看当前修改状态 |
| `git branch` | 查看所有分支（当前分支前有 `*`） |
| `git checkout 分支名` | 切换分支 |
| `git pull origin 分支名` | 拉取远程最新内容 |
| `git add .` | 添加所有修改的文件 |
| `git add 文件名` | 添加指定文件 |
| `git commit -m "说明"` | 提交修改并附带说明 |
| `git push origin 分支名` | 推送到远程仓库 |
| `git log --oneline -5` | 查看最近5条提交记录 |
| `git diff` | 查看未暂存的修改内容 |

---

## ❓ 常见问题

### Q: push 时提示被拒绝（rejected）怎么办？

说明远程有更新的内容，先拉取再推送：

```bash
git pull origin 你的分支名
# 解决可能的冲突后
git push origin 你的分支名
```

### Q: 不小心在错误的分支上修改了文件怎么办？

如果还没有提交，可以暂存修改并切换分支：

```bash
git stash            # 暂存当前修改
git checkout 正确的分支名
git stash pop        # 恢复暂存的修改
```

### Q: 如何查看自己当前在哪个分支？

```bash
git branch
```

带 `*` 号的就是当前分支。

---

> 📌 **仓库地址：** https://github.com/MitsukiCoffee/mathmodel.git