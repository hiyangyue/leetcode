# 002 整数反转
给出一个 32 位的有符号整数，你需要将这个整数中每位上的数字进行反转。

示例1：
> 输入: 123
> 输出: 321

示例2：
> 输入: -123
> 输出: -321

示例3：
> 输入: 120
> 输出: 21

注意:
假设我们的环境只能存储得下 32 位的有符号整数，则其数值范围为 [−231,  231 − 1]。请根据这个假设，如果反转后整数溢出那么就返回 0。

---
### 突破点
1. 数字的反转
2. 溢出的条件

### 思路
* 通过循环将每一个数都分开
* 溢出的判定条件： > MAX_VALUE or < MAX_VALUE

### 代码 

```
 public int reverse(int x) {
        int rev = 0;
        while(x != 0) {
            int pop = x % 10;
            x = x / 10;
            if(rev > Integer.MAX_VALUE / 10 || (rev == Integer.MAX_VALUE && pop > 7)) return 0;
            if(rev < Integer.MIN_VALUE / 10 || (rev == Integer.MIN_VALUE && pop < -8)) return 0;
            rev = rev * 10 + pop;
        }
        return rev;
    }
```
