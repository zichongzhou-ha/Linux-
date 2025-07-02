## hello world

- Makefile文件
```
hello:hello.c process.c
	gcc hello.c process.c -o hello
.PHONY:clean
clean:
	rm -f hello
```
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