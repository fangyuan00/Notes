# Git指令
### 根据commit id找到对应节点所属的分支和标签
```
git branch --contains commit
git tag --contains commit
```
### 关于git父提交
* Git中的特殊指针`HEAD`，指向当前所在的本地分支（本地分支的别名），`HEAD^`指向其父提交，`HEAD^^`指向其父提交的父提交。  
* 若`HEAD^`后面跟了数字，则`HEAD^1`为第一父提交，`HEAD^2`为第二父提交，该语法只有在合并分支时产生的提交中有效。  
  * 第一父提交为合并前当前分支的最后一次提交，第二父提交为被合并的分支的最后一次提交。  
* `HEAD~`后面也可以跟数字，`HEAD~1`为父提交，`HEAD~2`为父提交的父提交即祖父提交。 
#### 查看最新提交的更改内容
```
git show HEAD
```
#### 查看倒数第N条的提交
一般情况不会出错，但当存在有合并分支的提交时，则有风险。
```
git show HEAD~N
```
#### 打印最近N次提交的日志(correct)
```
git log -N
```
### git diff的4种命令
git分为**工作区**、**暂存区**、**对象区**。
1. 比较**工作区**与**暂存区**之间的差异
```
git diff
```
2. 比较**给定commit ID**与**工作区**的差异
```
git diff commit
```
3. 比较**暂存区**与给定**commit ID**的差异
```
git diff --cached commit
```
4. 比较指定的两次提交**commit1**与**commit2**的差异  
* 大概就是`commit2-commit1`的差异
```
git diff commit1 commit2
```
