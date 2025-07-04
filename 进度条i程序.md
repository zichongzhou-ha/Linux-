## 进度条小程序
>Makefile文件
```
hello:hello.c process.c
	gcc hello.c process.c -o hello -DN=2//在外面传参
.PHONY:clean
clean:
	rm -f hello
```
>hello.c文件
```
#include"process.h"
int main()
{
    
    ProncessOn();

    return 0;
}
```
>process.c文件
```
#include"process.h"
#include <stdio.h>
char style[S_Num]={'-','.','#','>','<'};
<!-- 习惯性地会将数组的大小用宏定义来写 -->
<!-- 通过外面传参，选择想要的图形进度条 -->
void ProncessOn()
{
    int cnt=0;
    char bar[NUM];
    memset(bar,'\0',sizeof(bar));
    const char* label="|\\-/";
    while(cnt<=100)
    {
     printf("[%-100s][%d%%][%c]\r",bar,cnt,lab[cnt%4]);
     fflush(stdout);
     bar[cnt++]=style[N];
     usleep(50000);

    }
    printf("\n");
}
```
>process.h文件
```
#pragma once
<!-- 1.当 hello.c 和 process.c 同时包含 process.h 时不会重复定义
2.避免因多次包含导致的重定义编译错误 -->
#include<stdio.h>
#include<string.h>
#include<unistd.h>

#define NUM 101
#define S_Num 5
extern void ProncessOn();//为啥在头文件中对函数的声明前加上extern
//明确告知编译器该函数在其他源文件（.c/.cpp）中定义!

```

### 总结
- \r->时回车   \n->是换行回车   \r\n->回车换行       
在语言层面\n就是回车换行
 ```
 int main()
 {
    int cnt=10;
    while(cnt)
    {
        printf("剩余时间：%2d\r",cnt);
        fflush(stdout);
        cnt--;
        sleep(1);
    }
    return 0;
 }
 ```
 - 对于上面这段代码，执行后等段时间才有打印，对它进行分析：
 首先执行的一定是printf，因为我们的代码是顺序结构，但是先执行prinf!=数据先显示，prinf的内容在缓冲区中，如果加上换行符\n就可以把它从缓冲区加载出来了，\r没有这个功能
 - fflush(stdout) 在 C/C++ 中用于强制刷新标准输出流（stdout）的缓冲区，确保缓冲区中的数据立即写入目标设备（如终端、文件等）
 
