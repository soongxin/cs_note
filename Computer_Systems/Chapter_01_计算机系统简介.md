# 计算机系统简介
### 计算机中的信息表示

* 文本文件, 比如编写的代码文件和txt文件等, 在计算机中一般是以ASCII码的形式来存储的. ASCII码是以八位二进制数组成的单字节来表示英文中的符号

* 除了文本文件之外的其他文件, 都是二进制编码的方式来存储, 通过文件的上下文来决定文件是按照什么格式解析.

[跳转](#jump)

[去其他文件](./Chapter_02_计算机信息表示方法.md#another)

* C语言文件的执行过程:

    1. 预处理: 将编写好的C语言代码进行预处理, 主要是替换代码中的宏定义, 文件后缀为`.cpp`.
    
    2. 编译: 将经过预处理的代码编译成汇编语言, 文件后缀为`.s`.

    3. 汇编: 将汇编语言表示的代码, 转换成机器可以处理的机器语言, 文件后缀为`.o`.

    4. 链接: 将程序中的系统代码, 如`printf()`函数等, 连接到系统中预先编译好的程序文件, 便于将来按顺序执行, 可以为无后缀的文件

> c语言文件在Linux系统中的执行可以使用`>>> ./hello`命令来执行, 当shell检测到命令并不是以系统命令开头时, 会默认将当前输入的文件名按照可执行文件来处理.

> 程序是由位和上下文组成, 位表示程序中存储的代码, 上下文包含了程序运行所需要的信息及参数等必要元素.

### 计算机系统组成

1. 总线

    总线负责在计算的各个组件之间传递信息, 通常被设计成传递固定大小的消息, 常为4个字节(32位)或8个字节(64位).

2. 主存(内存)

    主存由一组动态随机存储器组成(DRAM-Dyamic Random Memory)组成, 用来存放程序和程序处理的数据, 逻辑上来说是一个线性的数组. 

3. 外部存储(硬盘等)

    用来永久存储文件等数据

4. I/O设备

    显示器、扬声器等输出设备, 键盘、鼠标等输入设备.

5. CPU
    
    * 中央处理器单元(CPU-Center Processer Unit), 用来执行程序的部件.

        主要组成:

    1. 程序计数器(PC-Programm Counter), 一个指向正在运行程序的指针, 当前程序 -> 运行完成后, 指向下一条指令.

    2. ALU模块, 算法计算单元, 用来执行程序的逻辑运算.

    3. 寄存器, 用来保存需要执行的程序代码.

    4. 高速缓存, 高速缓存用来提高程序的运行速度, 一般的CPU拥有L1一级缓存, 现代CPU甚至已经拥有了L1~L3三级缓存.

    * 缓存结构

        CPU寄存器 -> L1高速缓存 -> L2高速缓存 -> L3高速缓存 -> 主存(DRAM) -> 电脑I/O设备, 硬盘等 -> 远端存储设备, Web网页, 服务器等

### 程序运行的抽象

计算机执行程序的过程, 被抽象成了虚拟内存、进程、I/O设备等.

1. 虚拟内存

    计算机的运行过程中, 程序需要访问的数据, 抽象成了虚拟内存, 在程序运行过程中, 从程序本身代码存储的位置开始, 到程序需要访问的内存, 按照一定的结构来排列.

2. 进程

    一个程序运行起来后, 程序本身和所占用的资源, 已经需要访问的虚拟内存, 组成了进程, 计算机的运行过程, 并不是只有一个进程在同时运行, 进程间的切换由操作系统来完成.

3. I/O 

    任何的输入、输出设备, 都可以抽象成I/O设备, 键盘鼠标显示器等.

<span id="jump">跳转到的位置</span>

    