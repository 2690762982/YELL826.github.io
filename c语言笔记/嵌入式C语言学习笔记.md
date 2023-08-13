替代a*2 = a<<1;

///////////////////////////////////////

a,b交换； swap（a，b）

a = a ^ b;
b = a ^ b;
a = a ^ b;

////////////////////////////////////////

if(a ^ b){

相当于a！=b

}

### [三目运算](https://so.csdn.net/so/search?q=三目运算&spm=1001.2101.3001.7020)符

结果 = <判别式> ? <代码1> : <代码2>;



![image-20230801082249840](C:\Users\26907\AppData\Roaming\Typora\typora-user-images\image-20230801082249840.png)





![image-20230802115900143](C:\Users\26907\AppData\Roaming\Typora\typora-user-images\image-20230802115900143.png)





一、定义方面：

1、int为整数型，用于定义整数类型的数据 。

2、float为单精度[浮点型](https://so.csdn.net/so/search?q=浮点型&spm=1001.2101.3001.7020)，能准确到小数点后六位 。

3、double为双精度浮点型，能准确到小数点都十二位 。

4、char为[字符型](https://so.csdn.net/so/search?q=字符型&spm=1001.2101.3001.7020)，用于定义字符类型的数据。

二、内存占据：

1、int 的内存大小是4 个byte。

2、float 内存大小是4 个byte。

3、double 的内存大小是8 个byte。

4、char 的内存大小是1 个byte。

基本数据类型表如下：

[![img](https://gss0.baidu.com/-Po3dSag_xI4khGko9WTAnF6hhy/zhidao/wh%3D600%2C800/sign=81f0bd65edfe9925cb596156049872e7/023b5bb5c9ea15ce8d0a45a9bb003af33b87b2ae.jpg)](https://gss0.baidu.com/-Po3dSag_xI4khGko9WTAnF6hhy/zhidao/pic/item/023b5bb5c9ea15ce8d0a45a9bb003af33b87b2ae.jpg)

三、表示的数据范围：

1、int：数的范围为-（2的31次方-1）到（2的31次方-1），数字为-2 147 483 647~2 147 483 647。

2、double：表示的范围为+1.111111111111111111111*2^1023（1.后面52个1）为1.7*10^308。负数亦然。

3、float：整数极限为3.4*10^38，负数亦然。

4、char：-128- 127。



## int8 和 uint8

[int8](https://so.csdn.net/so/search?q=int8&spm=1001.2101.3001.7020)就是用8个比特位来保存整数，第一位用来表示符号，索引int8的整数范围是-127到127；

uint8表示无符号整数，没有符号位，8个比特位全部用来表示整数，所以数据范围是0到255。



在C语言中，`return`语句用于从函数中返回值。`return;`表示从函数中立即返回，不返回任何值。`return 0;`表示从函数中返回一个整数值0，通常用于表示程序执行成功。`return -1;`表示从函数中返回一个整数值-1，通常用于表示程序执行失败。`return 1;`表示从函数中返回一个整数值1，可以用于表示程序执行成功并返回某种特定的结果。

下面是一些例子：

1. `return;`的例子：
```c
void functionWithoutReturnValue() {
    // 无返回值的函数
    printf("Hello, World!\n");
    return; // 从函数中立即返回
}
```

2. `return 0;`的例子：
```c
i nt functionWithReturnValue() {
    // 返回整数值的函数
    int result = 10 + 5;
    return result; // 返回结果为15
}

int main() {
    int value = functionWithReturnValue(); // 调用函数并获取返回值
    printf("The result is: %d\n", value);
    return 0; // 程序执行成功返回0
}
```

3. `return -1;`的例子：
```c
int search(int arr[], int n, int target) {
    // 在数组中查找目标值的函数
    for (int i = 0; i < n; i++) {
        if (arr[i] == target) {  
            return i; // 找到目标值，返回索引
        }
    }
    return -1; // 未找到目标值，返回-1
}

int main() {
    int arr[] = {1, 2, 3, 4, 5};
    int target = 6;
    int result = search(arr, 5, target); // 调用函数并获取返回值
    if (result != -1) {
        printf("The target is found at index %d\n", result);
    } else {
        printf("The target is not found\n");
    }
    return 0;
}
```

4. `return 1;`的例子：
```c
int calculateSum(int a, int b, int *sum) {
    // 计算两个数的和，并将结果存储在指针sum中
    *sum = a + b;
    return 1; // 返回1表示计算成功
}

int main() {
    int a = 5, b = 3, sum;
    if (calculateSum(a, b, &sum) == 1) { // 调用函数并检查返回值
        printf("The sum of %d and %d is %d\n", a, b, sum);
    } else {
        printf("Failed to calculate the sum\n");
    }
    return 0;
}
```

这些例子展示了不同类型的`return`语句的用法和意义。根据实际需求，可以选择适当的`return`语句来返回函数执行的结果



​	**while(1)和for(;;)异同点**

这里先说一下结论，然后再验证验证结论。

**1、相同点**

作用和效果都一样：都是实现无限循环的功能。

**2、不同点**

**while(1)：**其中括号里面是一个条件，程序会判断真假。而括号里面的“1”永远是一个“真值”。

其中，每一次循环，编译器都要判断常量1是不是等于零。

**for(;;)：**这两个;;空语句，编译器一般会优化掉的，直接进入死循环。

根据上面的描述，你可能会觉得：while(1) 比 for(;;) 要做更多事，汇编代码更多，代码量也更大

#                                                                           const

1、预编译指令只是对值进行简单的替换，不能进行类型检查

2、可以保护被修饰的东西，防止意外修改，增强程序的健壮性

3、编译器通常不为普通const常量分配存储空间，而是将它们保存在符号表中，这使得它成为一个编译期间的常量，没有了存储与读内存的操作，使得它的效率也很高。

​									const int n=5;
​									int const n=5;

这两种写法是一样的，都是表示变量n的值不能被改变了，需要注意的是，用const修饰变量时，一定要给变脸初始化，否则之后就不能再进行赋值了。

![image-20230801131826231](C:\Users\26907\AppData\Roaming\Typora\typora-user-images\image-20230801131826231.png)

# 																memcmp

`memcmp`是一个用于比较内存块的函数。它用于比较两个内存块的内容是否相等，并返回一个整数来表示比较结果。

- 如果`ptr1`和`ptr2`的内容相等，则返回0。

- 如果`ptr1`的内容大于`ptr2`的内容，则返回一个正数。

- 如果`ptr1`的内容小于`ptr2`的内容，则返回一个负数。

  ```c
  #include <stdio.h>
  #include <string.h>
  
  int main() {
      // 例子1：比较两个字符串是否相等
      char str1[] = "hello";
      char str2[] = "hello";
      int result = memcmp(str1, str2, sizeof(str1));
      if (result == 0) {
          printf("str1 and str2 are equal\n");
      } else {
          printf("str1 and str2 are not equal\n");
      }
  
      // 例子2：比较两个整数数组是否相等
      int arr1[] = {1, 2, 3, 4, 5};
      int arr2[] = {1, 2, 3, 4, 5};
      result = memcmp(arr1, arr2, sizeof(arr1));
      if (result == 0) {
          printf("arr1 and arr2 are equal\n");
      } else {
          printf("arr1 and arr2 are not equal\n");
      }
  
      // 例子3：比较部分内存块
      char str3[] = "hello";
      char str4[] = "world";
      result = memcmp(str3, str4, 3);
      if (result == 0) {
          printf("The first 3 characters of str3 and str4 are equal\n");
      } else {
          printf("The first 3 characters of str3 and str4 are not equal\n");
      }
  
      return 0;
  }
  ```

  # 															链表
  
  ![image-20230803091349488](C:\Users\26907\AppData\Roaming\Typora\typora-user-images\image-20230803091349488.png)
  
  

```c
#include "stdio.h"
   struct stu{
    int z;
    char x;
    struct stu *next;
};

   int main(){
       struct stu a,b,c,*head;
       a.z=1;
       a.x=2;
       b.z=1;
       b.x=2;
       head=&a;
       a.next=&b;
       b.next=&c;

     while(head !=NULL) {

     printf("%d ,%lf", head->z, head->x);//把头结点往后移输出
     head = head->next;
    }
}
```



![image-20230803104242651](C:\Users\26907\AppData\Roaming\Typora\typora-user-images\image-20230803104242651.png)

