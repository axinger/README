# 1. cocopod使用

## 1.1 新建

```ruby
init pod
```

## 1.2 打开编辑

```ruby
open -a xcode podfile
```

## 1.3 加载

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

## 1.4 注册 不要bb 表示注册过,登录

```ruby
pod trunk register aa@qq.com bb
```

# 2.制作cocopod库

## 2.1 新建

注册

```
pod trunk register liu_weixing@qq.com 'axinger' --description='阿星iOS'
```

```
pod trunk me
```



```
pod lib create AXiOSKit
```

```sh
pod lib create xx --template-url=https://gitee.com/axinger/pod-template.git
```

## 2.2 验证

### 2.2.1 本地验证,只从本地验证你的pod能否通过验证。

```shell
pod lib lint --verbose --use-libraries --allow-warnings --sources='https://gitee.com/axinger/AXCollectionObserve.git,https://gitee.com/mirrors/CocoaPods-Specs.git'
```

### 2.2.2 远程验证,是从本地和远程验证你的pod能否通过验证。

```ruby
pod spec lint --allow-warnings
pod spec lint  --use-libraries --allow-warnings --verbose --skip-import-validation
```

## 2.3推送

```ruby
pod trunk push  --allow-warnings
pod trunk push  --allow-warnings --verbose
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

## 2.4 删除本地搜索库

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



# 3. homebrew

```
rvm是用来管理ruby的，ruby的其中一个“程序”叫rubygems，简称 gem，而用来管理项目 的gem的，叫bundle.完全是不同的东西，他们相同的只是都可以管理gem

bundle是rails框架里面安装Gemfile指定的各种库的工具
```



## 3.1 brew cask 拓展 安装mac app

1. 搜索app,xx表示APP名称

```sh
brew search xx --cask
```

2. 安装app

```sh
brew install xx --cask
```

## 3.2 命令

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
brew services list	
brew search redis
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

## 3.3 RMV 离线安装

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

# 5 idea 快捷键

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

# 6 Mac 操作

## 6.1 mac 终端修改用户名

```shell
sudo scutil --set HostName xx
```

## 6.2 终端快捷键

```
清屏：command + k
终止当前进程：control + z
强制退出终端：command + q
```



## 6.3 设置git代理

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

