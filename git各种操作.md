1. 查看git的配置文件列表：git config --list --show-origin  
2. 修改用户名和邮箱：git config --global user.name "John Doe"  
                    git config --global user.email xx@xx.com
3. 配置编辑器：git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe' -multiInst -notabbar -nosession -noPlugin"  
4. 查看配置信息：git config --list  
5. 获得指定关键字的帮助：git help verb  
6. 初始化仓库：git init  
7. 添加追踪文件或将已经跟踪的文件放到暂存区：git add /*跟踪全部  
8. 快速提交到本地仓库：git commit -m 'initial project version'  
9. 克隆数据库并指定名字：git clone https://github.com/libgit2/libgit2 mylibgit  
10. 检查当前文件状态：git status    -s紧凑的输出
11. 忽略以.o结尾的文件：cat .gitignore /*.o   
12. 查看工作目录和暂存区文件区别：git diff    --staged比较暂存区和仓库中文件的区别  
13. 启动编辑器编辑提交修改到仓库：git commit    -am "message"直接将修改过的文件提交 --amend 重新提交  
14. 取消跟踪暂存区的文件：git rm    --cached从仓库中取消跟踪     README.md  
15. 给文件重命名：git mv README.md README  
16. 查看提交历史：git log    
	* -p 按补丁格式显示每个提交引入的差异。  
	* --stat 显示每次提交的文件修改统计信息。  
	* --shortstat 只显示 --stat 中最后的行数修改添加移除统计。  
        * --name-only 仅在提交信息后显示已修改的文件清单。  
	* --name-status 显示新增、修改、删除的文件清单。  
	* --abbrev-commit 仅显示 SHA-1 校验和所有 40 个字符中的前几个字符。  
	* --relative-date 使用较短的相对时间而不是完整格式显示日期（比如“2 weeks ago”）。  
	* --graph 在日志旁以 ASCII 图形显示分支与合并历史。  
	* --pretty 使用其他格式显示历史提交信息。可用的选项包括 oneline、short、full、fuller 和 format（用来定义自己的格式）。  
	* --oneline   --pretty=oneline --abbrev-commit 合用的简写。  
	* --pretty=format:"%h %s" 格式化输出  
	* --since=2.weeks 限定时间  
	* -<n> 仅显示最近的 n 条提交。  
	* --since, --after 仅显示指定时间之后的提交。  
	* --until, --before 仅显示指定时间之前的提交。  
	* --author 仅显示作者匹配指定字符串的提交。  
	* --committer 仅显示提交者匹配指定字符串的提交。  
        * --grep 仅显示提交说明中包含指定字符串的提交。  
	* -S 仅显示添加或删除内容匹配指定字符串的提交。  
	* format参数说明：  
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
17. 取消暂存：git reset HEAD CONTRIBUTING.md  
18. 取消对文件的所有修改：git checkout -- CONTRIBUTING.md  
19. 查看远程仓库：git remote 默认名字为origin  -v查看URL  
20. 添加一个新的远程 Git 仓库，同时指定一个方便使用的简写： git remote add shortname url  
21. 从远程仓库跟新本地库：git fetch origin  
22. 自动抓取后合并该远程分支到当前分支： git pull  
23. 推送到远程仓库：git push remote branch  
24. 查看某个远程仓库：git remote show remote  
25. 远程仓库的重命名： git remote rename pb origin  
25. 远程仓库的删除：git remote remove paul  
26. 列出标签： git tag  
27. 附注标签：git tag -a v1.4 -m "my version 1.4"  
28. 查看标签信息：git show v1.4  
29. 轻量标签：git tag v1.4-lw  
30. 补上标签：git tag -a v1.2 9fceb02  
31. 向远程仓库推送标签：git push origin v1.5  --tags推送所有的标签  
32. 删除标签：git tag -d v1.4-lw  
33. 从远程仓库删除标签：git push origin :refs/tags/v1.4-lw  
34. 查看标签的文件属性：git checkout 2.0.0  
35. 别名：git config --global alias.co checkout  
36. 分支创建：git branch testing  
37. 查看各个分支当前所指的对象：git log --oneline --decorate  
38. 分支切换：git checkout testing -b创建并切换  
39. 合并分支：git merge hotfix  
40. 删除分支：git branch -d hotfix  
41. 已经合并的分支：git branch --merged或--no-merged还没合并的分支  






























