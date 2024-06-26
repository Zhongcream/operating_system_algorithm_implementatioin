# 银行家算法(cn)

操作系统
-------

### 问题
编写一个多线程程序，实现银行家算法。创建n个线程,这些线程从银行请求和释放资源。银行家只会在请求不会让系统处于不安全状态时才会授予资源。确保共享数据的安全访问非常重要。为了确保对共享数据的安全访问，可以使用互斥锁

### 解决方案
* [C语言下的多线程实现](my_bankers_algorithm.c)

### 输入
```c
进程数量? 5
资源数量? 3

当前可用资源 (R1 R2 ...)? 3 3 2

进程 1 被分配的资源 (R1 R2 ...)? 2 0 0
进程 2 被分配的资源 (R1 R2 ...)? 2 0 0
进程 3 被分配的资源 (R1 R2 ...)? 3 0 2
进程 4 被分配的资源 (R1 R2 ...)? 2 1 1
进程 5 被分配的资源 (R1 R2 ...)? 0 0 2

进程 1 所需的最大资源 (R1 R2 ...)? 7 5 3
进程 2 所需的最大资源 (R1 R2 ...)? 3 2 2
进程 3 所需的最大资源 (R1 R2 ...)? 9 0 2
进程 4 所需的最大资源 (R1 R2 ...)? 2 2 2
进程 5 所需的最大资源 (R1 R2 ...)? 4 3 3
```

### 输出
```c
找到安全序列 : 2 4 5 1 3
正在执行进程...

--> 进程2
    已分配 : 2  0  0
    需求   : 1  2  2
    可用资源:3  3  2
    分配资源！
    进程代码正在运行...
    进程代码完成...
    释放资源中...
    资源已释放！
    现在可用:5  3  2

--> 进程4
    已分配 : 2  1  1
    需求   : 0  1  1
    可用资源:5  3  2
    分配资源!
    进程代码正在运行...
    进程代码完成...
    释放资源中...
    资源已释放！
    现在可用:7  4  3

--> 进程5
    已分配 : 0  0  2
    需求   : 4  3  1
    可用资源:7  4  3
    分配资源!
    进程代码正在运行...
    进程代码完成...
    释放资源中...
    资源已释放！
    现在可用:7  4  5

--> 进程1
    已分配 : 0  1  0
    需求   : 7  4  3
    可用资源:7  4  5
    分配资源!
    进程代码正在运行...
    进程代码完成...
    释放资源中...
    资源已释放！
    现在可用:7 5  5

--> 进程3
    已分配 : 3  0  2
    需求   : 6  0  0
    可用资源:7  5  5
    分配资源!
    进程代码正在运行...
    进程代码完成...
    释放资源中...
    资源已释放！
    现在可用:10  5  7

所有进程都已完成！
```

### 代办事项
* 创建文件
* 有同学提醒，需要视图，可以使用表格语法实现