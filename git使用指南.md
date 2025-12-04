# VSCode Git 使用指南

## 常用指令

- 初始化git仓库：`git init`

- 向仓库中添加文件：`git add [files]`

- 提交修改：`git commit -m "提交信息"`

- 链接远程仓库：

```bash
  git remote add origin https://github.com/{Username}/{repo_name}.git
  git branch -M main
  git push -u origin main
```

- 克隆远程仓库：`git clone [link]`

- 向远程仓库提交本地修改：`git push`

- 拉取远程仓库代码：`git pull`

- 切换分支：`git checkout [branch_name]`

- 合并分支：`git merge [branch_name]`

- 撤销提交（重置）：`git reset --soft/hard [commitID]`（将当前分支重置到指定 commitID。soft 会将 commitID 后的修改保留在暂存区，hard 则会直接丢弃这些修改，请谨慎使用）

- 撤销指定提交：`git revert [commitID]`（新建一个提交，用来撤销指定 commitID 所做的修改，不影响后续的其他提交）

## VSCode Git 可视化界面常用操作

### 初始化仓库

![初始化界面](fig/初始化界面.png)

点击左上角 Initialize Repository 即可在当前路径下新建一个 git 仓库，相当于 git init.

### 暂存

![暂存](fig/暂存.png)

![暂存效果](fig/暂存效果.png)

注：当暂存区存在文件时，提交时仅有暂存区的文件会被提交；暂存区为空时，VSCode 会询问是否提交未被暂存的文件（可通过设置令 VSCode 遇到该类情况不再询问，直接提交发生修改的所有文件）

### 提交（本地）

![提交（本地）1](fig/提交（本地）方法1.png)

在输入提交信息后点击 Commit 即可提交修改，或者先点击 Commit，之后会跳出填写提交信息的界面，填写内容后点击右上角的 "√" 即可提交修改

![提交（本地）2](fig/提交（本地）方法2.png)

### 向远程仓库提交

![向远程仓库提交](fig/向远程仓库提交.png)

点击 Sync Changes 即可

### 同步远程仓库信息

![同步远程仓库信息](fig/同步远程仓库信息.png)

点击 synchronize changes （首尾相接的箭头图标）即可

![拉取远程仓库更新](fig/拉取远程仓库更新.png)

点击 Pull 即可

### 分支管理

![分支管理1](fig/分支管理1.png)

- 分支切换：

  ![分支管理2](fig/分支管理2.png)

- 分支合并：

  ![分支合并](fig/分支合并.png)

- 分支合并冲突处理：

  ![分支合并冲突处理1](fig/分支合并冲突处理1.png)

  点击右下方 Resolve in Merge Editor 进入合并冲突处理界面

  ![分支合并冲突处理2](fig/分支合并冲突处理2.png)

  可以选择保留当前分支的版本还是引入将要合并进来的分支的版本

  ![分支合并冲突处理3](fig/分支合并冲突处理3.png)

  点击 Complete Merge 完成分支合并冲突处理

## 补充内容

- 如果不想让 git 追踪当前目录及子目录下的部分文件，可以编写 `.gitignore` 文件。

- 以上内容只是 git 完整功能的一小部分，在实际使用过程中如果遇到问题，建议向 AI 寻求帮助，对于 AI 给出的可能造成 git 记录丢失的操作，请保持谨慎。

- 一般来说，github 远程仓库上不建议存放太大的文件。