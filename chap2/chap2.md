## 2.1 写出下面每一种单词的正则表达式。

### a. 字母表 {a, b, c} 上满足后面条件的字符串：首次出现的 a 位于首次出现的 b 之前。

#### 解答

`[ac]*[bc]*`

### b. 字母表 {a, b, c} 上由偶数个 a 组成的字符串。

#### 解答
`([bc]*(a[bc]*a)*)*`

### c. 是 4 的倍数的二进制数。

#### 解答

`[10]+00`

### d. 大于 101001 的二进制数。

#### 解答

`1[01]{6,}|11[01]{4}|1011[01]{2}|10101[10]`

### e. 字母表 {a, b, c} 上不包含连续子串 baa 的字符串。

#### 解答

`[ac]*b*a?[bc]*`

### f. C 语言中非负整常数组成的语言，其中以 0 开头的数是八进制常数。

#### 解答

 `0[0-7]*|[1-9][0-9]*`

### g. 使得方程 ![a^n+b^n=c^n](https://render.githubusercontent.com/render/math?math=a%5En%2Bb%5En%3Dc%5En)

#### 解答

`1|10`

## 2.2 对于下列表描述，试解释为什么不存在对应的正则表达式。

### a. 由 a 和 b 组成的字符串，其中 a 的个数要多于 b。
#### 解答
因为正则表达式没有记忆数量的能力。

### b. 由 a 和 b 组成的回文字符串（顺读与倒读相同）。
#### 解答
因为正则表达式没有记忆数量的能力。

### c. 语法上正确的 C 程序。
#### 解答
因为正则表达式无法表达递归嵌套结构。
## 2.3 用自然语言描述下述有限状态自动机识别的语言。

#### a.
<!-- This is the original graph
digraph G {

   start[label= "", shape=none,height=.0,width=.0]
   {node[shape=circle];1;2;3;4;6;7;8;9}
   {node[shape=doublecircle];10}
   
   start->1
   1->2[label="0"]
   1->6[label="1"]
   2->3[label="1"]
   2->7[label="0"]
   3->4[label="1"]
   3->8[label="0"]
   4->9[label="0"]
   4->10[label="1"]
   6->7[label="0"]
   6->7[label="1"]
   7->8[label="0"]
   7->8[label="1"]
   8->10[label="0"]
   8->10[label="1"]
   
   rankdir="LR"
}
-->
![digraph](https://g.gravizo.com/svg?digraph%20G%20%7B%0A%0A%20%20%20start%5Blabel%3D%20%22%22%2C%20shape%3Dnone%2Cheight%3D.0%2Cwidth%3D.0%5D%0A%20%20%20%7Bnode%5Bshape%3Dcircle%5D%3B1%3B2%3B3%3B4%3B6%3B7%3B8%3B9%7D%0A%20%20%20%7Bnode%5Bshape%3Ddoublecircle%5D%3B10%7D%0A%20%20%20%0A%20%20%20start-%3E1%0A%20%20%201-%3E2%5Blabel%3D%220%22%5D%0A%20%20%201-%3E6%5Blabel%3D%221%22%5D%0A%20%20%202-%3E3%5Blabel%3D%221%22%5D%0A%20%20%202-%3E7%5Blabel%3D%220%22%5D%0A%20%20%203-%3E4%5Blabel%3D%221%22%5D%0A%20%20%203-%3E8%5Blabel%3D%220%22%5D%0A%20%20%204-%3E9%5Blabel%3D%220%22%5D%0A%20%20%204-%3E10%5Blabel%3D%221%22%5D%0A%20%20%206-%3E7%5Blabel%3D%220%22%5D%0A%20%20%206-%3E7%5Blabel%3D%221%22%5D%0A%20%20%207-%3E8%5Blabel%3D%220%22%5D%0A%20%20%207-%3E8%5Blabel%3D%221%22%5D%0A%20%20%208-%3E10%5Blabel%3D%220%22%5D%0A%20%20%208-%3E10%5Blabel%3D%221%22%5D%0A%20%20%20%0A%20%20%20rankdir%3D%22LR%22%0A%7D)

#### 解答

描述了不为 0110 的 4 位二进制字符串。




### b.
<!-- This is the original graph
digraph G {

   start[label= "", shape=none,height=.0,width=.0]
   {node[shape=circle];" ";"   ";"    ";"     ";}
   {node[shape=doublecircle];"  "}
  
   start->" "
   " "->"  "[label="a"]
   "  "->"   "[label="a"]
   "   "->"    "[label="a"]
   "    "->"     "[label="a"]
   "     "->" "[label="a"]
   
   rankdir="LR";
}
-->
![digraph](https://g.gravizo.com/svg?digraph%20G%20%7B%0A%0A%20%20%20start%5Blabel%3D%20%22%22%2C%20shape%3Dnone%2Cheight%3D.0%2Cwidth%3D.0%5D%0A%20%20%20%7Bnode%5Bshape%3Dcircle%5D%3B%22%20%22%3B%22%20%20%20%22%3B%22%20%20%20%20%22%3B%22%20%20%20%20%20%22%3B%7D%0A%20%20%20%7Bnode%5Bshape%3Ddoublecircle%5D%3B%22%20%20%22%7D%0A%20%20%0A%20%20%20start-%3E%22%20%22%0A%20%20%20%22%20%22-%3E%22%20%20%22%5Blabel%3D%22a%22%5D%0A%20%20%20%22%20%20%22-%3E%22%20%20%20%22%5Blabel%3D%22a%22%5D%0A%20%20%20%22%20%20%20%22-%3E%22%20%20%20%20%22%5Blabel%3D%22a%22%5D%0A%20%20%20%22%20%20%20%20%22-%3E%22%20%20%20%20%20%22%5Blabel%3D%22a%22%5D%0A%20%20%20%22%20%20%20%20%20%22-%3E%22%20%22%5Blabel%3D%22a%22%5D%0A%20%20%20%0A%20%20%20rankdir%3D%22LR%22%3B%0A%7D)


#### 解答

描述了 ![5^n+1(n∈N^*)](https://render.githubusercontent.com/render/math?math=5%5En%2B1(n%20%5cin%20%5cN%5e*)) 个 a。

### c.
<!-- This is the original graph

digraph G {
   start[label= "", shape=none,height=.0,width=.0]
   
   {node[shape=circle];1;2}
   {node[shape=doublecircle];0}
   
   start->0
   0->0[label="0"]
   0->1[label="1"]
   1->0[label="1"]
   1->2[label="0"]
   2->1[label="0"]
   2->2[label="1"]
   rankdir="LR"
}
 -->
![digraph](https://g.gravizo.com/svg?digraph%20G%20%7B%0A%20%20%20start%5Blabel%3D%20%22%22%2C%20shape%3Dnone%2Cheight%3D.0%2Cwidth%3D.0%5D%0A%20%20%20%0A%20%20%20%7Bnode%5Bshape%3Dcircle%5D%3B1%3B2%7D%0A%20%20%20%7Bnode%5Bshape%3Ddoublecircle%5D%3B0%7D%0A%20%20%20%0A%20%20%20start-%3E0%0A%20%20%200-%3E0%5Blabel%3D%220%22%5D%0A%20%20%200-%3E1%5Blabel%3D%221%22%5D%0A%20%20%201-%3E0%5Blabel%3D%221%22%5D%0A%20%20%201-%3E2%5Blabel%3D%220%22%5D%0A%20%20%202-%3E1%5Blabel%3D%220%22%5D%0A%20%20%202-%3E2%5Blabel%3D%221%22%5D%0A%20%20%20rankdir%3D%22LR%22%0A%7D)

#### TODO


## 2.4 将下面两个正则表达式转换为非确定的有限自动机。

### a. `(if|then|else)`

#### 解答

<!-- This is the original graph
digraph G {

   start[label= "", shape=none,height=.0,width=.0]
   {node[shape=circle];1;2;4;5;6;8;9;10}
   {node[shape=doublecircle];3;7;11}
  
   start->1
   1->2[label="i"]
   2->3[label="f"]
   1->4[label="t"]
   4->5[label="h"]
   5->6[label="e"]
   6->7[label="n"]
   1->8[label="e"]
   8->9[label="l"]
   9->10[label="s"]
   10->11[label="e"]
   rankdir="LR";
}
-->
![digraph](https://g.gravizo.com/svg?digraph%20G%20%7B%0A%0A%20%20%20start%5Blabel%3D%20%22%22%2C%20shape%3Dnone%2Cheight%3D.0%2Cwidth%3D.0%5D%0A%20%20%20%7Bnode%5Bshape%3Dcircle%5D%3B1%3B2%3B4%3B5%3B6%3B8%3B9%3B10%7D%0A%20%20%20%7Bnode%5Bshape%3Ddoublecircle%5D%3B3%3B7%3B11%7D%0A%20%20%0A%20%20%20start-%3E1%0A%20%20%201-%3E2%5Blabel%3D%22i%22%5D%0A%20%20%202-%3E3%5Blabel%3D%22f%22%5D%0A%20%20%201-%3E4%5Blabel%3D%22t%22%5D%0A%20%20%204-%3E5%5Blabel%3D%22h%22%5D%0A%20%20%205-%3E6%5Blabel%3D%22e%22%5D%0A%20%20%206-%3E7%5Blabel%3D%22n%22%5D%0A%20%20%201-%3E8%5Blabel%3D%22e%22%5D%0A%20%20%208-%3E9%5Blabel%3D%22l%22%5D%0A%20%20%209-%3E10%5Blabel%3D%22s%22%5D%0A%20%20%2010-%3E11%5Blabel%3D%22e%22%5D%0A%20%20%20rankdir%3D%22LR%22%3B%0A%7D%0A)

### b. `a((b|a*c)x)*|x*a`

#### 解答

<!-- This is the original graph
digraph G {
   start[label= "", shape=none,height=.0,width=.0];
   {node[shape=circle];1;2;3;4;7};
   {node[shape=doublecircle];6;8}
   
   start->1
   1->2[label="a"]
   2->4[label="b"]
   2->3[label="ε"]
   3->3[label="a"]
   3->4[label="c"]
   4->6[label="x"]
   1->7[label="ε"]
   7->7[label="x"]
   7->8[label="a"]
   2->6[label="ε"]
   6->2[label="ε"]
   
   rankdir="LR";
}
-->
![digraph](https://g.gravizo.com/svg?digraph%20G%20%7B%0A%20%20%20start%5Blabel%3D%20%22%22%2C%20shape%3Dnone%2Cheight%3D.0%2Cwidth%3D.0%5D%3B%0A%20%20%20%7Bnode%5Bshape%3Dcircle%5D%3B1%3B2%3B3%3B4%3B7%7D%3B%0A%20%20%20%7Bnode%5Bshape%3Ddoublecircle%5D%3B6%3B8%7D%0A%20%20%20%0A%20%20%20start-%3E1%0A%20%20%201-%3E2%5Blabel%3D%22a%22%5D%0A%20%20%202-%3E4%5Blabel%3D%22b%22%5D%0A%20%20%202-%3E3%5Blabel%3D%22%CE%B5%22%5D%0A%20%20%203-%3E3%5Blabel%3D%22a%22%5D%0A%20%20%203-%3E4%5Blabel%3D%22c%22%5D%0A%20%20%204-%3E6%5Blabel%3D%22x%22%5D%0A%20%20%201-%3E7%5Blabel%3D%22%CE%B5%22%5D%0A%20%20%207-%3E7%5Blabel%3D%22x%22%5D%0A%20%20%207-%3E8%5Blabel%3D%22a%22%5D%0A%20%20%202-%3E6%5Blabel%3D%22%CE%B5%22%5D%0A%20%20%206-%3E2%5Blabel%3D%22%CE%B5%22%5D%0A%20%20%20%0A%20%20%20rankdir%3D%22LR%22%3B%0A%7D)

## 2.5 将下面的 NFA 转换为确定的有限自动机。

### a.

<!-- This is the original graph
digraph G {

   start[label= "", shape=none,height=.0,width=.0]
   {node[shape=circle];1;2;3;4;5;6}
   {node[shape=doublecircle];7}
  
   start->1
   1->2[label="ε"]
   2->3[label="ε"]
   3->4[label="ε"]
   4->1[label="ε"]
   1->5[label="x"]
   5->2[label="z"]
   5->6[label="ε"]
   2->6[label="y"]
   6->7[label="ε"]
   
   rankdir="LR";
}
-->
![digraph](https://g.gravizo.com/svg?%0Adigraph%20G%20%7B%0A%0A%20%20%20start%5Blabel%3D%20%22%22%2C%20shape%3Dnone%2Cheight%3D.0%2Cwidth%3D.0%5D%0A%20%20%20%7Bnode%5Bshape%3Dcircle%5D%3B1%3B2%3B3%3B4%3B5%3B6%7D%0A%20%20%20%7Bnode%5Bshape%3Ddoublecircle%5D%3B7%7D%0A%20%20%0A%20%20%20start-%3E1%0A%20%20%201-%3E2%5Blabel%3D%22%CE%B5%22%5D%0A%20%20%202-%3E3%5Blabel%3D%22%CE%B5%22%5D%0A%20%20%203-%3E4%5Blabel%3D%22%CE%B5%22%5D%0A%20%20%204-%3E1%5Blabel%3D%22%CE%B5%22%5D%0A%20%20%201-%3E5%5Blabel%3D%22x%22%5D%0A%20%20%205-%3E2%5Blabel%3D%22z%22%5D%0A%20%20%205-%3E6%5Blabel%3D%22%CE%B5%22%5D%0A%20%20%202-%3E6%5Blabel%3D%22y%22%5D%0A%20%20%206-%3E7%5Blabel%3D%22%CE%B5%22%5D%0A%20%20%20%0A%20%20%20rankdir%3D%22LR%22%3B%0A%7D)

#### 解答

<!-- This is the original graph
digraph G {
   start[label= "", shape=none,height=.0,width=.0]
   {node[shape=circle];"1,2,3,4"}
   {node[shape=doublecircle];"5,6,7";"6,7"}
   start->"1,2,3,4"
   "1,2,3,4"->"5,6,7"[label="x"]
   "1,2,3,4"->"6,7"[label="y"]
   "5,6,7"->"1,2,3,4"[label="z"]
  
   rankdir="LR"
}
-->
![digraph](https://g.gravizo.com/svg?digraph%20G%20%7B%0A%20%20%20start%5Blabel%3D%20%22%22%2C%20shape%3Dnone%2Cheight%3D.0%2Cwidth%3D.0%5D%0A%20%20%20%7Bnode%5Bshape%3Dcircle%5D%3B%221%2C2%2C3%2C4%22%7D%0A%20%20%20%7Bnode%5Bshape%3Ddoublecircle%5D%3B%225%2C6%2C7%22%3B%226%2C7%22%7D%0A%20%20%20start-%3E%221%2C2%2C3%2C4%22%0A%20%20%20%221%2C2%2C3%2C4%22-%3E%225%2C6%2C7%22%5Blabel%3D%22x%22%5D%0A%20%20%20%221%2C2%2C3%2C4%22-%3E%226%2C7%22%5Blabel%3D%22y%22%5D%0A%20%20%20%225%2C6%2C7%22-%3E%221%2C2%2C3%2C4%22%5Blabel%3D%22z%22%5D%0A%20%20%0A%20%20%20rankdir%3D%22LR%22%0A%7D)

### b.

<!-- This is the original graph
digraph B {
   start[label= "", shape=none,height=.0,width=.0]
   {node[shape=circle];1;2;3;4}
   {node[shape=doublecircle];6}
   start->1
   1->1[label="a"]
   1->1[label="b"]
   1->2[label="a"]
   2->3[label="a"]
   2->3[label="b"]
   3->4[label="a"]
   3->4[label="b"]
   4->5[label="a"]
   4->5[label="b"]
   5->6[label="a"]
   5->6[label="b"]
   rankdir="LR"
}
-->
![digraph](https://g.gravizo.com/svg?digraph%20G%20%7B%0A%20%20%20start%5Blabel%3D%20%22%22%2C%20shape%3Dnone%2Cheight%3D.0%2Cwidth%3D.0%5D%0A%20%20%20%7Bnode%5Bshape%3Dcircle%5D%3B1%3B2%3B3%3B4%7D%0A%20%20%20%7Bnode%5Bshape%3Ddoublecircle%5D%3B6%7D%0A%20%20%20start-%3E1%0A%20%20%201-%3E1%5Blabel%3D%22a%22%5D%0A%20%20%201-%3E1%5Blabel%3D%22b%22%5D%0A%20%20%201-%3E2%5Blabel%3D%22a%22%5D%0A%20%20%202-%3E3%5Blabel%3D%22a%22%5D%0A%20%20%202-%3E3%5Blabel%3D%22b%22%5D%0A%20%20%203-%3E4%5Blabel%3D%22a%22%5D%0A%20%20%203-%3E4%5Blabel%3D%22b%22%5D%0A%20%20%204-%3E5%5Blabel%3D%22a%22%5D%0A%20%20%204-%3E5%5Blabel%3D%22b%22%5D%0A%20%20%205-%3E6%5Blabel%3D%22a%22%5D%0A%20%20%205-%3E6%5Blabel%3D%22b%22%5D%0A%20%20%20rankdir%3D%22LR%22%0A%7D)

#### 解答

<!-- This is the original graph
digraph G {

   start[label= "", shape=none,height=.0,width=.0]
   {node[shape=circle];1;"1,2";3;4;5}
   {node[shape=doublecircle];6}
  
   start->1
   1->"1,2"[label="a"]
   1->1[label="b"]
   "1,2"->"1,2"[label="a"]
   "1,2"->1[label="b"]
   "1,2"->3[label="a|b"]
   3->4[label="a|b"]
   4->5[label="a|b"]
   5->6[label="a|b"]
   rankdir="LR";
}
-->
![digraph](https://g.gravizo.com/svg?digraph%20G%20%7B%0A%0A%20%20%20start%5Blabel%3D%20%22%22%2C%20shape%3Dnone%2Cheight%3D.0%2Cwidth%3D.0%5D%0A%20%20%20%7Bnode%5Bshape%3Dcircle%5D%3B1%3B%221%2C2%22%3B3%3B4%3B5%7D%0A%20%20%20%7Bnode%5Bshape%3Ddoublecircle%5D%3B6%7D%0A%20%20%0A%20%20%20start-%3E1%0A%20%20%201-%3E%221%2C2%22%5Blabel%3D%22a%22%5D%0A%20%20%201-%3E1%5Blabel%3D%22b%22%5D%0A%20%20%20%221%2C2%22-%3E%221%2C2%22%5Blabel%3D%22a%22%5D%0A%20%20%20%221%2C2%22-%3E1%5Blabel%3D%22b%22%5D%0A%20%20%20%221%2C2%22-%3E3%5Blabel%3D%22a%7Cb%22%5D%0A%20%20%203-%3E4%5Blabel%3D%22a%7Cb%22%5D%0A%20%20%204-%3E5%5Blabel%3D%22a%7Cb%22%5D%0A%20%20%205-%3E6%5Blabel%3D%22a%7Cb%22%5D%0A%20%20%20rankdir%3D%22LR%22%3B%0A%7D)

### c.

<!-- This is the original graph
digraph C {
  start[label= "", shape=none,height=.0,width=.0]
  {node[shape=circle];1;2;3;5;6;7;8;10;11;12;14;15;16;17}
  {node[shape=doublecircle];4;9;13;18}
  
  start=1
  1->2[label="c"]
  2->3[label="a"]
  3->4[label="t"]
  1->5[label="ε"]
  5->6[label="c"]
  6->7[label="a"]
  7->8[label="t"]
  8->9[label="s"]
  5->10[label="ε"]
  10->11[label="c"]
  11->12[label="a"]
  12->13[label="r"]
  10->14[label="ε"]
  14->15[label="c"]
  15->16[label="a"]
  16->17[label="r"]
  17->18[label="s"]
  rankdir="LR"
}
-->
![digraph](https://g.gravizo.com/svg?digraph%20G%20%7B%0A%20%20start%5Blabel%3D%20%22%22%2C%20shape%3Dnone%2Cheight%3D.0%2Cwidth%3D.0%5D%0A%20%20%7Bnode%5Bshape%3Dcircle%5D%3B1%3B2%3B3%3B5%3B6%3B7%3B8%3B10%3B11%3B12%3B14%3B15%3B16%3B17%7D%0A%20%20%7Bnode%5Bshape%3Ddoublecircle%5D%3B4%3B9%3B13%3B18%7D%0A%20%20%0A%20%20start%3D1%0A%20%201-%3E2%5Blabel%3D%22c%22%5D%0A%20%202-%3E3%5Blabel%3D%22a%22%5D%0A%20%203-%3E4%5Blabel%3D%22t%22%5D%0A%20%201-%3E5%5Blabel%3D%22%CE%B5%22%5D%0A%20%205-%3E6%5Blabel%3D%22c%22%5D%0A%20%206-%3E7%5Blabel%3D%22a%22%5D%0A%20%207-%3E8%5Blabel%3D%22t%22%5D%0A%20%208-%3E9%5Blabel%3D%22s%22%5D%0A%20%205-%3E10%5Blabel%3D%22%CE%B5%22%5D%0A%20%2010-%3E11%5Blabel%3D%22c%22%5D%0A%20%2011-%3E12%5Blabel%3D%22a%22%5D%0A%20%2012-%3E13%5Blabel%3D%22r%22%5D%0A%20%2010-%3E14%5Blabel%3D%22%CE%B5%22%5D%0A%20%2014-%3E15%5Blabel%3D%22c%22%5D%0A%20%2015-%3E16%5Blabel%3D%22a%22%5D%0A%20%2016-%3E17%5Blabel%3D%22r%22%5D%0A%20%2017-%3E18%5Blabel%3D%22s%22%5D%0A%20%20rankdir%3D%22LR%22%0A%7D)

#### 解答

<!-- This is the original graph
digraph G {

  start[label= "", shape=none,height=.0,width=.0]
  {node[shape=circle];"1,5,10,14";"2,6,11,15";"3,7,12,16"}
  {node[shape=doublecircle];"4,8";"13,17";9;18}
    
  start->"1,5,10,14"
  "1,5,10,14"->"2,6,11,15"[label="c"]
  "2,6,11,15"->"3,7,12,16"[label="a"]
  "3,7,12,16"->"4,8"[label="t"]
  "3,7,12,16"->"13,17"[label="r"]
  "4,8"->9[label="s"]
  "13,17"->18[label="s"]
  rankdir="LR"
}
-->

![digraph](https://g.gravizo.com/svg?digraph%20G%20%7B%0A%0A%20%20start%5Blabel%3D%20%22%22%2C%20shape%3Dnone%2Cheight%3D.0%2Cwidth%3D.0%5D%0A%20%20%7Bnode%5Bshape%3Dcircle%5D%3B%221%2C5%2C10%2C14%22%3B%222%2C6%2C11%2C15%22%3B%223%2C7%2C12%2C16%22%7D%0A%20%20%7Bnode%5Bshape%3Ddoublecircle%5D%3B%224%2C8%22%3B%2213%2C17%22%3B9%3B18%7D%0A%20%20%20%20%0A%20%20start-%3E%221%2C5%2C10%2C14%22%0A%20%20%221%2C5%2C10%2C14%22-%3E%222%2C6%2C11%2C15%22%5Blabel%3D%22c%22%5D%0A%20%20%222%2C6%2C11%2C15%22-%3E%223%2C7%2C12%2C16%22%5Blabel%3D%22a%22%5D%0A%20%20%223%2C7%2C12%2C16%22-%3E%224%2C8%22%5Blabel%3D%22t%22%5D%0A%20%20%223%2C7%2C12%2C16%22-%3E%2213%2C17%22%5Blabel%3D%22r%22%5D%0A%20%20%224%2C8%22-%3E9%5Blabel%3D%22s%22%5D%0A%20%20%2213%2C17%22-%3E18%5Blabel%3D%22s%22%5D%0A%20%20rankdir%3D%22LR%22%0A%7D)

## 2.6 在下面这个自动机中找出两个等价的状态，并合并它们产生一个识别相同语言且较小的自动机。重复这个过程直到没有等价状态为止。

<!-- This is the original graph
digraph G {
  start[label= "", shape=none,height=.0,width=.0]
  {node[shape=circle];1;2;4;5;6;7;8}
  {node[shape=doublecircle];3}
  start->1
  1->2[label="0"]
  1->6[label="1"]
  2->3[label="1"]
  2->7[label="0"]
  3->1[label="0"]
  3->3[label="1"]
  4->3[label="0"]
  4->7[label="1"]
  5->6[label="1"]
  5->8[label="0"]
  6->7[label="1"]
  6->3[label="0"]
  7->5[label="1"]
  7->7[label="0"]
  8->7[label="0"]
  8->3[label="1"]
  
  {rank = same; 1;2;3;4}
  {rank = same; 5;6;7;8}
}
-->


### 解答


- P0 = {{1, 2, 4, 5, 6, 7, 8}, {3}}
- P1 = {{1, 5, 7}, {2, 8}, {4, 6}, {3}}
- P2 = {{1, 5} {2, 8}, {7}, {4, 6}, {3}}
- P3 = {{1, 5} {2, 8}, {7}, {4, 6}, {3}}

   因为 p2 = p3, 所以终止。


<!-- This is the original graph
digraph G {
  start[label= "", shape=none,height=.0,width=.0]
  {node[shape=circle];"1,5";"2,8";7;"4,6"}
  {node[shape=doublecircle];3}
  start->"1,5"
  "1,5"->"2,8"[label="0"]
  "1,5"->"4,6"[label="1"]
  "2,8"->7[label="0"]
  "2,8"->3[label="1"]
  7->7[label="0"]
  7->"1,5"[label="1"]c
  "4,6"->7[label="1"]
  "4,6"->3[label="0"]
  rankdir="LR"
}
-->

![digraph](https://g.gravizo.com/svg?digraph%20G%20%7B%0A%20%20start%5Blabel%3D%20%22%22%2C%20shape%3Dnone%2Cheight%3D.0%2Cwidth%3D.0%5D%0A%20%20%7Bnode%5Bshape%3Dcircle%5D%3B%221%2C5%22%3B%222%2C8%22%3B7%3B%224%2C6%22%7D%0A%20%20%7Bnode%5Bshape%3Ddoublecircle%5D%3B3%7D%0A%20%20start-%3E%221%2C5%22%0A%20%20%221%2C5%22-%3E%222%2C8%22%5Blabel%3D%220%22%5D%0A%20%20%221%2C5%22-%3E%224%2C6%22%5Blabel%3D%221%22%5D%0A%20%20%222%2C8%22-%3E7%5Blabel%3D%220%22%5D%0A%20%20%222%2C8%22-%3E3%5Blabel%3D%221%22%5D%0A%20%207-%3E7%5Blabel%3D%220%22%5D%0A%20%207-%3E%221%2C5%22%5Blabel%3D%221%22%5D%0A%20%20%224%2C6%22-%3E7%5Blabel%3D%221%22%5D%0A%20%20%224%2C6%22-%3E3%5Blabel%3D%220%22%5D%0A%20%20rankdir%3D%22LR%22%0A%7D)


## *2.7 任何接收至少一个字符串的 DFA 都能转换为一个正则表达式。将习题 2.3c 的 DFA 转化为正则表达式。**提示:** 首先假装状态1是初态。然后，编写一个通到状态 2 并返回到状态 1 的正则表达式和一个类似的通到状态 0 并返回到状态 1 的正则表达式。或者查看 Hopcroft 和 Ullman[1979]一书中定理 2.4 关于此算法的论述。

### 解答
`0*(1(01*0)*1)*`

## *2.8 假设 Lex 使用下面这个 DFA 来寻找输入文件中的单词：

### a. Lex 在匹配一个单词之前，必须在该单词之后再检测多少个字符？

### b. 设你对问题 a 的答案为 k， 写出一个至少包含两个单词的如输入文件，使得 Lex 的第一次调用在返回第一个单词前需要检测该单词末尾之后的 k 个字符。若对问题 a 的答案为 0，则写出一个包含至少两个单词的输入文件，并指出每个单词的结束点。

## 2.9 一个基于 DFA 的解释型词法分析器使用以下两张表。
- edges 以状态和输入符号为索引，产生一个状态号。
- final 以状态为索引，返回 0 或一个动作号。

从下面这个词法规范开始：
```
(aba)+      (action 1);
(a(b*)a)    (action 2);
(a|b)       (action 3);
```
为一个词法分析器生成 edges 和 final 表。

然后给该词法分析器分析字符串 abaabbaba 的每一步。注意，一定要给出此词法分析器重要的内部变量的值，该词法分析器将被反复调用以获得后继的单词。

### 解答
#### 1. 首先将此词法规范转换为 NFA。

<!-- This is the original graph
digraph G {
  start[label= "", shape=none,height=.0,width=.0]
  {node[shape=circle];1;2;3;4;5;7;8;9}
  {node[shape=doublecircle];6;10;11}
  start->1
  1->2[label="ε"]
  1->3[label="ε"]
  1->4[label="ε"]
  2->5[label="a"]
  3->6[label="a|b"]
  4->7[label="a"]
  5->8[label="b"]
  7->9[label="ε"]
  8->10[label="a"]
  9->9[label="b"]
  10->2[label="ε"]
  9->11[label="a"]
  
  rankdir="LR"
}
-->

![digraph](https://g.gravizo.com/svg?digraph%20G%20%7B%0A%20%20start%5Blabel%3D%20%22%22%2C%20shape%3Dnone%2Cheight%3D.0%2Cwidth%3D.0%5D%0A%20%20%7Bnode%5Bshape%3Dcircle%5D%3B1%3B2%3B3%3B4%3B5%3B7%3B8%3B9%7D%0A%20%20%7Bnode%5Bshape%3Ddoublecircle%5D%3B6%3B10%3B11%7D%0A%20%20start-%3E1%0A%20%201-%3E2%5Blabel%3D%22%CE%B5%22%5D%0A%20%201-%3E3%5Blabel%3D%22%CE%B5%22%5D%0A%20%201-%3E4%5Blabel%3D%22%CE%B5%22%5D%0A%20%202-%3E5%5Blabel%3D%22a%22%5D%0A%20%203-%3E6%5Blabel%3D%22a%7Cb%22%5D%0A%20%204-%3E7%5Blabel%3D%22a%22%5D%0A%20%205-%3E8%5Blabel%3D%22b%22%5D%0A%20%207-%3E9%5Blabel%3D%22%CE%B5%22%5D%0A%20%208-%3E10%5Blabel%3D%22a%22%5D%0A%20%209-%3E9%5Blabel%3D%22b%22%5D%0A%20%2010-%3E2%5Blabel%3D%22%CE%B5%22%5D%0A%20%209-%3E11%5Blabel%3D%22a%22%5D%0A%20%20%0A%20%20rankdir%3D%22LR%22%0A%7D)

其中:
- 终态10 对应动作 (action 1)
- 终态11 对应动作 (action 2)
- 终态6 对应动作 (action 3)

#### 2. 再将次 NFA 转换为 DFA。

<!-- This is the original graph
digraph G {
  start[label= "", shape=none,height=.0,width=.0]
  {node[shape=circle];"1,2,3,4";"8,9";9;5;8;}
  {node[shape=doublecircle];"5,6,7,9";"2,10,11";11;"2,10";6}
  start->"1,2,3,4"
  "1,2,3,4"->"5,6,7,9"[label="a"]
  "1,2,3,4"->6[label="b"]
  "5,6,7,9"->11[label="a"]
  "5,6,7,9"->"8,9"[label="b"]
  "8,9"->"2,10,11"[label="a"]
  "8,9"->9[label="b"]
  "2,10,11"->5[label="a"]
  5->8[label="b"]
  8->"2,10"[label="a"]
  "2,10"->5[label="a"]
  9->9[label="b"]
  9->11[label="a"]
   rankdir="LR"
}
-->

![digraph](https://g.gravizo.com/svg?digraph%20G%20%7B%0A%20%20start%5Blabel%3D%20%22%22%2C%20shape%3Dnone%2Cheight%3D.0%2Cwidth%3D.0%5D%0A%20%20%7Bnode%5Bshape%3Dcircle%5D%3B%221%2C2%2C3%2C4%22%3B%228%2C9%22%3B9%3B5%3B8%3B%7D%0A%20%20%7Bnode%5Bshape%3Ddoublecircle%5D%3B%225%2C6%2C7%2C9%22%3B%222%2C10%2C11%22%3B11%3B%222%2C10%22%3B6%7D%0A%20%20start-%3E%221%2C2%2C3%2C4%22%0A%20%20%221%2C2%2C3%2C4%22-%3E%225%2C6%2C7%2C9%22%5Blabel%3D%22a%22%5D%0A%20%20%221%2C2%2C3%2C4%22-%3E6%5Blabel%3D%22b%22%5D%0A%20%20%225%2C6%2C7%2C9%22-%3E11%5Blabel%3D%22a%22%5D%0A%20%20%225%2C6%2C7%2C9%22-%3E%228%2C9%22%5Blabel%3D%22b%22%5D%0A%20%20%228%2C9%22-%3E%222%2C10%2C11%22%5Blabel%3D%22a%22%5D%0A%20%20%228%2C9%22-%3E9%5Blabel%3D%22b%22%5D%0A%20%20%222%2C10%2C11%22-%3E5%5Blabel%3D%22a%22%5D%0A%20%205-%3E8%5Blabel%3D%22b%22%5D%0A%20%208-%3E%222%2C10%22%5Blabel%3D%22a%22%5D%0A%20%20%222%2C10%22-%3E5%5Blabel%3D%22a%22%5D%0A%20%209-%3E9%5Blabel%3D%22b%22%5D%0A%20%209-%3E11%5Blabel%3D%22a%22%5D%0A%20%20%20rankdir%3D%22LR%22%0A%7D)

其中:
- 终态(5,6,7,8) 对应动作 (action 3)
- 终态6 对应动作 (action 3)
- 终态(2,10,11) 对应动作 (action 1), (action 2)
- 终态11 对应动作 (action 2)
- 终态(2,10) 对应动作 (action 1)

调整状态号：
<!-- This is the original graph
digraph G {
  start[label= "", shape=none,height=.0,width=.0]
  {node[shape=circle];1;4;6;7;9;}
  {node[shape=doublecircle];2;5;8;10;3}
  start->1
  1->2[label="a"]
  1->3[label="b"]
  2->8[label="a"]
  2->4[label="b"]
  4->5[label="a"]
  4->6[label="b"]
  5->7[label="a"]
  7->9[label="b"]
  9->10[label="a"]
  10->7[label="a"]
  6->6[label="b"]
  6->8[label="a"]
  rankdir="LR"
}
-->

![digraph](https://g.gravizo.com/svg?digraph%20G%20%7B%0A%20%20start%5Blabel%3D%20%22%22%2C%20shape%3Dnone%2Cheight%3D.0%2Cwidth%3D.0%5D%0A%20%20%7Bnode%5Bshape%3Dcircle%5D%3B1%3B4%3B6%3B7%3B9%3B%7D%0A%20%20%7Bnode%5Bshape%3Ddoublecircle%5D%3B2%3B5%3B8%3B10%3B3%7D%0A%20%20start-%3E1%0A%20%201-%3E2%5Blabel%3D%22a%22%5D%0A%20%201-%3E3%5Blabel%3D%22b%22%5D%0A%20%202-%3E8%5Blabel%3D%22a%22%5D%0A%20%202-%3E4%5Blabel%3D%22b%22%5D%0A%20%204-%3E5%5Blabel%3D%22a%22%5D%0A%20%204-%3E6%5Blabel%3D%22b%22%5D%0A%20%205-%3E7%5Blabel%3D%22a%22%5D%0A%20%207-%3E9%5Blabel%3D%22b%22%5D%0A%20%209-%3E10%5Blabel%3D%22a%22%5D%0A%20%2010-%3E7%5Blabel%3D%22a%22%5D%0A%20%206-%3E6%5Blabel%3D%22b%22%5D%0A%20%206-%3E8%5Blabel%3D%22a%22%5D%0A%20%20rankdir%3D%22LR%22%0A%7D)

其中:
- 终态2 对应动作 (action 3)
- 终态3 对应动作 (action 3)
- 终态5 对应动作 (action 1), (action 2)
- 终态8 对应动作 (action 2)
- 终态10 对应动作 (action 1)

#### 3. 最小化此 DFA。
- P0: {{1,4,6,7,9}, {2,3,5,8,10}}
- P1: {{1}, {4,6}, {7}, {9}, {2}, {3,8}, {5,10}}
- P2: {{1}, {4}, {6}, {7}, {9}, {2}, {3,8}, {5,10}}
- P3: {{1}, {4}, {6}, {7}, {9}, {2}, {3,8}, {5,10}}

因为 p2=p3, 所以终止。

<!-- This is the original graph
digraph G {
  start[label= "", shape=none,height=.0,width=.0]
  {node[shape=circle];1;4;6;7;9;}
  {node[shape=doublecircle];2;"5,10";"3,8";"5,10";"3,8"}
  start->1
  1->2[label="a"]
  1->"3,8"[label="b"]
  2->"3,8"[label="a"]
  2->4[label="b"]
  4->"5,10"[label="a"]
  4->6[label="b"]
  "5,10"->7[label="a"]
  7->9[label="b"]
  9->"5,10"[label="a"]
  6->6[label="b"]
  6->"3,8"[label="a"]
  rankdir="LR"
}
-->

![digraph](https://g.gravizo.com/svg?digraph%20G%20%7B%0A%20%20start%5Blabel%3D%20%22%22%2C%20shape%3Dnone%2Cheight%3D.0%2Cwidth%3D.0%5D%0A%20%20%7Bnode%5Bshape%3Dcircle%5D%3B1%3B4%3B6%3B7%3B9%3B%7D%0A%20%20%7Bnode%5Bshape%3Ddoublecircle%5D%3B2%3B%225%2C10%22%3B%223%2C8%22%3B%225%2C10%22%3B%223%2C8%22%7D%0A%20%20start-%3E1%0A%20%201-%3E2%5Blabel%3D%22a%22%5D%0A%20%201-%3E%223%2C8%22%5Blabel%3D%22b%22%5D%0A%20%202-%3E%223%2C8%22%5Blabel%3D%22a%22%5D%0A%20%202-%3E4%5Blabel%3D%22b%22%5D%0A%20%204-%3E%225%2C10%22%5Blabel%3D%22a%22%5D%0A%20%204-%3E6%5Blabel%3D%22b%22%5D%0A%20%20%225%2C10%22-%3E7%5Blabel%3D%22a%22%5D%0A%20%207-%3E9%5Blabel%3D%22b%22%5D%0A%20%209-%3E%225%2C10%22%5Blabel%3D%22a%22%5D%0A%20%206-%3E6%5Blabel%3D%22b%22%5D%0A%20%206-%3E%223%2C8%22%5Blabel%3D%22a%22%5D%0A%20%20rankdir%3D%22LR%22%0A%7D)

其中:
- 终态2 对应动作 (action 3)
- 终态(5,10) 对应动作 (action 1), (action 2)
- 终态(3,8) 对应动作 (action 2), (action 3)

调整状态号：

 <!-- This is the original graph
digraph G {
  start[label= "", shape=none,height=.0,width=.0]
  {node[shape=circle];1;3;5;6;8;}
  {node[shape=doublecircle];2;4;7;4;7}
  start->1
  1->2[label="a"]
  1->7[label="b"]
  2->7[label="a"]
  2->3[label="b"]
  3->4[label="a"]
  3->5[label="b"]
  4->6[label="a"]
  6->8[label="b"]
  8->4[label="a"]
  5->5[label="b"]
  5->7[label="a"]
  rankdir="LR"
}
-->

![digraph](https://g.gravizo.com/svg?digraph%20G%20%7B%0A%20%20start%5Blabel%3D%20%22%22%2C%20shape%3Dnone%2Cheight%3D.0%2Cwidth%3D.0%5D%0A%20%20%7Bnode%5Bshape%3Dcircle%5D%3B1%3B3%3B5%3B6%3B8%3B%7D%0A%20%20%7Bnode%5Bshape%3Ddoublecircle%5D%3B2%3B4%3B7%3B4%3B7%7D%0A%20%20start-%3E1%0A%20%201-%3E2%5Blabel%3D%22a%22%5D%0A%20%201-%3E7%5Blabel%3D%22b%22%5D%0A%20%202-%3E7%5Blabel%3D%22a%22%5D%0A%20%202-%3E3%5Blabel%3D%22b%22%5D%0A%20%203-%3E4%5Blabel%3D%22a%22%5D%0A%20%203-%3E5%5Blabel%3D%22b%22%5D%0A%20%204-%3E6%5Blabel%3D%22a%22%5D%0A%20%206-%3E8%5Blabel%3D%22b%22%5D%0A%20%208-%3E4%5Blabel%3D%22a%22%5D%0A%20%205-%3E5%5Blabel%3D%22b%22%5D%0A%20%205-%3E7%5Blabel%3D%22a%22%5D%0A%20%20rankdir%3D%22LR%22%0A%7D)

其中:
- 终态2 对应动作 (action 3)
- 终态4 对应动作 (action 1), (action 2)
- 终态7 对应动作 (action 2), (action 3)

#### 4. 由上图可轻松得到 edges 和 final 表

edges 表（其中粗体数字表示终态）：

| |a|b|
|-|-|-|
|1|**2**|**7**|
|**2**|**7**|3|
|3|**4**|5|
|**4**|6| |
|5|**7**|5|
|6| |8|
|**7**| | |
|8|**4**| |

final 表：
|1|2|3|4|5|6|7|8|
|-|-|-|-|-|-|-|-|
|0|3|0|1,2|0|0|2,3|0|





### 字符串 abaabbaba 中每个字母的 position。
|1|2|3|4|5|6|7|8|9|
|-|-|-|-|-|-|-|-|-|
|a|b|a|a|b|b|a|b|a|

### 该词法分析器分析字符串 abaabbaba 的每一步的过程

|curr_char_pos|curr_char|curr_state|last_final_state|last_final_state_char_pos|remarks|
|:-:|:-:|:-:|:-:|:-:|:-:|
|0| |1| | |初始状态1|
|1|a|2|2|1| |
|2|b|3|2|1| |
|3|a|4|4|3| |
|4|a|6|4|3| |
|5|b|8|4|3| |
|6|b| |4|3|状态 8 不能接收字符 b，匹配上一个终态 4, 执行对应终态的第一个动作 (action 1)|
|3|a|1| | |curr_state 恢复为 1，curr_char_pos = last_final_state_char_pos|
|4|a|2|2|4| |
|5|b|3|2|4| |
|6|b|5|2|4| |
|7|a|7|7|7| |
|8|b| |7|7|状态 7 为终态且不能接收任何字符，执行状态7对应的第一个动作 (action 2)|
|7|a|1| | |curr_state 恢复为 1，curr_char_pos = last_final_state_char_pos|
|8|b|7|7|8| |
|9|a| |7|8|状态 7 为终态且不能接收任何字符，执行状态7对应的第一个动作 (action 2)|
|8|b|1| | |curr_state 恢复为 1，curr_char_pos = last_final_state_char_pos|
|9|a|2|2|9| |
| | | |2|9|到达字符串末尾，执行状态 2 对应的对应的动作 (action 3)|
