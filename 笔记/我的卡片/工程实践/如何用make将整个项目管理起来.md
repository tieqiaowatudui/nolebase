使用c语言开发的时候,需要频繁的使用gcc指令对开发出的源代码进行编译并指定编译结果存放的地方.整个构建过程手动太过麻烦,很多时候我们只修改了大量文件中的一小部分,使用指令依然全量重新编译消耗大量时间.
为了实现构建的自动化以及对于目标文件的管理以及各种不同文件之间的依赖关系,引入了构建工具make.
make工具需要在机器上安装make程序.使用的方式是在工程目录空间中添加一个`Makefile`文件.
`Makefile`文件的核心围绕 target,resource,command三者展开.具体的语法如下:

```c
target:resource
	command
```

这其中target是必须有的.而resource和command不适必须的,至少有一个.
构建的核心逻辑就是:资源target依赖于resource,通过command实现依赖资源和target的转变.
> command这里必须使用 `tab`.如果使用四个空格会报错.

# 目标(target)
目标是make构建的结果,这个结果可以作为其他目标的资源的中间目标,也可以是最终的目标,也可以作为触发command执行的一个单位.

# 资源(resource)
资源表示了整个