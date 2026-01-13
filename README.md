# -
team-project

Git获取代码指南👇
点击<>Code,复制HTTP链接
打开本地终端，进入你想存放代码的文件夹（如 cd Desktop/项目文件夹）
执行克隆命令：git clone 复制的HTTPS链接



Git提交代码指南👇
在本地代码文件夹打开cmd命令行 -> cd 文件夹名
确保修改代码经过测试无误后提交

# 1. 查看修改状态（可选，确认哪些文件改了）
git status

# 2. 暂存所有修改的文件（. 表示所有，也可以指定文件名如 git add main.py）
git add .

# 3. 提交修改，写清楚修改说明
git commit -m "新增main.py，实现登录功能"

# 4. 推送到 GitHub 远程仓库
git push origin main


拉取别人的最新提交的代码👇
进入本地仓库文件夹；
执行拉取命令：git pull origin main
如果拉取时提示「冲突」（比如你和别人改了同一个文件的同一行），需要先解决冲突（修改文件，保留正确内容），再重新提交推送。


多人协作时最容易遇到「代码冲突」，这里给最简单的解决方法：
执行 git pull origin main 后，Git 会提示冲突的文件（如 main.py）；
打开冲突文件，会看到类似这样的标记：

<<<<<<< HEAD
# 你本地修改的代码
print("我的代码")
=======
# 别人推送的代码
print("团队成员的代码")
>>>>>>> 一串字符

删除冲突标记（<<<<<<< HEAD、=======、>>>>>> 一串字符），修改成最终要保留的代码（比如合并双方的逻辑）；
重新提交并推送：
git add .
git commit -m "解决main.py的代码冲突"
git push origin main
