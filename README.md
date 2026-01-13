# -
team-project

第三步：本地克隆仓库（把远程仓库拉到自己电脑）
协作成员（包括你自己）需要先把 GitHub 上的仓库「复制」到本地，才能修改代码。
回到仓库主页，点击绿色的「<> Code」按钮，复制 HTTPS 链接（如 https://github.com/你的用户名/team-project.git）；
打开本地终端，进入你想存放代码的文件夹（如 cd Desktop/项目文件夹）；
执行克隆命令：
bash
运行
git clone 复制的HTTPS链接
# 示例：git clone https://github.com/zhangsan/team-project.git
克隆完成后，本地会出现和仓库同名的文件夹，里面就是仓库的所有文件。
第四步：本地修改代码并推送到 GitHub（共享你的修改）
这是核心步骤，把你本地写的代码同步到远程仓库，让团队成员能看到。
进入本地仓库文件夹（如 cd team-project）；
本地修改 / 新增代码（比如新建 main.py，写几行代码）；
执行 Git 命令，把修改推送到 GitHub：
bash
运行
# 1. 查看修改状态（可选，确认哪些文件改了）
git status

# 2. 暂存所有修改的文件（. 表示所有，也可以指定文件名如 git add main.py）
git add .

# 3. 提交修改，写清楚修改说明（必须，方便团队知道你改了什么）
git commit -m "新增main.py，实现登录功能"

# 4. 推送到 GitHub 远程仓库（main 是默认分支名，也可能是 master）
git push origin main
如果是第一次推送，可能需要输入 GitHub 用户名和密码（或用 Token，GitHub 现在推荐 Token 登录，可在 GitHub 设置里生成）。
第五步：拉取团队成员的最新代码（获取别人的修改）
团队成员修改并推送代码后，你需要把远程的最新代码拉到本地，保证自己的代码是最新的。
进入本地仓库文件夹；
执行拉取命令：
bash
运行
git pull origin main
如果拉取时提示「冲突」（比如你和别人改了同一个文件的同一行），需要先解决冲突（修改文件，保留正确内容），再重新提交推送。
第六步：解决代码冲突（协作中常见问题）
多人协作时最容易遇到「代码冲突」，这里给新手最简单的解决方法：
执行 git pull origin main 后，Git 会提示冲突的文件（如 main.py）；
打开冲突文件，会看到类似这样的标记：
python
运行
<<<<<<< HEAD
# 你本地修改的代码
print("我的代码")
=======
# 别人推送的代码
print("团队成员的代码")
>>>>>>> 一串字符
删除冲突标记（<<<<<<< HEAD、=======、>>>>>> 一串字符），修改成最终要保留的代码（比如合并双方的逻辑）；
重新提交并推送：
bash
运行
git add .
git commit -m "解决main.py的代码冲突"
git push origin main
