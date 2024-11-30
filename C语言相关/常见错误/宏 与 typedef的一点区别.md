```c
#define INT_PTR int*
typedef int* int_ptr;
int main()
{
	INT_PTR i, j;
	int_ptr x, y;
}
```
在上面代码中 j是`int`型,而 i, x, y 这几常量为`int*`类型，为什么？

**#define这个宏**，在预处理阶段将会转化为
```
#define INT_PTR int*
INT_PTR i,j
int* i，j;(这只是简单的文本替换,不做类型检查)
```

**而对于typedef** ，在预处理阶段会有类型检查
```c
typedef int*  int_ptr;  
int_ptr x,y 
int *x, *y;
```
