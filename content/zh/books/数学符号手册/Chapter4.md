---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "数字"
linktitle: "第四章 数字"
summary: 数学符号手册，翻译至Mathematical Notation by Edward R. Scheinerman。如何表示数字。
date: 2020-09-23T22:21:58+08:00
lastmod: 2020-09-23T22:21:58+08:00
draft: ture  # Is this a draft? true/false
toc: true  # Show table of contents? true/false
type: docs  # Do not modify.

# Add menu entry to sidebar.
# - Substitute `example` with the name of your course/documentation folder.
# - name: Declare this menu item as a parent with ID `name`.
# - parent: Reference a parent ID if this page is a child.
# - weight: Position of link in menu.
menu:
  数学符号手册:
    #name: 目录
    parent: 目录
    weight: 4
---

## 1. 实数

　　**数字的书写**。所有实数的集合用${\Bbb R}$表示。通常来说，实数是用十进制来计数，以一个符号开始（如果是正数那么符号是可选的，但是是负数一定要在数字前面加负号），接着是一串有限的数字，一个小数点，最后接一串有限或无限的数字。

　　小数点后面无限重复的数字块常常用上划线来表示：$45.07123123123123\ldots=45.07\overline{123}$。当数字大小在0和1之间，最好写出前面的0。0.123要比.123更好，因为最前的0可以提醒读者这是个小数否则只有小数点很容易被忽略。

　　小数点左边的数字如果大于3位的话，通常要加逗号来增加可读性：$1,332,443$。但是数字在1000和9999之间通常不加逗号。某些情况下，可以用空格来代替逗号：$1\ 332\ 443$。

　　并不是所有人都用句号来代表作小数点。有些国家用逗号来代替（例如：$\pi \approx 3,14159$），且用句号来间隔3位以上的数字（例如：$1.332.443$）。

　　百分号的意思是“除以100”。下面数字其实都表示一个值，但是可以被写成不同的形式：$\frac 1 4 \quad 0.25 \quad 25\%$。

　　科学计数法常常用来表示实数，特别是一些很大或很少的数。例如：$1.23\times 10^7 = 12,300,000$ 和$4.56\times 10^{-4}=0.000456$。在10的幂前面的数字通常要大于1且小于10。电脑程序使用科学计数法来表示数字时可能会用E或e来代替10的幂运算，像这样：
$$
\begin{align*}
1.23\times 10^7 \quad &1.23E07 \\\\
4.56\times10^{-4} \quad &4.56E-04
\end{align*}
$$

---
<center> 第13页 </center>

　　工程符号是科学计数法的变体，10的指数一定要是3的倍数，像这样:
$$
\begin{align*}
Scientific\ notation:\quad &6.022\times 10^{23}\\\\
Engineering\ notation:\quad &602.2\times10^{21}
\end{align*}
$$
对于工程符号，在10的幂前面的数字应该要大于1小于1000。

　　有时候使用其它基数而不是10是很有用的。下面列出一些其它形式的计数法：

- 基数在下标上用字母来代表，比如：$14_{FIVE}\ or \ 0.202020_{THREE}$。
- 基数在下标上用数字来表示，比如：$1011_2$。
- 在计算机领域，16进制是用$0X$或$0x$开头。例如：$0X1A2B93$或$0x1a2b93$。这里字母A到F分别代表数字10到15。
- 在计算机领域，8进制是简单地用0开头。如$0177$。

　　有些实数可以用连分式来表示。例如：
$$
1+\cfrac{1}{2+\cfrac 1 {3+\cfrac 1 {4+ \cfrac 1{\cdots}}}}
$$
这种连分式也可用紧缩记法来表示，像这样：$1+\frac 1 {2+} \frac 1{3+} \frac 1 {4+} \cdots$。这两个例子中，分子都是1，不过也可以是其它的。但是在分子都是1的情况下，连分式也可以表示成这样：$[1;2,3,4,\cdots]$。

---

　　**数字的注释。** 实数$x$的绝对值用$|x|$表示。

　　加减号$\pm$通常用来指代两个不同的值。因此$\pm 2$是指2和-2。这是很有用的速记方式，可以在一个公式中用来表示两个不同的正负值。例如，等式$x^2-2x-2=0$的解是$1\pm \sqrt{3}$。这意思是$1+\sqrt{3}$和$1-\sqrt{3}$都是等式的解。

　　但在一个表达式中使用加减号$\pm$两次则容易造成误解。试想一下$\pm 1 \pm \sqrt{5}$。这也许表示$1+\sqrt{5}$和$-1-\sqrt{5}$这两个值，但也可以表示$1-\sqrt{5}$和$-1+\sqrt{5}$。真实想表达的意思得根据上下文进行推导。

---
<center> 第14页 </center>

　　减加号$\mp$表示的意思与$\pm$是一样的。$\mp$常常与$\pm$联合使用，表示相反的符号。因此$\pm3\mp\sqrt{7}$是指两个值：$3-\sqrt{7}$t和$3+\sqrt{7}$。

　　等式符号$=$有两种含义。一个是指两个值是相等的，就像$3+4=7$。在定义一个对象的时候还有另一种意思，就像“假设$x=1+\sqrt{5}$”。有些人在定义对象时用$:=$来表示。此外，符号$\triangleq$和$\buildrel def \over {=}$也可以表示等式符号。



## 2. 实数的子集

　　整数是指小数点后没有任何数字的实数，其中小数点写不写是可选的。整个整数的集合用${\Bbb Z}$表示：${\Bbb Z}=\lbrace \cdots,-3,-2,-1,0,1,2,3,\cdots \rbrace$。

　　名词*自然数*没有一个标准的定义。这里我们把*自然数*定义为非负数的整数。因此，${\Bbb N}=\lbrace 0,1,2,3,\cdots \rbrace$。然而，有些数学家认为要把0给排除在外。

　　*有理数*是指可以被写成两个整数之比$a/b$，且$b$不为0的实数。有理数的集合用${\Bbb R}$表示。也可以写成${\Bbb Q}=\lbrace x \in {\Bbb R}:x=a/b\quad where\quad a,b \in {\Bbb Z}\quad and\quad b \neq 0 \rbrace$。

　　这些集合的包含关系是这样的：${\Bbb R} \supset {\Bbb Q}\supset {\Bbb Z} \supset {\Bbb N}$。

　　在这些符号右上角加星号则有多种解释：

- ${\Bbb R^*},{\Bbb C^*}$等表示相对应集合除去元素0的其它所有元素。注意：${\Bbb C}$表示复数的集合（见4.4章节）。
- ${\Bbb R^*},{\Bbb C^*}$等也可以表示集合的可逆元素。在整数情况下，${\Bbb Z^*}$表示$\lbrace-1,1\rbrace$。不过这种情况我们更倾向于用${\Bbb Z^{\times}}$来表示。
- ${\Bbb C^*}$有时用来表示${\Bbb C} \cup \lbrace\infty\rbrace$，尽管我们推荐用$\hat {\Bbb C}$或$\overline {\Bbb C}$来表示。类似地，${\Bbb R^*}$有时用来表示${\Bbb R} \cup \lbrace-\infty,+\infty\rbrace$，但是我们推荐用$\overline {\Bbb R}$。

---
<center> 第15页 </center>

- ${\Bbb Z^*}$用来表示非负整数，$\lbrace0,1,2,\cdots\rbrace$，但是我们更推荐用${\Bbb N}$来表示。
- 最后${}^* {\Bbb R}$用来表示非标准实数，详细情况见第19页。

　　在${\Bbb R}$的上标或下标加上加号$+$通常是表示正实数：${\Bbb R^+}$或${\Bbb R_+}$。然而有时候为了方便需要把0也包括进来，于是${\Bbb R^n_+}$表示非负实数。类似地，${\Bbb Q^+}$和${\Bbb Z^+}$分别表示正的有理数和整数。

　　实数的区间可以用开放或关闭的括号和中括号表示。括号表示区间不包括临界点，而中括号则表示区间包括临界点。下面列出几个例子：
$$
\begin{align*}
[1,2]=\lbrace x \in {\Bbb R}:1 \leq x \leq 2\rbrace \\\\ 
[1,2)=\lbrace x \in {\Bbb R}:1 \leq x < 2\rbrace \\\\
(1,2]=\lbrace x \in {\Bbb R}:1 < x \leq 2\rbrace \\\\
(1,2)=\lbrace x \in {\Bbb R}:1 < x < 2\rbrace \\\\
\end{align*}
$$
　　有些人用反中括号表示不包括一个区间的临界点。例如[a,b[表示的意思和[a,b)是一样的，即$\lbrace x:a \leq x <b \rbrace$。类似地，]a,b]表示(a,b]，而]a,b[表示(a,b)。

　　符号$-\infty$和$\infty$也会用来表示区间的临界点：$[1,\infty)=\lbrace x \in {\Bbb R}:x \geq 1\rbrace$和$(-\infty,2)=\lbrace x \in {\Bbb R}:x < 2 \rbrace$。尽管表示所有的实数可以用$(-\infty,\infty)$表示，但是更简单明了的方式是用${\Bbb R}$表示。





## 3. 常见的实数

　　有一些实数有它本身特殊的含义。这里列举出一些常见的：

- $e$，自然对数的底数。它的近似值是2.71828。
- $\pi$，圆周率。它的近似值是3.14159。
- $\gamma$，欧拉常数：$\gamma = \lim_{n \to \infty}[\sum_{k=1}^{n} \frac 1 k - ln\ n]$。它的近似值是0.5772。
- $\phi$，黄金比例：$\phi = (1+\sqrt{5})/2$。它的近似值是1.618。

　　注意很多学科都保留了一些特定字母来表示常数，例如$c$表示光速。



---
<center> 第16页 </center>





## 4. 复数

待续$\cdots$

---
<center> 第17页 </center>



## 5. 基础运算符

　　两个数$a$与$b$之和可以表示为$a+b$，差值可以表示为$a-b$。

　　乘法则有多种表示方法。如果数字是用字母代替，那么$ab$则是最常用的方式。如果是一个数字和一个字母的乘积，那么数字一般写在字母前面，比如$3x$。两个数字的乘法则用$\cdot$或$\times$作为操作符：$5 \cdot 7$或 $8 \times 11$。由于$\cdot$或$\times$都不是标准键盘上的字符，有一些人（特别是一些编程语言）则用星号来表示乘法：$3 * 5$。

　　除法可以用这些方式来表示：$a \div b, a/b$或$ \frac a b$。大家可以选择一个最易读懂的符号。

　　指数则用上标来表示：$a^b$。然而，有时候也用$\wedge$或$**$来表示。

　　关于累加$\sum$和累积$\prod$的讨论见第8页。



## 6. 其它的表示体系

　　在工程和科学应用中，数学家也会使用很多其它数字体系。这里我们列出一些常见的体系。

- **分子序。**对一个整数$n\geq 2$，我们用${\Bbb Z_n}$表示集合$\lbrace 0,1,\cdots,n-1 \rbrace$

- **有限域。**一个有$n$个元素的有限域可以写成GF(n)或${\Bbb F_n}$。众所周知，一个有限域的大小一定要是素数的指数，所以有限域最有可能像这样：$GF(p^a)$或${\Bbb F_{p^a}}$。

  

---
<center> 第18页 </center>

- **高斯整数**。*高斯整数*表现形式为$a+bi$，实数和虚数部分都是整数的复数。高斯整数的集合用${\Bbb Z[i]}$表示。
- **四元数。**哈密顿发现的*四元数*的表现形式是$a+bi+cj+dk$，其中$a,b,c,d \in {\Bbb R}$，且i,j,k有下面的特性：

$$
\begin{align*}i^2=1 \qquad &ij=k \qquad ik=-j \\\\j^2=-1 \qquad &ij=k \qquad ik=-j \\\\j^2=-1 \qquad &ij=k \qquad ik=-j \\\\\end{align*}
$$

整个四元数的集合用${\Bbb H}$表示。注意元素间的乘法在${\Bbb H}$中是不能相互交换的。

- **外延。**上面我们提到高斯整数用${\Bbb Z[i]}$表示。这个注释意思是我们整合了整数集${\Bbb Z}$和虚数$i$，用加减乘方法构建了所有可能的数。



## 7. 无限

　　我们把无限的概念扩展到实数或复数体系中是非常有用的。

　　在实数领域中，$\overline {\Bbb R}$表示*扩展的实数*集合，它还包括了无限值$+\infty$和$-\infty$。

　　对于复数来说，$\hat {\Bbb C}$或$\overline {\Bbb C}$表示*扩展的复数*集合，也被称为黎曼球面，它还额外包括无限值$\infty$。这个体系有时也简单地用${\Bbb C} \cup \lbrace\infty\rbrace$表示。有些作者也写成${\Bbb C^*}$，不过这种符号更合适被用来表示集合${\Bbb C}-\lbrace0\rbrace$。

　　${}^* {\Bbb R}$是一个奇怪的实数扩展，表示*非标准实数*，包括了无穷小和超整数。

---
<center> 第19页 </center>

　　我们在第7页中谈过，假定一个集合A，符号|A|表示集合A的势。 对一个有限元素的集合来说，这是一个整数。但是对于无限的集合来说，我们有特别的表示方法。

　　符号$\aleph_0$用来表示整数集合的势：$\aleph_0 = |{\Bbb Z}|$。它是最小的超限数。符号${\aleph}$是希伯来语字母*aleph*，符号$\aleph_0$可以读作"aleph null" 或"aleph naught"。势为$\aleph_0$的集合也被称为*可数的*。

　　实数的势$|{\Bbb R}|$可以用$c$表示。$c$的数量也被称为*连续统的势*。

---
<center> 第20页 </center>