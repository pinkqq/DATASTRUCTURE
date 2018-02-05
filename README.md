# DATASTRUCTURE
数据结构

###约瑟夫环（递归）
假设问题是从n个人编号分别为0...n-1，取第k个，则第k个人编号为k-1的淘汰，剩下的编号为  0,1,2,3...k-2,k,k+1,k+2...此时因为从刚刚淘汰那个人的下一个开始数起，因此重新编号把k号设置为0,则
k    0
k+1 1
...
0 n-k
1 n-k+1
假设已经求得了n-1个人情况下的最终胜利者保存在f[n-1]中，则毫无疑问，该胜利者还原到原来的真正编号即为 (f[n-1]+k)%n （因为第二轮重新编号的时候，相当于把每个人的编号都减了k，因此重新+k即可恢复到原来编号）。
由此，我们可以想象，当最终只剩下一个人的时候，该人即为胜利者，此时重新编号，因为只有一个人，所以此时f[1]=0

转自：http://www.cnblogs.com/kkrisen/p/3569281.html#undefined*/

###逆波兰计算器（栈）
计算机在计算普通表达式时，要对运算优先级用递归进行判断，对于更为复杂的表达式会使计算机运算效率变低甚至崩溃。而逆波兰表达式只需要进行简单的入栈出栈操作就可以完成任何普通表达式的运算。
#####逆波兰表达式逻辑实现
如果当前字符为变量或者为数字，则压栈，如果是运算符，则将栈顶两个元素弹出作相应运算，结果再入栈，最后当表达式扫描完后，栈里的就是结果。
#####普通表达式——>逆波兰表达式
(1)          a+b——>a b +

(2)    a+(b-c)——>a b c - +

(3)a+(b-c)*d——>a b c -  d * + 