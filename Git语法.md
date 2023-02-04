# 目录
&emsp;&emsp;&emsp;&emsp;[一、配置相关](#1)  
&emsp;&emsp;&emsp;&emsp;[二、本地仓库相关](#2)  
&emsp;&emsp;&emsp;&emsp;[三、远程仓库相关](#3)  
&emsp;&emsp;&emsp;&emsp;[四、 分支相关](#4)  
&emsp;&emsp;&emsp;&emsp;[五、 提交历史相关](#5)  
&emsp;&emsp;&emsp;&emsp;[六、 标签相关](#6)  
&emsp;&emsp;&emsp;&emsp;[七、 冲突相关](#7)  
&emsp;&emsp;&emsp;&emsp;[八、 其他](#8)  


## 一、配置相关<span id="1">
		1. 查看git的配置文件列表: git config --list --show-origin
		2. 修改用户名:  git config --global user.name  用户名
		3. 修改邮箱: git config --global user.email 邮箱地址
		4. 配置编辑器: git config --global core.editor "编辑器地址 -multiInst -notabbar -nosession -noPlugin"
		5. 设置别名: git config --global alias.co checkout
## 二、本地仓库相关<span id="2">
		1. 初始化仓库: git init
		2. 检查当前文件状态: git status
		3. 添加追踪文件或将已经跟踪的文件放到暂存区: git add 文件名
		4. 启动编辑器编辑提交修改到仓库: git commit
		5. 快速提交到本地仓库: git commit -am 提交信息
		6. 修改上一个commit的描述: git commit -amend
		7. 重新提交第一个commit: git update-ref -d HEAD
		8. 还原某一个commit的修改: git revert commit-id
		9. 回到某个commit的状态,并删除后面的commit: 
			1. 重置暂存区,工作区不会被更改: git reset --mixed HEAD^
			2. 回退至三个版本之前,只回退了commit的信息,暂存区和工作区与回退之前保持一致: git reset --soft HEAD~3
			3. 彻底回退到指定commit-id的状态,暂存区和工作区也会变为指定commit-id版本的内容: git reset --hard commit-id
		10. 忽略文件: cat .gitignore 正则表达式
		11. 取消跟踪暂存区的文件: git rm 文件名
		12. 取消跟踪仓库中的文件: git rm --cached 文件名
		13. 给文件重命名: git mv 旧名字 新名字
		14. 取消文件的暂存: git reset HEAD 文件名
		15. 取消对文件的所有修改: git checkout --文件名
		16. 放弃工作区的修改: git checkout 文件名
		17. 放弃所有修改: git checkout .
		18. 存储当前的修改,但不用提交commit: git stash
		19. 保存当前状态,包括untracked的文件: git stash -u
		20. 展示所有stashes: git stash list
		21. 回到某个stash的状态: git stash apply stash@{n}
		22. 回到最后一个stash的状态,并删除这个stash: git stash pop
		23. 删除所有的stash: git stash clear
		24. 展示所有tracked的文件: git ls-files -t
		25. 展示所有untracked的文件: git ls-files --others
		26. 展示所有忽略的文件: git ls-files --others -i --exclude-standard
## 三、远程仓库相关<span id="3">
		1. 克隆远程仓库并重命名: git clone 远程仓库地址 新的仓库名
		2. 列出所有远程仓库: git remote
		3. 查看远程仓库: git remote 仓库名
		4. 添加一个新的远程仓库,并重命名: git remote add 名字 仓库地址
		5. 远程仓库的重命名:  git remote rename 旧名字 新名字
		6. 远程仓库的删除: git remote remove 仓库名
		7. 查看远程分支和本地分支的对应关系: git remote show 仓库名
		8. 抓取远程仓库并将远程分支合并到当前分支:  git pull
		9. 推送到远程仓库: git push 仓库名 分支
		10. 删除远程分支: git push origin --delete 远程分支名
		11. 从远程仓库更新本地库: git fetch 仓库名
		12. 抛弃本地所有的修改,回到远程仓库的状态: git reset --hard  仓库名/分支名
		13. 列出所有远程分支: git branch -r
## 四、 分支相关<span id="4">
		1. 分支创建: git branch 分支名
		2. 删除分支: git branch -d 分支名
		3. 查看已经合并的分支: git branch --merged
		4. 查看未合并的分支: git branch --no-merged
		5. 展示本地分支关联远程仓库的情况: git branch -vv
		6. 关联远程分支: git branch -u 仓库名/远程分支名
		7. 列出本地和远程分支: git branch -a
		8. 重命名本地分支: git branch -m 新的分支名
		9. 查看各个分支当前所指的对象: git log --oneline --decorate
		10. 快速切换到上一个分支: git checkout -
		11. 分支切换: git checkout 分支名
		12. 分支创建并切换: git checkout -b 分支名
		13. 合并分支: git merge 分支名
		14. 远程删除了分支本地也想删除: git remote prune 仓库名
		15. 把A分支的某一个commit,放到B分支上: git cherry-pick commit-id
## 五、 提交历史相关<span id="5">
		1. 查看提交历史: git log
		2. 按补丁格式显示每个提交引入的差异: git log -p
		3. 显示每次提交的文件修改统计信息: git log --stat
		4. 只显示 --stat 中最后的行数修改添加移除统计: git log --shortstat
	    5. 仅在提交信息后显示已修改的文件清单: git log --name-only
		6. 显示新增、修改、删除的文件清单: git log --name-status
		7. 仅显示 SHA-1 校验和所有 40 个字符中的前几个字符: git log --abbrev-commit
		8. 使用较短的相对时间而不是完整格式显示日期: git log --relative-date
		9. 在日志旁以 ASCII 图形显示分支与合并历史: git log --graph
		10. 使用其他格式显示历史提交信息。可用的选项包括oneline、short、full、fuller和format: git log --pretty
		11. 展示简化的commit历史:  git log --pretty=oneline --graph --decorate --all
		12. 格式化输出:  git log --pretty=format:"%h %s"
			* %H 提交的完整哈希值
			* %h 提交的简写哈希值
			* %T 树的完整哈希值
			* %t 树的简写哈希值
			* %P 父提交的完整哈希值
			* %p 父提交的简写哈希值
			* %an 作者名字
			* %ae 作者的电子邮件地址
			* %ad 作者修订日期（可以用 --date=选项 来定制格式）
			* %ar 作者修订日期，按多久以前的方式显示
			* %cn 提交者的名字
			* %ce 提交者的电子邮件地址
			* %cd 提交日期
			* %cr 提交日期（距今多长时间）
			* %s 提交说明
		13. 限定时间:  git log --since=2.weeks
		14. 仅显示最近的 n 条提交:  git log -<n>
		15. 仅显示指定时间之后的提交:  git log --since, --after
		16. 仅显示指定时间之前的提交:  git log --until, --before
		17. 仅显示作者匹配指定字符串的提交:  git log --author
		18. 仅显示提交者匹配指定字符串的提交:  git log --committer
	    19. 仅显示提交说明中包含指定字符串的提交:  git log --grep
		20. 仅显示添加或删除内容匹配指定字符串的提交:  git log -S
		21. 查看某段代码是谁写的: git blame 文件名
		22. 显示本地更新过HEAD的git命令记录: git reflog
		23. 查看两个星期内的改动: git whatchanged --since='2 weeks ago'
## 六、 标签相关<span id="6">
		1. 列出标签:  git tag  
		2. 附注标签: git tag -a 标签名 -m "标签描述"
		3. 查看标签信息: git show 标签名
		4. 轻量标签: git tag 标签名
		5. 补上标签: git tag -a 标签名 记录哈希码
		6. 删除标签: git tag -d 标签名
		7. 查看标签详细信息: git tag -ln
		8. 在指定的commit上打标签: git tag -a 标签名 -m "描述" commit-id
		9. 向远程仓库推送标签:git push 仓库名 标签名 
		10. 一次性推送所有标签到远程仓库: git push 仓库名 --tags
		11. 从远程仓库删除标签: git push 仓库名 --delete tag 标签名
		12. 查看标签的文件属性: git checkout 标签名
		13. 切回到某个标签: git checkout -b 分支名 标签名
		14. 展示当前分支的最近的标签: git describe --tags --abbrev=0
## 七、 冲突相关<span id="7">
		1. 查看工作目录和暂存区文件的区别: git diff
		2. 查看暂存区和仓库中文件的区别: git diff  --cached
		3. 展示工作区的冲突文件列表: git diff --name-only --diff-filter=U
		4. 展示本地仓库中任意两个commit之间的文件变动: git diff commit1-id commit2-id
		5. 输出工作区、暂存区、本地最近的版本不同: git diff HEAD
## 八、 其他<span id="8">
		1. 获得指定关键字的帮助信息: git help 关键字
		2. 展示帮助信息: git help -g