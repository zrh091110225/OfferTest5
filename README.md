# 剑指Offer笔试题5

*题目来源：*[牛客网](http://www.nowcoder.com/ta/coding-interviews?page=1)

### 题目一 扑克牌顺子

**描述:**  
LL今天心情特别好,因为他去买了一副扑克牌,发现里面居然有2个大王,2个小王(一副牌原本是54张^_^)...他随机从中抽出了5张牌,想测测自己的手气,看看能不能抽到顺子,如果抽到的话,他决定去买体育彩票,嘿嘿！！“红心A,黑桃3,小王,大王,方片5”,“Oh My God!”不是顺子.....LL不高兴了,他想了想,决定大\小 王可以看成任何数字,并且A看作1,J为11,Q为12,K为13。上面的5张牌就可以变成“1,2,3,4,5”(大小王分别看作2和4),“So Lucky!”。LL决定去买体育彩票啦。 现在,要求你使用这幅牌模拟上面的过程,然后告诉我们LL的运气如何。为了方便起见,你可以认为大小王是0。

**解题思路:** [代码](https://github.com/ToryangChen/OfferTest5/blob/master/src/CardContinue.java)  

 * 排序数组,使用快排;
 * 统计数组中0的个数;(即大小王的个数,不能超过4)
 * 统计剩下的相邻的数之间空缺的总数,是否等于0的个数;
 
### 题目二 数据流中的中位数

**描述:**  
如何得到一个数据流中的中位数？如果从数据流中读出奇数个数值，那么中位数就是所有数值排序之后位于中间的数值。如果从数据流中读出偶数个数值，那么中位数就是所有数值排序之后中间两个数的平均值。

**解题思路:** [代码](https://github.com/ToryangChen/OfferTest5/blob/master/src/GetMidInStream.java)  
这个题目需求是是模拟一个输入数据流:我们可以每次insert一个数据;进行排序后返回已经插入数据的中位数;  
代码中将输入数据流放进一个数组中,使用堆排序,对每个插入数据进行排序;最后返回数组的中位数;

### 题目三 矩阵中的路径

**描述:**  
请设计一个函数，用来判断在一个矩阵中是否存在一条包含某字符串所有字符的路径。路径可以从矩阵中的任意一个格子开始，每一步可以在矩阵中向左，向右，向上，向下移动一个格子。如果一条路径经过了矩阵中的某一个格子，则该路径不能再进入该格子。 例如 a b c e s f c s a d e e 矩阵中包含一条字符串"bcced"的路径，但是矩阵中不包含"abcb"路径，因为字符串的第一个字符b占据了矩阵中的第一行第二个格子之后，路径不能再次进入该格子。

**解题思路:** [代码](https://github.com/ToryangChen/OfferTest5/blob/master/src/HasPathInMatrix.java)  

   * 从矩阵某个外围位置开始,上下左右进行遍历查找,看是否能够匹配得到需要查找的字符串;
   * 使用回溯法上下左右进行递归尝试;

### 题目四 二叉搜索树的第k个结点 

**描述:**  
 给定一颗二叉搜索树，请找出其中的第k大的结点。 例如:  
     5  
    / \  
    3 7  
   /\ /\  
  2 4 6 8 中，  
 按结点数值大小顺序第三个结点的值为4。


**解题思路:** [代码](https://github.com/ToryangChen/OfferTest5/blob/master/src/KthNodeInTree.java)  

   * 二叉搜索树,中序遍历后可以得到一个升序序列;
   * 将升序序列存入一个栈中,pop出栈,取第k个结点返回;
   
### 题目五 正则表达式匹配

**描述:**  
请实现一个函数用来匹配包括'.'和'*'的正则表达式。模式中的字符'.'表示任意一个字符，而'*'表示它前面的字符可以出现任意次（包含0次）。 在本题中，匹配是指字符串的所有字符匹配整个模式。例如，字符串"aaa"与模式"a.a"和"ab*ac*a"匹配，但是与"aa.a"和"ab*a"均不匹配


**解题思路:** [代码](https://github.com/ToryangChen/OfferTest5/blob/master/src/Match.java)  
*代码中有详细注释,这里不赘述;* 
   
### 题目六 滑动窗口的最大值

**描述:**  
给定一个数组和滑动窗口的大小，找出所有滑动窗口里数值的最大值。例如，如果输入数组{2,3,4,2,6,2,5,1}及滑动窗口的大小3，那么一共存在6个滑动窗口，他们的最大值分别为{4,4,6,6,6,5}； 针对数组{2,3,4,2,6,2,5,1}的滑动窗口有以下6个： {[2,3,4],2,6,2,5,1}， {2,[3,4,2],6,2,5,1}， {2,3,[4,2,6],2,5,1}， {2,3,4,[2,6,2],5,1}， {2,3,4,2,[6,2,5],1}， {2,3,4,2,6,[2,5,1]}。

**解题思路:** [代码](https://github.com/ToryangChen/OfferTest5/blob/master/src/MaxInWindows.java)  
题目不难,使用循环嵌套就好,找出窗口list,取最大值就好;

### 题目七 机器人的运动范围

**描述:**  
地上有一个m行和n列的方格。一个机器人从坐标0,0的格子开始移动，每一次只能向左，右，上，下四个方向移动一格，但是不能进入行坐标和列坐标的数位之和大于k的格子。 例如，当k为18时，机器人能够进入方格（35,37），因为3+5+3+7 = 18。但是，它不能进入方格（35,38），因为3+5+3+8 = 19。请问该机器人能够达到多少个格子？

**解题思路:** [代码](https://github.com/ToryangChen/OfferTest5/blob/master/src/MoveingCount.java)  

*没看懂题目的问题,先把代码贴出来,持续更新!*

### 题目八 机器人的运动范围

**描述:**  
地上有一个m行和n列的方格。一个机器人从坐标0,0的格子开始移动，每一次只能向左，右，上，下四个方向移动一格，但是不能进入行坐标和列坐标的数位之和大于k的格子。 例如，当k为18时，机器人能够进入方格（35,37），因为3+5+3+7 = 18。但是，它不能进入方格（35,38），因为3+5+3+8 = 19。请问该机器人能够达到多少个格子？

**解题思路:** [代码](https://github.com/ToryangChen/OfferTest5/blob/master/src/MoveingCount.java)  

*没看懂题目的问题,先把代码贴出来,持续更新!*

### 题目九 二叉树的下一个结点

**描述:**  
给定一个二叉树和其中的一个结点，请找出中序遍历顺序的下一个结点并且返回。注意，树中的结点不仅包含左右子结点，同时包含指向父结点的指针。

**解题思路:** [代码](https://github.com/ToryangChen/OfferTest5/blob/master/src/NextTreeNode.java)  

  * 如果有右子树，则找右子树的最左节点;
  * 没右子树，则找第一个当前节点是父节点左孩子的节点;
  
### 题目十 数组中只出现一次的数字

**描述:**  
一个整型数组里除了两个数字之外，其他的数字都出现了两次。请写程序找出这两个只出现一次的数字。

**解题思路:** [代码](https://github.com/ToryangChen/OfferTest5/blob/master/src/NumberAppearOnce.java)  

  * 将数组中的数进行异或,得到只出现一次的两个数异或的结果;
  * 异或的结果必定有大于等于1位为1,去第1个为1的位数n;
  * 将数组中的数按照第n位是否为1分为两个数组,只出现一次的数也分别在这两个数组中;
  * 将两个数组各自异或,两个数分别得到的两个数为只出现一次的数字;
  
### 题目十一 按照之字形打印二叉树

**描述:**  
请实现一个函数按照之字形打印二叉树，即第一行按照从左到右的顺序打印，第二层按照从右至左的顺序打印，第三行按照从左到右的顺序打印，其他行以此类推。

**解题思路:** [代码](https://github.com/ToryangChen/OfferTest5/blob/master/src/PrintTree.java)  

  * 先进行层序遍历;
  * 在遍历每一层的时候看这一层是否需要从右往左打印;
  
### 题目十二 序列化二叉树

**描述:**  
请实现两个函数，分别用来序列化和反序列化二叉树

**解题思路:** [代码](https://github.com/ToryangChen/OfferTest5/blob/master/src/SerializeTree.java)  

  * 根据给出的返回值类型可知,序列化就是:需要将一个二叉树序列化成为一个String类型;
  * 反序列化就是将序列化返回的String字符串返回到原二叉树;
  
### 题目十三 对称的二叉树

**描述:**  
请实现一个函数，用来判断一颗二叉树是不是对称的。注意，如果一个二叉树同此二叉树的镜像是同样的，定义其为对称的。

**解题思路:** [代码](https://github.com/ToryangChen/OfferTest5/blob/master/src/SymmetricalTree.java)  
 使用递归的方法:
   
 * 左子树的左子树和右子树的右子树相同
 * 左子树的右子树和右子树的左子树相同

### 题目十四 二叉搜索数与双向链表

**描述:**  
输入一棵二叉搜索树，将该二叉搜索树转换成一个排序的双向链表。要求不能创建任何新的结点，只能调整树中结点指针的指向。

**解题思路:** [代码](https://github.com/ToryangChen/OfferTest5/blob/master/src/Tree2List.java)  

  * 中序遍历,将顺序链表存到list中;
  * 针对list中的TreeNode,对前后指针进行修改,使node.left指向前一个,node.right指向后一个;

### 题目十五 丑数

**描述:**  
把只包含因子2、3和5的数称作丑数（Ugly Number）。例如6、8都是丑数，但14不是，因为它包含因子7。 习惯上我们把1当做是第一个丑数。求按从小到大的顺序的第N个丑数。

**解题思路:** [代码](https://github.com/ToryangChen/OfferTest5/blob/master/src/UglyNumber.java)  
 第一个丑数是1,分别用2,3,5去乘已知的丑数,所得的丑数继续添加到丑数的数组中;