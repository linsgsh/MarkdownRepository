### 一、shell远程连接

#### 1、更新软件源

```shell
#更新系统
sudo apt-get update
```

#### 2、安装shell服务

```shell
#apt-get方法安装软件
sudo apt-get install openssh-server
```

#### 3、查看IP

```shell
ifconfig
```

#### 4、远程连接

````shell
#设置root密码(普通用户)
sudo password  root
输入密码：

#普通用户切换为root用户
su root
输入密码

#root用户切换到/目录
cd /

#给目标目录设置权限(如果不给目标目录设置权限,则传输失败)
chomod 777 /opt

#传输文件
#新建传输文件 --> 选择windows目录的文件和linux目标目录
````





### 二、搜狗输入法

#### 1、添加fcitx键盘输入法系统

```shell
#更新系统
sudo apt-get update

#安装所缺少的依赖
sudo apt-get -f install

#
sudo apt-get update --fix-missing
```



#### 2、安装搜狗输入法 

```shell
#1.进入搜狗输入法安装包的目录
cd  /下载

#2.dpkg命令安装(**代表版本号)
sudo dpkg -i sogoupinyin_**_amd64.deb 

#3.系统设置 --> 语言支持 --> 键盘输入法系统 --> fictx

#4.重启
reboot
```



### 三、Ubuntu设置中文

 System Settings --> Lanauge Support  --> install/remove lanague 

--> chinese --> 点击apply --> 输入密码 -->  点击Authenticate

--> 切换 Regional formats --> 选择中文 --> 点击Apply System-wide 

--> 点击close --> 注销



### 







