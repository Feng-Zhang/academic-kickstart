---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "函数"
linktitle: "第六章 函数"
summary: 数学符号手册，翻译至Mathematical Notation by Edward R. Scheinerman。如何表示函数。
date: 2020-09-27T21:41:47+08:00
lastmod: 2020-09-27T21:41:47+08:00
draft: false  # Is this a draft? true/false
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

　　并不是集合B中的所有元素都是$f$的输出值。例如，如果我们说$cos:{\Bbb R} \to {\Bbb R}$，这表示函数$cos$接受任何实数作为输入，返回的值也是实数。当然，函数$cos$的输出值在区间[-1,1]之间，而不能说可以返回任何其它实数。

　　函数$f(x)$暗示函数$f$会接受值$x$并返回一个值。也就是说，$f$是一个函数，$f(x)$是函数$f$在$x$时返回的一个值（通常是一个数字）。

　　另一种函数的返回值的表达方式也会使用，尤其在函数是一个公式的时候。一般的形式是这样的：$(some\ expression\ involving \ a \ variable \ x)|_{x=a}$。这个意思是用a代替x来估计表达式的返回值。这种类型的注释通常使用莱布尼茨符号衍生品（见第50页）。

　　注释$y=f(x)$是$x \mapsto y$的缩写，读作“x maps to y”。注意函数$f$是不用在表达式$x \mapsto y$中显示出来，所以只有当涉及的函数不清楚时也会用这种注释。此外，还可以用$\mathop{\mapsto}\limits^f$来代表$f(x)=y$。

　　如果函数的输入和输出都是函数，则这个函数称为*算子*。一般用大写算子的名字来区别函数和算子。如果输入是函数，算子会省略掉括号：$Lf$表示算子$L$在函数$f$上的估计。

　　注释$f(\cdot)$用来强调$f$是一个函数，点号则表示函数期待输入一个参数。这个在指代一个不是字母的函数时非常有用。例如，当我们讨论数值的绝对值函数时，我们可以写成$|\cdot|$。

　　函数

