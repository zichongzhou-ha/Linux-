## hello world

- Makefile文件
```
hello:hello.c process.c
	gcc hello.c process.c -o hello
.PHONY:clean
clean:
	rm -f hello
```
>.PHONY:被改关键字修饰的对象是一个伪目标，即跳过了对于文件时间的检查，可以反复make clean；
>为什么我执行一次make生产了hello文件再执行make就不会再在执行命令了呢？gcc如何得知我不需要在编译了呢
>通过对hello.c最近一次内容的修改时间与hello文件进行比较，如果比它早就不用再编译了，如果对hello.c有进行内容上的修改就又会编译了,.PHONY也就是跳过了这个检查的过程

- hello.c文件
```
#include"process.h"
int main()
{
    
    ProncessOn();

    return 0;
}
```

- process.c文件
```
#include"process.h"

void ProncessOn()
{
    printf("hello world\n");
}
```

- process.h文件
```
#include<stdio.h>
extern void ProncessOn();
```
