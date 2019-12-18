# 小鹤音形fcitx rime挂接版

本仓库为小鹤双拼Linux Rime挂接版镜像,挂接内容来自官方网盘。 

- 网盘地址：
http://flypy.ys168.com/  

Linux小鹤音形无直接对应程序，需要挂载Rime使用。

Rime是个优秀的输入工具，在Mac/Windos/Linux/Andrido/ios平台都有对应的实现。  

Linux平台的Rime依赖Fcitx或IBus。（本仓库挂接版为Fcitx配置，IBUS请自行测试）

> 小鹤双拼挂载官方提供的是基于Fcitx框架



## 更新记录

- 官网更新说明:
https://flypy.com/bbs/forum.php?mod=viewthread&tid=8&extra=page%3D1

## 测试环境

已经在Archlinux下测试可以正常使用。

- Archlinux
    - Manjaro
    - Arch分支

- 其他GNU/Linux发型版请测。

## 安装

- Fcitx输入法框架
- Rime输入法

在**Archlinux**及**Arch分支**(例如**Manjaro**)下安装

```sh
$ sudo pacman -S fcitx-rime
$ sudo pacman -S fcitx-configtool
```

或者使用`yay`作为包管理工具:
```sh
$ sudo yay fcitx-rime
$ sudo yay fcitx-configtool
```

## 配置fcitx
安装完Fcitx输入框架几Rime输入发后，在任务栏上右键**Fcitx**托盘图标:

如果是英文系统，需要取消`only show current language`的勾选。


## 配置小鹤双拼挂在

将GNU/Linux版本的小鹤双拼文件下载后，进入**rime-data**文件夹。


> 进行以下操作时，建议先备份Rime默认的配置文件。

将**rime-data**目录下的所有**yaml**和**txt**复制到**rime**的**rime-date**文件夹:  

```sh
$ sudo cp *.yaml *.txt /usr/share/rime-data/
```

将**build**文件夹下所有的**bin**文件放到**rime**的**build**目录
```sh
 $ sudo cp -r build /usr/share/rime-data/build/

重启fcitx,并切换到Rime输入发生效。(右键fcitx托盘重启和选择输入法）。

>  上面将自己的配置覆盖默认配置是有争议的，建议将配置文件移动到~/.config/fcitx/rime 


**美化设置**

fcitx用户目录位置：

```sh
 ~/.config/fcitx/rime/             
 ```

rime的皮肤用的是fcitx的皮肤，自定义皮肤目录为:
```sh
/usr/share/fcitx/skin
```
## 插件设置
在新更的小鹤双拼挂载中，多了个rime.lua。里面集成了日期和时间功能。并且在小鹤双拼输入方案**flypy.schema.yaml**中也增加了对应的配置，但是在测试时并未能触发。测试了半天没搞定。

**Rime配置**

禁用Rime的英文模式
rime的英文模会将`Shift`键触发为rime的英文模式。
从输入方案中 `engine/processor`列表里注视`ascii_composer`


## Todo

迁移配置文件到`~/.config/fcitx/rime`
