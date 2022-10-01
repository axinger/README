# 1.Mac命令

## 1.本地path配置

```text
#JDK 
#export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-9.0.1.jdk/Contents/Home
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_201.jdk/Contents/Home
export PATH=$PATH:$JAVA_HOME/bin
# JDK END

# go
# go 创建项目保存路径
export GOPATH=$HOME/Develop/go
# go sdk的目录
export GOROOT=/usr/local/go
# go END

#flutter 国内镜像
export PUB_HOSTED_URL=https://pub.flutter-io.cn
export FLUTTER_STORAGE_BASE_URL=https://storage.flutter-io.cn
export FLUTTER_HOME=$HOME/Develop/SDK/flutter
export PATH=$PATH:$FLUTTER_HOME/bin
# flutter END
```

## 2.命令

### 1.修改md5值

```
echo a >>
```

### 2.查看端口占用

```
lsof -i:8080
```

### 3.关闭端口

```
kill -9 PID 
```

### 4.查找文件命令

```
which       查看可执行文件的位置  命令只是根据PATH环境变量查找。
whereis    查看文件的位置 
locate       配 合数据库查看文件位置 
find          实际搜寻硬盘查询文件名称 
```

### 5.mac 终端修改用户名

```shell
sudo scutil --set HostName xx
```

### 6 修改侧边栏中文

```
1Desktop-桌面 touch ~/Desktop/.localized
2Documents-文稿 touch ~/Documents/.localized
3downloads-下载 touch ~/downloads/.localized
4Pictures-图片 touch ~/Pictures/.localized
5Music-音乐 touch ~/Music/.localized
6Movies-影片 touch ~/Movies/.localized 
```

## 3. shell终端

### 1.终端快捷键

```
清屏：command + k, 或者 Ctrl+l
终止当前进程：control + z
强制退出终端：command + q
清除正在输入的: Ctrl+u
```

## 4. 设置git代理

### 1.通用git

设置代理

```bash
git config --global http.proxy http://127.0.0.1:8001
```

取消代理

```bash
git config --global --unset http.proxy
git config --global --unset https.proxy
```

查看已有配置

```bash
git config --global -l
```

### 2 设置github代理

#### 1 ***http*** 、***https*** 方式

```bash
git config --global http.https://github.com.proxy http://127.0.0.1:8001
git config --global https.https://github.com.proxy https://127.0.0.1:8001
```

#### 2  SSH协议 sock5代理设置

```bash
git config --global http.https://github.com.proxy socks5://127.0.0.1:8001
git config --global https.https://github.com.proxy socks5://127.0.0.1:8001
```

#### 3 取消代理

```bash
git config --global --unset http.https://github.com.proxy
git config --global --unset https.https://github.com.proxy
```

# 2. homebrew

```
rvm是用来管理ruby的，ruby的其中一个“程序”叫rubygems，简称 gem，而用来管理项目 的gem的，叫bundle.完全是不同的东西，他们相同的只是都可以管理gem

bundle是rails框架里面安装Gemfile指定的各种库的工具
```

```
Homebrew国内如何自动安装（国内地址）

苹果电脑 常规安装脚本（推荐 完全体 几分钟安装完成）：

/bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"

苹果电脑 极速安装脚本（精简版 几秒钟安装完成）：

/bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)" speed
```

## 1 brew cask 拓展 安装mac app

### 1.搜索app,xx表示APP名称

```sh
brew install --cask 软件名
```

### 2.安装app

```sh
brew install xx --cask 失效
brew install --cask 软件名
```

### 3. 源,替换为中科大源

```
https://www.cnblogs.com/heycomputer/articles/12823788.html
```

```bash
# 替换各个源
$ git -C "$(brew --repo)" remote set-url origin https://mirrors.ustc.edu.cn/brew.git
$ git -C "$(brew --repo homebrew/core)" remote set-url origin https://mirrors.ustc.edu.cn/homebrew-core.git
$ git -C "$(brew --repo homebrew/cask)" remote set-url origin https://mirrors.ustc.edu.cn/homebrew-cask.git

# zsh 替换 brew bintray 镜像
$ echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.ustc.edu.cn/homebrew-bottles' >> ~/.zshrc
$ source ~/.zshrc

# bash 替换 brew bintray 镜像
$ echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.ustc.edu.cn/homebrew-bottles' >> ~/.bash_profile
$ source ~/.bash_profile

# 刷新源
$ brew update
```

### 4.重置为官方源

```shell
# 重置 brew.git 为官方源
$ git -C "$(brew --repo)" remote set-url origin https://github.com/Homebrew/brew.git

# 重置 homebrew-core.git 为官方源
$ git -C "$(brew --repo homebrew/core)" remote set-url origin https://github.com/Homebrew/homebrew-core.git

# 重置 homebrew-cask.git 为官方源
$ git -C "$(brew --repo homebrew/cask)" remote set-url origin https://github.com/Homebrew/homebrew-cask

# zsh 注释掉 HOMEBREW_BOTTLE_DOMAIN 配置
$ vi ~/.zshrc
# export HOMEBREW_BOTTLE_DOMAIN=xxxxxxxxx

# bash 注释掉 HOMEBREW_BOTTLE_DOMAIN 配置
$ vi ~/.bash_profile
# export HOMEBREW_BOTTLE_DOMAIN=xxxxxxxxx

# 刷新源
$ brew update
```

## 2 命令

```
brew search **  //查找某个软件包
brew list  //列出已经安装的软件的包
brew install ** //安装某个软件包,默认安装的是稳定版本
brew uninstall **//卸载某个软件的包
brew upgrade ** //更新某个软件包
brew info ** //查看指定软件包的说明
brew cache clean //清理缓存

搜索服务
brew search redis
查看安装位置
brew list redis
// 查看正在运行的服务
brew services list    
brew search xx
open /usr/local/bin/jmeter
nacos 启动
sh startup.sh -m standalone
// 启动
brew services start kafka
// 关闭
brew services stop kafka
// 重启
brew services restart kafka
启动
sh zkServer.sh start
停止脚本
sh zkServer.sh stop
sudo nginx
sudo nginx -s reload
sudo nginx -s quit
```

## 3 RMV 离线安装

```
上github下载rvm，https://github.com/rvm/rvm.git。
双击打开/bin/rvm-installer
    .../Users/ccy/.rvm/ is complete.
提示这个说明安装完成。
然后配置到.bash_profile
export PATH="/Users/ccy/.rvm/bin:$PATH"
终端输入：rvm
无-bash: rvm: command not found提示。

作者：molaoye
链接：https://www.jianshu.com/p/4fb2e0f44a65
来源：简书
```

# 3. cocopod使用

## 1 新建

```ruby
init pod
```

## 2 打开编辑

```ruby
open -a xcode podfile
```

## 3 加载

```ruby
pod install --verbose --no-repo-update
```

执行pod install时，提示如下信息：

The version of CocoaPods used to generate the lockfile (1.2.0.beta.1) is higher than the version of the current executable (1.1.1). Incompatibility issues may arise
解决方法：

执行：
命令更新资源库即可。

```ruby
pod repo update
```

## 4 注册 不要bb 表示注册过,登录

```ruby
pod trunk register aa@qq.com bb
```

## 5.制作cocopod库

### 1.制作

#### 1. 注册(登录)

```
pod trunk register liu_weixing@qq.com 'axinger' --description='阿星iOS'
```

#### 2. 查看自己的库

```
pod trunk me
```

#### 3. 删除仓库的库

```
pod trunk remove-owner AXFoundation liu_weixing@qq.com
```

#### 4. 创建库

```
pod lib create AXiOSKit
```

```sh
pod lib create xx --template-url=https://gitee.com/axinger/pod-template.git
```

#### 5.查看库信息

```
pod trunk info AXiOSKit
```

### 2.验证

```
说明：
(1)--verbose:表示显示全部的日志信息，建议加上这个，方便判断错误信息。
(2)--sources:如果我们在podspec里面依赖到一些私有的库之后，直接进行校验是会报错的提示找不到，这里加上我们的Spec仓库的地址告诉CocoaPods找不到的时候去哪里找。
(3)--allow-warnings:表示允许警告.
(4)--use-libraries:表示使用静态库或者是framework，这里主要是解决当我们依赖一些framework库后校验提示找不到库的时候用到。
```

#### 1 本地验证,只从本地验证你的pod能否通过验证。

```shell
pod lib lint --verbose --use-libraries --allow-warnings --skip-import-validation
--sources='https://gitee.com/axinger/AXCollectionObserve.git,https://gitee.com/mirrors/CocoaPods-Specs.git'
```

#### 2 远程验证,是从本地和远程验证你的pod能否通过验证。

```ruby
pod spec lint --use-libraries --verbose --skip-import-validation --allow-warnings
pod spec lint --use-libraries --allow-warnings --verbose --skip-import-validation

pod spec lint --allow-warnings --verbose
pod spec lint  --use-libraries --allow-warnings --verbose --skip-import-validation
```

## 3推送

```ruby
pod trunk push  --allow-warnings
pod trunk push  --allow-warnings --verbose --use-libraries
```

```
pod repo push 本地repo名 podspec名 --sources='私有仓库repo地址,https://github.com/CocoaPods/Specs'
```

cocopod 本地查找路径

```sh
find ~/.cocoapods/repos/master -iname xxx
```

进入对应的文件夹用以下命令

```sh
find gitee -iname xxx
```

或者

```sh
find Specs -iname xxx
```

## 4 删除本地搜索库

```sh
rm ~/Library/Caches/CocoaPods/search_index.json
```

```sh
sudo xattr -rd com.apple.quarantine /Applications/CleanMyMacX.app
```

****

分割线

```markdown
****
```

# 4.Xcode

## 4.1快捷键

```
    1.工程导航器:Command+1
    2.显示/隐藏导航器面板:Command+0
    3.显示/隐藏实用工具面板:Command+Option+0
    4.在辅助编辑器中打开文件:在项目导航器中选中文件执行Option+左键点击操作。
    5.搜索导航器(Find Navigator，也就是搜索):Command+Shift+F
    6.文件跳转栏:Control+6（键入方法/变量名+Enter跳转）
    7.快速打开: Command + Shift + O
    8.跳转栏和快速打开搜索输入快捷键
    9. 程序中(Objective-C或C++编写).h and .m文件间的快速切换: Control + Command + Up Arrow
    10.运行app: Command + R
    11.清除工程: Command + Shift + K
    12.构建应用程序: Command + B
    13.文档和参考: Command + Shift + 0 (Zero)
    14.清空控制台  Command  + k
    15.control+command+上, h,m文件切换
```

## 4.2控制台

```
    1. p命令：可以查看基本数据类型的值，如果查看对象的话，会返回对象的地址指针。p命令还可以接表达式。
    2. po命令：打印对象，与p命令类似。
    3. bt命令：打印线程的堆栈信息。bt all 是打印所有线程的堆栈信息。
    4. expr命令： expression 的简写，能够在调试时，动态的执行赋值表达式，同时打印出结果。我们可以在调试时，动态的修改变量的值，这在调试想要让应用执行异常路径（如执行某个else 情况）很有用。
    5. call命令：动态调用函数，在控制台执行该命令的，可以在不修改代码，不重新编译的情况下，修改界面上的视图。
    6. image命令：image list可以查看某一个地址对应的代码位置。除了 image list 还有 image add、image lookup等命令，当遇到crash 时，查看线程栈，只能看到栈帧的地址，使用 image lookup –address 地址 可以方便的定位到这个地址对应的代码行。
    7. x命令:查看地址，例如：x student
    8. x/4gx命令：打印4个16进制地址。x/4gx student
```

****

# 5.idea 快捷键

```
ctrl + h 查看类或接口的继承关系：
command+e 最近文件
^+cmd+e 最近代码
op+cmd+l 代码格式化
^+option + o 清除多余import
option command + ↔️ 最近位置
按shift两次 搜索文件名
查看所有方法 command + 7
VS Code 快捷键
格式化 shift +op+f 或者鼠标右键
```

# 7 shell语法

## 7.1 子串尽量用双引号

## 7.2 打印

```
echo 输出空字符＋空行
echo -n 输出空字符不加空行＝＝什么都不输出
echo -e 能够识别以\开头的一些特殊字符，详见man echo 
```

```shell
your_name='runoob'
str=" $your_name! \n"
echo -e $str
echo  $str
```

## 7.3 子串长度

```
${#}
```

```shell
str2="1234"
echo 子串长度: ${#str2} #输出 4
```

## 7.4 脚本

```shell
#!/bin/bash

#脚本所在目录
currentPath=$(dirname $0)
cd $currentPath
echo "当前路径: $(pwd)"

echo
echo "🐶 选择环境变量(输入序号,默认值0 release)"
# declare -A buildMap
is_itunes_on_1="release is_itunes_on:1"
buildMap=([0]="release" [1]=$is_itunes_on_1 [2]="test")

for key in ${!buildMap[@]}; do
    buildFormat="$buildFormat $key ${buildMap[$key]}, "
done
# 前景色：30黑 31红 32绿 33黄 34蓝 35紫 36青 37白
# 背景色：40黑 41红 42绿 43黄 44青 45蓝 46青 47白

#含有颜色
axLog() {
    # 所有参数 $*
    echo -e "\033[47;34m $* \033[0m"
    echo
}

# echo -e "\033[47;34m $buildFormat \033[0m"
# echo
axLog $buildFormat

read -p "请输入模式编号: " buildKey
# :- 默认值
buildKey=${buildKey:-0}
# 是否包含,判断是否为指定范围
[ "${buildMap[buildKey]}" ] || buildKey=0
# 取值
buildValue=${buildMap[buildKey]}
# echo 编译模式key: $buildKey
echo 编译模式value: $buildValue

echo
echo "🐶 输入版本号(默认值工程版本号)"
read -p "输入版本号: " version_number
# version_number=${version_number:-''}
echo 版本号是: $version_number

echo
echo "🐶 选择环境变量(输入序号,默认值0)"
envNumMap=(["0"]="生产" ["2"]="信通测试" ["8"]="润信通10030" ["10"]="润和测试")
for key in ${!envNumMap[@]}; do
    envNumFormat="$envNumFormat $key ${envNumMap[$key]}, "
done
axLog $envNumFormat

read -p "请输入环境变量编号: " envNum
# :- 默认值
envNum=${envNum:-'0'}
# 是否包含,判断是否为指定范围
[ ${envNumMap[envNum]} ] || envNum="0"
echo 环境变量: $envNum
# echo "envNum = $envNum"

file="Gemfile.lock"
rm -rf $file

# 拼接语句
#😄 定义语句
fastlane="fastlane ios "
if [ "$buildValue" != "" ]; then
    fastlane="$fastlane $buildValue"
fi

if [ "$envNum" != "" ]; then
    fastlane="$fastlane envNum:$envNum"
fi

if [ "$version_number" != "" ]; then
    fastlane="$fastlane version_number:$version_number"
fi

# 打印fastlane语句
echo
echo "🔽 🔽 🔽 🔽 🔽 🔽 🔽 🔽 🔽 🔽"
echo
echo 🚀 ${fastlane}
echo
echo "🔼 🔼 🔼 🔼 🔼 🔼 🔼 🔼 🔼 🔼"
echo
# 执行fastlane语句
# $fastlane
```

# 8 vscode 快捷键

```bash
Option + Shift + F 格式化
```

# 9 GitHub频道

```
https://github.com/topics
```

# 10 git 提交日志

```
type用于说明 commit 的类别，只允许使用下面7个标识。

        feat：新功能（feature）
        fix：修补bug
        docs：文档（documentation）
        style： 格式（不影响代码运行的变动）
        refactor：重构（即不是新增功能，也不是修改bug的代码变动）
        test：增加测试
        chore：构建过程或辅助工具的变动

如果type为feat和fix，则该 commit 将肯定出现在 Change log 之中。其他情况（docs、chore、style、refactor、test）由你决定，要不要放入 Change log，建议是不要。
```

# 11 SQLite

## 1 建表,有主键

```sqlite
CREATE TABLE test_create_tab2 (
id INTEGER PRIMARY KEY
); 
```

## 2 建表,主键,含有默认值

```sqlite
CREATE TABLE test_create_tab1 (
id INT,
val VARCHAR(10),
PRIMARY KEY (id)
);
```

## 3 建表,自增主键

```sqlite
Create table tabName(
id INTEGER PRIMARY KEY AUTOINCREMENT, 
name varchar, 
type Integer);
```

## 4 查询最后一条数据

本文共分为三种方式

1.max(id) 函数

```
select * from student where id = (select max(id) from student);
```

2.order by id desc limit 1

```
select * from student order by id desc limit 1;
```

3.last_insert_id() 函数

```
select * from student where id = (select last_insert_id());
```

## 5 不存在插入，存在更新语句

```
replace INTO
```

# 14 vim 命令

```text
:w            - 保存文件，不退出 vim
:w file  -将修改另外保存到 file 中，不退出 vim
:w!          -强制保存，不退出 vim
:wq          -保存文件，退出 vim
:wq!        -强制保存文件，退出 vim
:q            -不保存文件，退出 vim
:q!          -不保存文件，强制退出 vim
:e!          -放弃所有修改，从上次保存文件开始再编辑
```

# 15 linux 命令

```shell
ps -ef | grep java  #查看java服务
```

## 1. 查询 端口和进程号

### (1)、根据端口找PID

```
netstat -anp | grep 8080
```

### (2)、根据应用名找PID

```
ps -ef | grep java
```

### (3)、PID列表

````
jps -l
````

### (4)、PID过滤

````
jps -l | grep 应用名
````

### (5)、通过PID查端口

```
netstat -nap | grep 进程号
```

```
lsof -i | grep 进程号 # 不好用
```

### (6)、查询已开放的端口

```
netstat -lntu
```

```
参数使用，
    -l – 只显示监听接口
    -n – 显示端口号
    -t – 启用的 tcp 端口列表
    -u – 启用的 udp 端口列表
```

### (7)、通过应用名称获得PID

```
`ps -ef | grep -n ${packageName} | grep -v grep | awk '{print $2}'`
```



```shell
curl ip.sb # 只显示ipv4

curl cip.cc #显示ipv4和地址信息
```

## jps命令

```
# jps(Java Virtual Machine Process Status Tool)
#是java提供的一个显示当前所有java进程pid的命令，适合在linux/unix平台上简单察看当前java进程的一些简单情况。

jps -l （显示java进程的Id和软件名称）

jps -lmv（显示java进程的Id和软件名称；显示启动main输入参数；虚拟机参数）
```

```
ps -ef | grep xx
```

## 文件权限

```textile
chmod 775 xx
```

```latex
Linux文件访问权限分为可读，可写和可执行三种。
rwxr-xr-x 1 root root 6444 09-22 15:33 shmwrite

-rw-r--r-- 1 root root 1443 09-22 15:33 shmwrite.c

drwxr-xr-x 2 root root 4096 09-22 17:19 test

第一个字符代表文件类型。d代表目录,-代表非目录
第一个字符代表文件类型。d代表目录,-代表非目录。

接下来每三个字符为一组权限，分为三组，依次代表所有者权限，同组用户权限，其它用户权限

每组权限的三个字符依次代表是否可读，是否可写，是否可执行

r 表示拥有读的权限

w 表示拥有写的权限

x 表示拥有可执行的权限

- 表示没有该权限

修改权限

可用chmod命令来修改文件权限。

例如：

chmod 754 test
chmod -R 754 test # -R表示修改本文件夹及子文件夹权限

4代表读权限，2代表写权限，1代表执行权限

7=4 + 2 + 1,表示拥有可读可写可执行权限

5=4 + 1,表示拥有可读可执行权限，但是没有写权限

0 代表没有任何权限

以此类推

思考下为什么是4，2，1分别代表读写执行权限,而不是其它数字？

我们知道计算机最底层编码都是二进制，即0，1。要表示一个文件读写执行权限，底层只需一个字节，即8位即可。
```

```
systemctl status xx
```

```
netstat -aptn命令行，查看所有开启的端口号，
```

## netstat 命令

```
netstat -tunlp 用于显示 tcp，udp 的端口和进程等相关情况
netstat 查看端口占用语法格式：
netstat -tunlp | grep 端口号

-t (tcp) 仅显示tcp相关选项
-u (udp)仅显示udp相关选项
-n 拒绝显示别名，能显示数字的全部转化为数字
-l 仅列出在Listen(监听)的服务状态
-p 显示建立相关链接的程序名
```

## **lsof 的命令**

```
losf能看到pid和用户，能够找到哪一个进程占用了这个端口grep
lsof -i 所有端口
lsof -i:8080：查看8080端口占用
lsof abc.txt：显示开启文件abc.txt的进程
lsof -c abc：显示abc进程现在打开的文件
lsof -c -p 1234：列出进程号为1234的进程所打开的文件
lsof -g gid：显示归属gid的进程情况
lsof +d /usr/local/：显示目录下被进程开启的文件
lsof +D /usr/local/：同上，但是会搜索目录下的目录，时间较长
lsof -d 4：显示使用fd为4的进程
lsof -i -U：显示所有打开的端口和UNIX domain文件
```



# 16 docker

## 安装和命令

### 国内安装docker

```
curl -sSL https://get.daocloud.io/docker | sh
```

```
--restart=always \ 自启动
--privileged=true \ 容器内部拥有root权限
```

### 创建完成的容器修改启动参数

```
docker container update restart=always 容器名或id
```

### 查看气启动参数

```
runlike 容器
```



### 系统开关机命令

```
启动: systemctl start docker
停止: systemctl stop docker
重启: systemctl restart docker
查看状态: systemctl status docker
开机启动: systemctl enable docker
```

### 镜像命令

```
查看概要: docker info
查看本地镜像: docker images
拉取镜像: docker pull
查看存储: docker system df
强制删除镜像: docker rmi -f
查看已下载的Docker镜像latest具体版本
docker image inspect (docker image名称):latest|grep -i version
```

### 容器命令

```
启动交互式容器(前台命令行)

查看运行的容器: docker ps 
显示所有的容器，包括未运行的: docker ps -a
    停止后无法查看,要查看需要运行的,可以用 docker images 查找容器id 也可以用 docker ps -n 2 最近使用的
查看已经停止的: docker ps -n 2
进入容器: docker exec -it 容器id /bin/bash

退出
容器关闭:   exit 
容器不停止:  ctrl+p+q 

启动已经停止的容器id: docker start 容器id
重启容器: docker restart 容器id
停止容器: docker stop 容器id
强制停止容器: docker kill 容器id
删除已停止容器: docker rm

开机启动 docker update --restart=always  xx
```

### 查看容器运行状态

```
docker stats 
```

### 复制文件到容器

```
docker cp 容器di:容器内路径 目的主机路径
```

## portainer-ce 图形界面

### 命令

```
docker run -d  --name portainer -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock -v /app/portainer_data:/data --restart always --privileged=true portainer/portainer-ce:latest
```



## mysql

### 命令

```
docker run \
--name mysql8 -d \
-p 3306:3306 \
--network demo-network \
--network-alias mysql8 \
-e MYSQL_ROOT_PASSWORD=123456 \
--restart=always \
--privileged=true \
-v ~/mydata/mysql8/data:/var/lib/mysql \
-v ~/mydata/mysql8/logs:/var/log/mysql \
-v ~/mydata/mysql8/conf/my.cnf:/etc/mysql/my.cnf \
mysql:8.0.28
```

### 配置文件 my.cnf

```
[mysqld]
pid-file        = /var/run/mysqld/mysqld.pid
socket          = /var/run/mysqld/mysqld.sock
datadir         = /var/lib/mysql
secure-file-priv= NULL
# Disabling symbolic-links is recommended to prevent assorted security risks
symbolic-links=0

# Custom config should go here
!includedir /etc/mysql/conf.d/


## 阿里云,下面不要使用
# 默认使用“mysql_native_password”插件认证
default_authentication_plugin= mysql_native_password
#Accept connections from any IP address,客户端远程
bind-address = 0.0.0.0

# 设置mysql客户端默认字符集
default-character-set=utf8
[client]
# 设置mysql客户端连接服务端时默认使用的端口
port=3306
default-character-set=utf8
```

### Navicat链接问题

```
docker exec -it mysql8 /bin/bash
mysql -u root -p
use mysql;
update user set host = '%' where user ='root';
flush privileges;
```

##  postgres

```
docker run --name demo-pgsql  -d \
--network demo-network \
-e POSTGRES_PASSWORD=postgres \
-p 5432:5432 \
-v ~/mydata/pgsql/data:/var/lib/postgresql/data \
postgres
```



## nacos

### 低版本(1.4.x)

```
挂载的文是/home/nacos/init.d/custom.properties
```

```
docker pull nacos/nacos-server:1.4.0

mkdir -p ~/mydata/nacos1/{init.d,conf}

docker run --name nacos -d \
-e MODE=standalone \
-p 8848:8848 \
--restart=always \
-v ~/mydata/nacos/logs:/home/nacos/logs \
-v ~/mydata/nacos/init/custom.properties:/home/nacos/init.d/custom.properties \
nacos/nacos-server:1.4.0
```

### 1.4.2 及 2.0.3版本

```
mkdir -p ~/mydata/nacos/{logs,conf}
```

````
修改内存大小
-e JVM_XMS=128m \
-e JVM_XMX=128m \
-e JVM_XMN=64m \
````

```
挂载的文件是/home/nacos/conf/application.properties
```

##### 复制配置文件

```
docker  run \
--name nacos -d \
-p 8848:8848 \
nacos/nacos-server:v2.0.4
```

```
docker cp nacos:/home/nacos/conf/application.properties ~/mydata/nacos/conf/application.properties
```

```
docker stop nacos 
docker rm nacos
```



```
docker  run \
--name nacos -d \
-p 8848:8848 \
--network demo-network \
--privileged=true \
--restart=always \
-e MODE=standalone \
-v ~/mydata/nacos/logs:/home/nacos/logs \
-v ~/mydata/nacos/conf/application.properties:/home/nacos/conf/application.properties \
nacos/nacos-server:v2.0.4
```

##### 持久化SQL,注意版本

```
https://github.com/alibaba/nacos/blob/2.0.4/distribution/conf/nacos-mysql.sql
```

## seata

### 命令

```
docker run --name demo-seata -d \
-p 8091:8091 \
--network demo-network \
--privileged=true \
--restart=always \
-e SEATA_PORT=8091 \
-v ~/mydata/seata/conf/registry.conf:/seata-server/resources/registry.conf \
-v ~/mydata/seata/conf/file.conf:/seata-server/resources/file.conf \
-v ~/mydata/seata/logs:/root/logs \
seataio/seata-server:1.4.2
```

### 持久化SQL

```
新版本 seata+nacos 需要在nacos导入配置文件,官网执行sh脚本
https://github.com/seata/seata/blob/develop/script/server/db/mysql.sql
```



## redis

### 命令

```
docker run --name redis6 -d \
-p 6379:6379 \
--privileged=true \
--restart=always \
--network demo-network \
-v ~/mydata/redis/conf:/etc/redis.conf \
-v ~/mydata/redis/data:/data \
redis:6.2.7-alpine3.15
```

## nginx

### 建立挂载目录

```
mkdir -p ~/mydata/nginx/{conf,conf.d,html,log}

docker run --name demo-nginx -p 8080:80 -d nginx
docker cp demo-nginx:/etc/nginx/nginx.conf ~/mydata/nginx/conf/nginx.conf

docker cp demo-nginx:/etc/nginx/conf.d/default.conf ~/mydata/nginx/conf.d/default.conf
```

### 命令

```
docker run --name demo-nginx -d \
-p 3500:80 \
--network demo-network \
-v ~/mydata/nginx/html:/usr/share/nginx/html \
-v ~/mydata/nginx/conf/nginx.conf:/etc/nginx/nginx.conf \
-v ~/mydata/nginx/conf.d/default.conf:/etc/nginx/conf.d/default.conf \
-v ~/mydata/nginx/log:/var/log/nginx \
nginx:1.21.6-alpine
```

```
docker run -i -t --network demo-network   -p 50070:50070 -p 9000:9000 -p 8088:8088 -p 8040:8040 -p 8042:8042  -p 49707:49707  -p 50010:50010  -p 50075:50075  -p 50090:50090 sequenceiq/hadoop-docker:2.6.0 /etc/bootstrap.sh -bash
```



## mongodb

### 文件夹

```
mkdir -p ~/mydata/mongodb/{data,conf,backup}
```

### mongodb.conf

```
# mongodb.conf
logappend=true
# 被远程
# bind_ip=127.0.0.1
port=27017 
fork=true
noprealloc=true
auth=true
```



### 命令

```
docker run --name mongodb -d \
-p 27017:27017 \
--network=demo-network \
--privileged=true \
-e MONGO_INITDB_ROOT_USERNAME=admin \
-e MONGO_INITDB_ROOT_PASSWORD=admin123 \
-v ~/mydata/mongodb/data:/data/db \
-v ~/mydata/mongodb/backup:/data/backup \
-v ~/mydata/mongodb/conf:/data/configdb \
mongo:4.4.13-focal
```

## minio

### 命令

```
docker run -p 9030:9000 -p 9031:9001 --name minio \
-d --restart=always \
--privileged=true \
-e TZ="Asia/Shanghai" \
-e MINIO_ROOT_USER=admin \
-e MINIO_ROOT_PASSWORD=admin123 \
-v ~/mydata/minio/data:/data \
-v ~/mydata/minio/config:/root/.minio \
minio/minio:latest server /data --console-address ":9001"
```

## keycloak

```
docker run --name keycloak -d -p 7010:8080 -e KEYCLOAK_USER=admin -e KEYCLOAK_PASSWORD=admin jboss/keycloak:16.0.0
```

```
docker exec -it keycloak bash
```

```
cd /opt/jboss/keycloak/bin  # 在opt里面,每个版本不一样,
```

```
./kcadm.sh config credentials --server http://localhost:8080/auth --realm master --user admin 
```

```
./kcadm.sh update realms/master -s sslRequired=NONE
```

## rabbitmq

### 命令

```
docker run --name rabbitmq -d \
--privileged=true \
--restart=always \
-d -p 5672:5672 -p 15672:15672 \
-v ~/mydata/rabbitmq/data:/var/lib/rabbitmq \
-v ~/mydata/rabbitmq/conf:/etc/rabbitmq \
-v ~/mydata/rabbitmq/log:/var/log/rabbitmq \
--hostname=rabbitmqhost \
-e RABBITMQ_DEFAULT_VHOST=my_vhost \
-e RABBITMQ_DEFAULT_USER=admin \
-e RABBITMQ_DEFAULT_PASS=123456 \
rabbitmq:3.9.20-management-alpine
```

### 进入bin开启管理页面

```
docker exec -it rabbitmq /bin/bash
```

```
rabbitmq-plugins enable rabbitmq_management
```





# 17 flink

```sql
-- 源数据表
CREATE TABLE source_person
(
    id STRING,
    name STRING,
    primary key (id) NOT ENFORCED
)
WITH (
    'connector' = 'mysql-cdc',-- 监听binlog用mysql-cdc
    'hostname' = 'localhost',
    'port' = '3306',
    'username' = 'root',
    'password' = '12345678',
    'database-name' = 'test_flink',
    'table-name' = 'person',
    'scan.startup.mode' = 'latest-offset' -- 每次偏移,默认全量
)

-- 目标数据表
CREATE TABLE target_person (
 id INT,
 name STRING,
 primary key (id) NOT ENFORCED
) WITH (
 'connector' = 'jdbc',
 'driver' = 'com.mysql.cj.jdbc.Driver',
 'url' = 'jdbc:mysql://localhost:3306/test_flink_target?serverTimezone=UTC&useSSL=false',
 'username' = 'root',
 'password' = '12345678',
 'table-name' = 'person'
)

-- 监听输入
insert into target_person select * from source_person
```

