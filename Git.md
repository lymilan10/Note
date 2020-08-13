### Git

#### Git 全局配置

git remote add origin https://github.com/lymilan10/vue-jingdong.git

git push -u origin dev

#### 创建Git仓库

mkdir wap  //新建文件夹

cd wap

##### 工作目录，.git 所在的目录，本地仓库 

##### 初始化生成 .git 文件，里面有index和HEAD文件

##### HEAD指向最新放入仓库的版本

git init //

##### 新创建的文件要添加到暂存区，只有在暂存区的文件，本地仓库才会追踪它的变化

git add . //添加目录下的所有文件

##### 暂存区文件提交到本地仓库

git commit -m "修改记录"

git remote add origin https://git.oschina.net/name/package.git //远程仓库地址

#### 列出本地分支和远程分支

git branch -a 

#### 列出远程分支

git branch -r

#### 删除远程分支

git branch -d -r “分支名”

#### 创建本地分支

git branch develop

#### 删除本地分支

git branch -d "分支名"

#### 

