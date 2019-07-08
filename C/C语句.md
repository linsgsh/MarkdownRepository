---
title: C语句
date: 2019-07-07 16:53:10
tags: 
    - C语言
categories: C语言
---

## 语句

### 一、选择/分支语句

#### 1、if语句

(1)if(表达式)........

```c
int i = 10;

if(i == 10) {
    printf("i等于10");
}

//当if执行语句只有一条时,可以不用写{}
if(i == 10) 
    printf("i等于10");
```

(2)if(表达式)........ else ........

```c
int i = 9;

if(i % 2 == 0) {
    printf("i是偶数");
} else {
    printf("i是奇数");
}


if(i % 2 == 0) 
    printf("i是偶数");
else 
    printf("i是奇数");
```

(3)if(表达式1)........ else if(表达式2) ........ else ........

```c
int i = 1;

if(i > 0) {
    printf("i是正整数");
} else if(i == 0) {
    printf("i是0");
} else {
    printf("i是负整数");
}

if(i > 0) 
    printf("i是正整数");
else if(i == 0) 
    printf("i是0"); 
else 
    printf("i是负整数");
```

(4)总结

```c
1、当if.../else if.../else的语句只有一条时,可以省略{},但是最好写上{}
2、对于if...,从数值上来说当表达式值为非零值时执行语句,当值为零时不执行语句
3、对于if...,从逻辑上来说当表达式为真时(即为1)执行语句,当为假(即为0)时不执行语句
```



#### 2、switch语句

(1)switch... case  ... default结构

```c
int i = 1;

switch(i) {
    case 1 :
        printf("星期一");
        break;
    case 2 :
        printf("星期二");
        break;
    case 3 :
        printf("星期三");
        break;
    case 4 :
        printf("星期四");
        break;
     case 5 :
        printf("星期五");
        break;
     case 6 :
        printf("星期六");
        break;
      default :
         printf("星期天");
         break;
}
```

(2)case分支：

​    每一个case后面跟的值都必须是一个整数类型常量或者整数类型常量表达式(或者宏),不能是一个变量

(3)break：case/default后面要跟一个break,防止渗透

(4)default：当前面的case分支都不满足条件时,走该分支

(5)switch内定义一个变量

```c
//定义天数和总金额变量
int day = 1, amount = 1;

switch(day) {
  //定义利息,根据天数变化而变化
  int interest;
        
    case 1 :
        interest = 1;
        break;
    case 2 :
        interest = 4;
        break;
    case 3 :
        interest = 7;
        break;
    case 4 :
        interest = 10;
        break;
    case 5 :
        interest = 12;
        break;
    case 6 :
        interest = 15;
        break;
    default :
        interest = 20;
        break;
}


/*
 * 当在switch的{}内定义变量时,必须在case分支之前声明(和初始化)
 * 该变量生命周期只存在于定义该变量的switch{}内
 */
```



### 二、迭代/循环语句

#### 1、while语句

(1)while(表达式)的执行条件

```c
 数值上：当的表达式值为非零时执行;为0时不执行
 
 逻辑上：当表达式结果为真(值为1)时执行,结果为假(值为0)时不执行
 
 使用上：从逻辑角度理解
```

(2)形式

```c
int i = 10;

while(i > 0) {
    i--;
}

//当while语句只执行一句时可以省略{},但是最好写上{}
while(i > 0) 
    i--;
```

(3)

(3)执行流程

  先判断,再根据判断结果决定是否执行循环。可以和for循环等效

(4)适用场景

   未知循环的次数时,适用while循环

(5)死循环

```
while(1) {
	//code
}

//声明一个变量(未初始化)
int status;

//另类死循环,因为每次的条件都是一个赋值表达式值都是1
while(status = 1) {
	//code
}
```



#### 2、do...while语句

(1)while(表达式)的执行条件

```c
 数值上：当的表达式值为非零时执行;为0时不执行

 逻辑上：当表达式结果为真(值为1)时执行,结果为假(值为0)时不执行
```

(2)形式

```
int i = 0;

do {
	i++;
} while(i < 10);
```

(3)执行流程

  先执行一次循环,接着判断,然后再根据结果决定是否执行循环



#### 3、for语句

(1)结构：

```c
for(A; B; C)

   A：初始化

   B：循环测试条件

   C：执行更新

   A、B、c都是表达式；成为控制表达式
```



(2)适用场景：已知循环次数(计数循环)

```c
for(表达式1; 表达式2; 表达式3) {
    
}

0、计数器：i
1、表达式1：给计数器赋值
2、表达式2：表示计数器范围
3、表达式3：递增计数器
```

例子：

```c
//C99
for(int i = 0; i < 15; i++) {
    printf("%d" , i);
}

//C99之前
int j;

for(j = 20; j > 0; j--) {
    printf("%d ", j);
}
```

(3)死循环

```c
for(; ; ) {
	//code
}
```



### 三、跳转语句

#### 1、continue

(1)跳过本轮循环,直接进入下一轮循环

(2)不会跳出当前循环

```c
for(int i = 0; i < 15; i++) {
    if(i % 2 == 0) {
        continue;
    }
    
    if(i == 13) {
        break;
    }
}
```

#### 2、break

(1)迭代：跳过当前循环(如果有多层嵌套循环,只是跳出break所在的那层循环)

```c
//打印行列
for(int i = 1; i < 11; i++) {
    for(int j = 1; j < 11; j++) {
        //当每行的列数达到7时,则跳出列的循环,继续下一行的循环
        if(j == 7) {
            break;
        }

        printf("第%d行第%d列  ", i, j);
    }

    printf("\n");
}
```

(2)switch：防止渗透

```c
int day = 1;

switch(day) {
    case 1 :
        printf("星期一");
        break;
    case 2 :
        printf("星期二");
        break;
    case 3 :
        printf("星期三");
        break;
    case 4 :
        printf("星期四");
        break;
     case 5 :
        printf("星期五");
        break;
     case 6 :
        printf("星期六");
        break;
      default :
         printf("星期天");
         break;
}
```



#### 3、return

(1)函数有返回值：返回一个是返回值数据类型的值

```c
int get_max(int i, int j) {
    if(i > j) {
        return i;
    } else {
        return j;
    }
}
```

(2)函数无返回值：中断函数中正在执行的流程,调用函数提前结束

```c
void malloc_array() {
    //分配一个长度为10的数组
    int *p = malloc(10 * sizeof(int));

    //判断是否是空指针
	if(p == NULL) {
        printf("系统分配内存失败");
        //结束函数正在执行流程
        return;
    }
    
    //给数组元素赋值
    for(int i = 0; i < 10; i++) {
        p[i] = i;
    }
}
```



#### 4、goto



### 四、表达式语句





### 五、复合语句(块)

(1)if.... else if .... else

(2)while .... else

(3)do... while ...

(4)其他                  

````c
int i = 2, j, k;

{
    i++;
    j = i * 2;
    k = j++;
}
````

### 六、空语句

#### 1、跳过输入行剩余部分

````c
int ch;

//输入内容：Linux\n(\n表示按下回车)
printf("请输入内容 :");

//第一次读取字符
ch = getchar();

//读取字符赋值给ch,再判断读取的字符是否是换行符'\n'
while((ch = getchar()) != '\n') {
    //空语句(只有一个分号;)
    ;
}
````



#### 2、跳过不定数量的空格

```c
int ch;

//内容：首字符            第一个非空格字符
printf("请输入内容 :");

//第一次读取字符
ch = getchar();

while((ch = getchar()) == ' ') {
    ;
}

//读取第一个字符后开始的非空格
putchar(ch);
```



### 七、读取字符函数函数

#### 1、getchar()函数

​    读取输入字符： 每次只读取一个字符,不会跳过任何一个字符

````c
输入内容(\n表示换行,代表输入结束)：SQL\n
字符：S、Q、L、\n

int ch;

printf("请输入内容 :");

//第一次读取：S
ch = getchar();
//显示S
putchar(ch);

//第二次读取：Q
ch = getchar();
//显示Q
putchar(ch);

//第三次读取：L
ch = getchar();
//显示L
putchar(ch);

//第四次读取：\n
ch = getchar();
//显示空白
putchar(ch);


//需求一、打印从第一次读取非\n字符到读取到\n之前的字符
while((ch = getchar()) != '\n') {
     putchar(ch);
}

//需求二：第一次读取字符后,跳过剩下所有的字符(不包括\n)
do {
    //读取字符赋值给ch
    ch = getchar();
    
//判断读取的字符是否是'\n'
} while(ch != '\n');

//读取字符赋值给ch,再判断读取的字符是否是'\n'
while((ch = getchar()) != '\n') {
    ;
}

````



#### 2、scanf()函数

(1)用途：读取输入键盘输入的内容

```c
键盘输入的数据先保存到缓冲区,当输入换行符\n时,键盘输入数据结束,开始读取数据到内存中

空白字符：空格字符''、水平制表字符\t、垂直制表字符、换页字符、换行字符\n
```

(2)读取字符：格式是%c, 不会主动跳过任何字符, 每次读取一个字符

(3)读取其他

```c
//读取其他类型时
//1、根据格式进行读取, 跳过若干个空白字符,从第一个非空白字符的位置开始读取
//2、当读取到不符合格式要求的数据或者换行符\n时将其放到缓冲区
//3、第一个非空白字符可以是+或者-(看做是一元正负运算符)

int i;
printf("请输入数字: ");
scanf("%d", &i);
printf("%d", i);

char ch;
printf("\n请输入字符");
scanf("%c", &ch);
printf("%c", ch);

/*
 * 情况一：假设输入的内容是3.14,实际缓冲区的数据是：3.14\n
 * 1、根据第一次读取的格式是十进制整数的d类型,所以读取3,剩下的.14\n放回到缓冲区
 * 2、根据第二次读取的格式是char字符类型,所以会读取一个字符即.,然后14\n放回缓冲区
 * 3、放回缓冲区的14\n供下次读取
 */

/*
 * 情况二：假设输入的内容是3,实际缓冲区的数据是：3\n
 * 1、根据第一次读取的格式是十进制整数的d类型,所以读取3,剩下的\n放回到缓冲区
 * 2、根据第二次读取的格式是char字符类型,所以会读取一个字符即\n,然后缓冲区是空的
 */
```
