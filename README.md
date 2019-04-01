## 说明

skills 中需要对应角色名启动角色专属脚本（列表）

并且还需要调整与skills目录同级的人物技能文件，需要启动hkj之后在“脚本设置”中自行调整，这里就不做具体的维护工作了，只用来维护脚本。

## 使用

为了方便复用和单点维护，windows系统建议使用符号连接```mklink```实现快速引入

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
