## 项目目录结构

```
|- character
   |- XXX.txt              // 技能模板，根据不同的场景需求拟定的角色模板（通俗的讲就是skills中某个职业的一系列技能的组合），可用软连接方式连接到 角色.txt
|- skills
   |- default              // 默认技能，为方便维护，所有的姿势默认放在这里。将此目录复制到/res/skills中，或者建立同名软连接
   |- XXX                  // 针对不同角色的通用的技能脚本组
      |- ${技能名称}.txt    // 技能脚本
```

## res目录结构

很多人一头雾水，我开始也是

```
SB目录
 |- res
    |- auto_del_obj.dat.dat     //背包自动清理
    |- ${角色名}_${角色id}.txt    //技能脚本排序、生效列表
    |- skills                   //技能脚本目录
       |- default               //默认技能脚本存放处
          |- common.txt         //全局脚本（缺失的话会出提示）
          |- ${技能名称}.txt     //默认技能脚本（优先级最低）
       |- ${技能名称}.txt        //自定义技能脚本（优先级中）
       |- ${角色名}              //角色技能目录
          |- ${技能名称}.txt     //角色技能脚本（优先级最高）
```

同名称的技能脚本根据所在目录不同拥有不同的优先级，呈覆盖关系，只有一个会生效： 单独角色脚本 > 自定义技能脚本 > 默认技能脚本

## 说明

skills 中需要对应角色名启动角色专属脚本（列表）

并且还需要调整与skills目录同级的人物技能文件，需要启动黑科技之后在“脚本设置”中自行调整，这里就不做具体的维护工作了，只用来维护脚本。

## 使用

### 拷贝更名

将脚本目录复制到 ```C:\SB所在目录\res\skills```，将目录名改为角色名即可。

### 符号连接快速引入

为了方便复用和单点维护，windows系统建议使用符号连接```mklink```实现快速引入，windows10可直接使用，其他版本

检出或下载本项目至目录

```bat
mklink /d C:\SB所在目录\res\skills\角色名 C:\本项目目录\skills\脚本组名
```
 
如:

```bat
mklink /d C:\magicbane\res\skills\xxx C:\workspace\SB-Launcher\skills\DLY_FM
```

这样角色 xxx 就可以使用 德鲁伊自动打怪的脚本

如果有 xxx_2 可重复上面步骤，也使用同样的脚本

需要注意的是，启动脚本前要调整脚本顺序，具体的排序方式请按照右侧推荐的排序规则

### 如果不想敲命令或不是win10

下载安装带界面的 [Symlinker](http://amd989.github.io/Symlinker/)

- Windows Vista
- Windows 7
- Windows 8 and 8.1

windows 10 一样可用
