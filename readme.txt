
GIT本地新建分支并提交到远程仓库
1.建立本地仓库

    查看当前项目根目录中有没有 .git文件（隐藏文件），如果没有，右键->Git bash here ，然后输入命令git init建立本地仓库

git init
2.将代码提交到本地仓库

git add .
git commit -m "new branch commit"
3.在本地仓库中建立一个与远程仓库的别名，以便之后提交代码而不是每次都要输入远程仓库地址。指令结尾是git的仓库地址，我使用的是SSH连接方式

git remote add origin git@XX.XX.XX.12:gyjia/hotcodeserver.git 
4.此时我要把本地的代码提交的远程仓库上，步骤如下

    1）首先要建立本地的分支，并切换到该分支上（本地建立完分支，默认是在master分支上）

git branch hello_git_branch
git checkout hello_git_branch
    2）push到远程仓库上面

git push origin hello_git_branch
        由于刚才我们为远程仓库起了一个别名，那么这里就可以使用别名origin调用。

        这里的含义是将hello_git_branch这个分支提交到远程仓库上面。如果远程仓库没有这个分支，那么也会新建一个该分支。

        还有一种方法，可以指定提交到远程仓库的某个分支上。如下，是将hello_git_branch分支提交到远程仓库的master上面

git push origin hello_git_branch:master
拓展：

如果本地当前是在hello_git_branch分支上面，此时想把远程仓库的master与我的hello_git_branch分支合并（merge），可以使用如下命令:

git pull origin hello_git_branch:master
如果您使用如下指令，含义就是将远程仓库的master分支合并下来。如果本地没有master分支，那么本地就新建一个master分支


