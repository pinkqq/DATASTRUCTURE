# DATASTRUCTURE
数据结构
[TOC]
## 约瑟夫环（递归）
假设问题是从n个人编号分别为0...n-1，取第k个，则第k个人编号为k-1的淘汰，剩下的编号为  0,1,2,3...k-2,k,k+1,k+2...此时因为从刚刚淘汰那个人的下一个开始数起，因此重新编号把k号设置为0,则
k    0
k+1 1
...
0 n-k
1 n-k+1
假设已经求得了n-1个人情况下的最终胜利者保存在f[n-1]中，则毫无疑问，该胜利者还原到原来的真正编号即为 (f[n-1]+k)%n （因为第二轮重新编号的时候，相当于把每个人的编号都减了k，因此重新+k即可恢复到原来编号）。
由此，我们可以想象，当最终只剩下一个人的时候，该人即为胜利者，此时重新编号，因为只有一个人，所以此时f[1]=0

转自：http://www.cnblogs.com/kkrisen/p/3569281.html#undefined*/

## 逆波兰计算器（栈）
计算机在计算普通表达式时，要对运算优先级用递归进行判断，对于更为复杂的表达式会使计算机运算效率变低甚至崩溃。而逆波兰表达式只需要进行简单的入栈出栈操作就可以完成任何普通表达式的运算。
### 逆波兰表达式逻辑实现
如果当前字符为变量或者为数字，则压栈，如果是运算符，则将栈顶两个元素弹出作相应运算，结果再入栈，最后当表达式扫描完后，栈里的就是结果。
### 普通表达式——>逆波兰表达式
(1)          a+b——>a b +

(2)    a+(b-c)——>a b c - +

(3)a+(b-c)*d——>a b c -  d * + 

### 规则
中缀表达式a + b*c + (d * e + f) * g，其转换成后缀表达式则为a b c * + d e * f  + g * +。

转换过程需要用到栈，具体过程如下：

1）如果遇到操作数，我们就直接将其输出。

2）如果遇到操作符，则我们将其放入到栈中，遇到左括号时我们也将其放入栈中。

3）如果遇到一个右括号，则将栈元素弹出，将弹出的操作符输出直到遇到左括号为止。注意，左括号只弹出并不输出。

4）如果遇到任何其他的操作符，如（“+”， “*”，“（”）等，从栈中弹出元素直到遇到发现更低优先级的元素(或者栈为空)为止。弹出完这些元素后，才将遇到的操作符压入到栈中。有一点需要注意，只有在遇到" ) "的情况下我们才弹出" ( "，其他情况我们都不会弹出" ( "。

5）如果我们读到了输入的末尾，则将栈中所有元素依次弹出。
##八皇后问题
在8*8国际象棋棋盘上，要求在每一行放置一个皇后，且能做到在竖方向，斜方向都没有冲突。
##KMP算法
1）暴力匹配算法
2）next 数组
<a href="http://www.ruanyifeng.com/blog/2013/05/Knuth%E2%80%93Morris%E2%80%93Pratt_algorithm.html" >字符串匹配的KMP算法 - 阮一峰的网络日志</a>