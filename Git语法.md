# 一、配置相关
		1. 查看git的配置文件列表：git config --list --show-origin
		2. 修改用户名： git config --global user.name "用户名"
		3. 修改邮箱: git config --global user.email 邮箱地址
		4. 配置编辑器：git config --global core.editor "'编辑器地址 -multiInst -notabbar -nosession -noPlugin"
# 二、 帮助相关
		1. 获得指定关键字的帮助信息：git help 关键字
# 三、本地仓库相关
		1. 初始化仓库：git init
		2. 添加全部追踪文件或将全部已经跟踪的文件放到暂存区：git add *
		3. 快速提交到本地仓库：git commit -am "提交信息"
		4. 启动编辑器编辑提交修改到仓库：git commit
		5. 重新提交刚刚提交过的修改：git commit -amend
		6. 检查当前文件状态：git status
		7. 忽略文件：cat .gitignore 正则表达式
		8. 取消跟踪暂存区的文件：git rm 文件名
		9. 取消跟踪仓库中的文件：git rm --cached 文件名
		10. 给文件重命名：git mv 旧名字 新名字
		11. 取消文件的暂存：git reset HEAD 文件名
		12. 取消对文件的所有修改：git checkout --文件名
# 四、远程仓库相关
		1. 克隆远程仓库并重命名：git clone 远程仓库地址 新的仓库名
		2. 查看远程仓库：git remote 仓库名
		3. 添加一个新的远程仓库,并重命名：git remote add 名字 仓库地址
		4. 从远程仓库更新本地库：git fetch 仓库名
		5. 抓取远程仓库并将远程分支合并到当前分支： git pull
		6. 推送到远程仓库：git push 仓库名 分支
		7. 查看某个远程仓库：git remote show 仓库名
		8. 远程仓库的重命名： git remote rename 旧名字 新名字
		9. 远程仓库的删除：git remote remove 仓库名  
# 五、 对比相关
		1. 查看工作目录和暂存区文件的区别：git diff
		2. 查看暂存区和仓库中文件的区别：git diff  --staged
# 六、 提交历史相关
		1. 查看提交历史：git log
		2. 按补丁格式显示每个提交引入的差异: git log -p
		3. 显示每次提交的文件修改统计信息: git log --stat
		4. 只显示 --stat 中最后的行数修改添加移除统计: git log --shortstat
	    5. 仅在提交信息后显示已修改的文件清单: git log --name-only
		6. 显示新增、修改、删除的文件清单: git log --name-status
		7. 仅显示 SHA-1 校验和所有 40 个字符中的前几个字符: git log --abbrev-commit
		8. 使用较短的相对时间而不是完整格式显示日期: git log --relative-date
		9. 在日志旁以 ASCII 图形显示分支与合并历史: git log --graph
		10. 使用其他格式显示历史提交信息。可用的选项包括oneline、short、full、fuller和format: git log --pretty
		11. 在一行中显示一条历史记录： git log --oneline
		12. 格式化输出： git log --pretty=format:"%h %s"
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
		13. 限定时间： git log --since=2.weeks
		14. 仅显示最近的 n 条提交： git log -<n>
		15. 仅显示指定时间之后的提交： git log --since, --after
		16. 仅显示指定时间之前的提交： git log --until, --before
		17. 仅显示作者匹配指定字符串的提交： git log --author
		18. 仅显示提交者匹配指定字符串的提交： git log --committer
	    19. 仅显示提交说明中包含指定字符串的提交： git log --grep
		20. 仅显示添加或删除内容匹配指定字符串的提交： git log -S
 # 七、 标签相关
		1. 列出标签： git tag  
		2. 附注标签：git tag -a v1.4 -m "my version 1.4"  
		3. 查看标签信息：git show v1.4  
		4. 轻量标签：git tag v1.4-lw  
		5. 补上标签：git tag -a v1.2 9fceb02  
		6. 向远程仓库推送标签：git push origin v1.5  --tags推送所有的标签  
		7. 删除标签：git tag -d v1.4-lw  
		8. 从远程仓库删除标签：git push origin :refs/tags/v1.4-lw  
		9. 查看标签的文件属性：git checkout 2.0.0  
# 八、 分支相关
		1. 别名：git config --global alias.co checkout  
		2. 分支创建：git branch testing  
		3. 查看各个分支当前所指的对象：git log --oneline --decorate  
		4. 分支切换：git checkout testing -b创建并切换  
		5. 合并分支：git merge hotfix  
		6. 删除分支：git branch -d hotfix  
		7. 已经合并的分支：git branch --merged或--no-merged还没合并的分支  
