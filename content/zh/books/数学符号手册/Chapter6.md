---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "函数"
linktitle: "第六章 函数"
summary: 数学符号手册，翻译至Mathematical Notation by Edward R. Scheinerman。如何表示函数。
date: 2020-09-27T21:41:47+08:00
lastmod: 2020-09-27T21:41:47+08:00
draft: true  # Is this a draft? true/false
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
    weight: 6
---



## 基础知识

　　**基础符号。**在工程或科学领域会遇到很多函数，它接受实数作为输入，返回实数作为输出。这个注释$f:{\Bbb R} \to {\Bbb R}$的意思是函数$f$接受任何实数作为输入，而返回的输出位于实数集合中。

　　更通俗的说法是，如果有任一集合A和B，注释$f:A \to B$是指函数$f$接受来自集合A的元素作为输入，返回的值都在集合B的范围内。

　　并不是集合B中的所有元素都是$f$的输出值。例如，如果我们说$cos:{\Bbb R} \to {\Bbb R}$，这表示函数$cos$接受任何实数作为输入，返回的值也是实数。当然，函数$cos$的输出值在区间[-1,1]之间，而不能说会返回任何其它实数。

　　函数$f(x)$暗示函数$f$会接受值$x$并返回一个值。也就是说，$f$是一个函数，$f(x)$是函数$f$在$x$时返回的一个值（通常是一个数字）。

　　另一种函数的返回值的表达方式也会使用，尤其在函数是一个公式的时候。一般的形式是这样的：$(some\ expression\ involving \ a \ variable \ x)|_{x=a}$。这个意思是用a代替x来估计表达式的返回值。这种类型的注释通常使用莱布尼茨符号衍生品（见第50页）。

　　注释$y=f(x)$是$x \mapsto y$的缩写，读作“x maps to y”。注意函数$f$是不用在表达式$x \mapsto y$中显示出来，所以只有当涉及的函数不清楚时也会用这种注释。此外，还可以用$\mathop{\mapsto}\limits^f$来代表$f(x)=y$。

　　如果函数的输入和输出都是函数，则这个函数称为*算子*。一般用大写算子的名字来区别函数和算子。如果输入是函数，算子会省略掉括号：$Lf$表示算子$L$在函数$f$上的估计。

---

<center> 第25页 </center>

　　注释$f(\cdot)$有时会用来强调$f$是一个函数，点号则表示函数期待输入一个参数。这个在指代一个不是字母的函数时非常有用。例如，当我们讨论数值的绝对值函数时，我们可以写成$|\cdot|$。当然在两个竖线之间用一个哑变量或空白也行。

　　函数也可以接受多个参数，例如$f(x,y)$是一个可接受两个参数的函数。这种情况下，点号有助于表达哪个参数是常量，哪个参数是变量。比如，$f(\cdot,b)$表示一个可接受一个变量的函数，第一个参数可以是其域值内任何一个，第二个参数是是一个常量，值为b。

　　对于一个函数$f:X \to Y$，函数$f$的像用$Im(f)$表示：$Im(f)=\{y \in Y |\exists x \in X, f(x)=y \}$。更通俗地讲，如果$A \in X$，那么$f(A)$表示集合${\lbrace f(a) | a \in A \rbrace}$。因此$f(X)=Im(f)$。

　　函数常常用代数公式来表示，但不是绝对的。函数也可以定义为分段函数，像这样：$f(x)=\begin{cases} e^{-1/x^2} & \text{for x>0} \\ 0 & \text{otherwise} \end{cases}$

　　**复合与逆函数。**假设$f:A \to B$和$g:B \to C$，那么$g \circ f$是一个新函数，即函数$g$和$f$的复合，$(g \circ f):A \to C$可定义为$(g \circ f)(x)=g[f(x)]$。

　　注释$f^{-1}(y)$表示的是使得$f(x)=y$时x的值，我们称$f^{-1}$为$f$的逆函数或反函数。

　　如果有多个x的$f(x)=y$，那么$f^{-1}$不是一个函数。有人使用注释$f^{-1}(y)$来代表输出值为y的所有x值的集合。然而，有些情况会强制$f^{-1}$成为一个函数，即对x的选择进行限制。例如，arc sin函数是$sin^{-1}$。有无限个x使得$sin \ x=\frac 1 2$，但是如果我们限定x的取值范围是区间$(-\frac \pi 2,\frac \pi 2]$。这种情况下，arc sin就变成一个函数。此外，如果没有值使得$f(x)=y$，那么$f^{-1}(y)$是未定义的。







<center> 第26页 </center>







<center> 第27页 </center>





<center> 第28页 </center>





<center> 第29页 </center>



<center> 第30页 </center>



<center> 第31页 </center>


<center> 第32页 </center>


<center> 第33页 </center>


<center> 第34页 </center>


<center> 第35页 </center>



<center> 第36页 </center>

<center> 第37页 </center>



