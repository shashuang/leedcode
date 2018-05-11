# 问题分析 #

    编写程序判断给定的数是否为丑数。

    丑数就是只包含质因子 2, 3, 5 的正整数。例如， 6, 8 是丑数，而 14 不是，因为它包含了另外一个质因子 7。

    注意：

    1、1也可以被当做丑数。
    2、输入不会超过32位整数的范围。 

# 代码实现 #
```C
bool isUgly(int num) {
    while(num>=2)
    {
        if(num%2==0)
        {
            num=num/2;
        }
        else if(num%3==0)
        {
            num=num/3;
        }
        else if(num%5==0)
        {
            num=num/5;
        }
        else
        {
            return false;
        }
    }
    return num==1;
}
```
# 总结体会 #
     验证某一个数是否为丑数，要求只含有2、3、5质因子，也就是该数应该是2、3、5这三个数的乘积，

     不能存在其他数。要判断否被这三个数整除，如果能整除，则继续判断除数是否被整除。如果都被整

     除，则说明是丑数，返回TRUE，不能整除，返回FALSE。