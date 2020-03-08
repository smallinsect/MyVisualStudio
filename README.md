# MyVisualStudio

输出目录
$(SolutionDir)../bin/$(Platform)/$(Configuration)/
中检目录
$(SolutionDir)../bintemp/$(Platform)/$(ProjectName)/$(Configuration)/

windows下查看动态库和静态库的函数接口
在window下查看动态库的导出函数可以用vs自带的Dependenc工具；
查看静态库的信息要用命令行来实现：
dumpbin   /LINKERMEMBER   *.lib   >   1.txt
查看动态库的信息要用命令行来实现：
dumpbin  /exports  *.dll  >1.tx


静态库：在vs中新建生成静态库的工程，编译生成成功后，只产生一个.lib文件


动态库：动态链接库是一个包含可由多个程序同时使用的代码和数据的库，DLL不是可执行文件。动态链接提供了一种方法，使进程可以调用不属于其可执行代码的函数。函数的可执行代码位于一个 DLL 中，该 DLL 包含一个或多个已被编译、链接并与使用它们的进程分开存储的函数。在vs中新建生成动态库的工程，编译成功后，产生一个.lib文件和一个.dll文件

静态库中的lib：该LIB包含函数代码本身（即包括函数的索引，也包括实现），在编译时直接将代码加入程序当中
动态库中的lib：该LIB包含了函数所在的DLL文件和文件中函数位置的信息（索引），函数实现代码由运行时加载在进程空间中的DLL提供
总之，lib是编译时用到的，dll是运行时用到的。如果要完成源代码的编译，只需要lib；如果要使动态链接的程序运行起来，只需要dll。
