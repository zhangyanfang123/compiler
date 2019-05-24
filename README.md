# MiniC Compiler
> 编译器课程设计 实现C语言编译器的子集,生成 Intelx86 32位汇编,
[下载](http://baidu.com)
## 功能
1. 数据类型: void int char
2. 运算符: 不支持三元表达式，不支持位运算符
3. 语句: 支持分支语句 if else 结构，switch case 结构
        支持循环结构 do while结构 while 结构 for结构
        支持 break 支持 continue
4. 数组: 不支持数组初始化,只支持一维数组
5. 指针: 不支持指针数组,可以实现字符串初始化
6. 函数调用： 支持函数调用，支持向数组传入指针和数组
7. 基本输入输出：内置printf write read
        printf 输出常量字符串
        write 输出单个变量或常量
        read 输入变量
8. 不支持预处理:即不要使用#
## 打印结果
1. 词法分析中间结果 支持到文件的重定向 使用 -o 或者 >
> -lex source.c [> target.txt]
2. 语法分析中间结果 支持到文件的重定向 使用 -o 或者 >
> -parse source.c [> target.txt]
3. 语义分析中间结果 支持到文件的重定向 使用 -o 或者 >
> -intercode source.c [> target.txt]
4. 代码生成中间结果 支持到文件的重定向 使用 -o 或者 >
> -S source.c [> target.s]
## 源文件使用
1. 源文件在windows平台，codeblocks IDE开发，可以使用        codeblocks打开项目文件，其他打开方式自行探索
2. 源文件使用 windows库，只可以在windows中使用，当然删除几个特定功能可以做到软件移植，读者可以尝试
3. 对生成的汇编使用32位 gcc可以进行汇编链接
> gcc -o target source.s

4.使用gcc 生成汇编的指令，可以做一下比较
> gcc -S source.c -masm=intel -m32 -std=c99
## 联系开发者
1. 如果程序出现结果异常或者程序崩溃，请联系开发者，感激不尽
2. 开发者 会在下一步计划实现 float double 指针数组，数组初始化，结构体，预编译器，可以期待一下

###示例代码
```c
void change(int *a, int *b){
	int t = *a;
	*a = *b;
	*b = t;
}
int main() {
	int a = 1;
	int b = 3;
	change(&a,&b);
	write(a);
        printf("\n");
	write(b);
        printf("\n");
}

```


# compiler
