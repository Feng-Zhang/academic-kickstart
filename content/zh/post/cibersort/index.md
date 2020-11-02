---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Test"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2020-11-02T07:44:39+08:00
lastmod: 2020-11-02T07:44:39+08:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---





　　众所周知，肿瘤一直是影响人类健康的第二大疾病，全世界的科研人员都集中了大量的人力物力进行肿瘤相关的研究和治疗。近几年，随着免疫治疗疗效的不断提高，目前已在多种肿瘤如黑色素瘤，非小细胞肺癌、肾癌和前列腺癌等实体瘤的治疗中展示出了很强的治疗效果，多个肿瘤免疫治疗药物已经获得美国FDA批准临床应用。

　　随着深入研究，我们也逐渐了解到肿瘤免疫微环境的复杂性和多样性以及它对免疫治疗的重要影响。同一种疾病和治疗方式，比如PD1，但是不同人的疗效却不一样。利用多组学技术，从宏观层面解析肿瘤组织中的免疫细胞构成，将有助于免疫治疗反应性的改善。目前单细胞测序技术可以达到这一目标，但是由于测序成本昂贵，还不具备。

**什么是免疫浸润**

　　所谓肿瘤免疫微环境的概念，就是肿瘤的内部和周围往往聚集着大量的免疫细胞。这些免疫细胞之间，以及肿瘤细胞和免疫细胞之间存在着千丝万缕，免疫细胞多种多样，所以所谓免疫微环境，或者说免疫浸润的分析，本质上，就是搞清楚肿瘤组织当中免疫细胞的构成比例。

![img](C:\Users\Administrator\AppData\Local\YNote\data\297946506@qq.com\91f693bde57642fe85318db732556646\clipboard.png)

**如何分析免疫浸润**

讲完了背景，我们就来看看，到底是如何判断免疫细胞的构成的呢？目前看来，计算免疫微环境的方法，常用的有两类：

（1）一类就是“实测法”，高精度的单细胞测序，Single cell RNA-seq。为了搞清楚构成，索性一个一个细胞去分开测序，把细胞表达都测了，通过一些标记基因，来判断到底这里面有多少类型的免疫细胞，以及每种细胞的构成比例。

（2）还有一种方法，那就是“推测法”，通过bulk RNA-seq进行推测。我们常规的普通RNA测序和芯片结果就是把所有细胞统一裂解抽提RNA，那么检测到的基因表达中，就是各种免疫细胞和肿瘤细胞混杂在一起的表达，通过一些算法，我们可以从这个混杂的表达谱中推断免疫细胞的构成比，常用的软件有CIBETSORT、TIMER、EPIC等等。

　　这两种方法各有有缺，单细胞最大的缺点就是贵！贵在一个样本要数万元的经费；其次是难！难在有些组织不好处理，单细胞比较难以制备。不过单细胞测序最大的优点就是信息量大，结果更接近事实情况，讲的现实一点，比较好发高分文章。Bulk RNA-seq缺点就是不准确，优点就是便宜，公共数据多，比如TCGA中大量的表达谱数据，任人取用。单细胞的分析，我们以后再说，今天就来讲讲比较亲民的bulk sequencing如何进行免疫浸润的分析。

**分析软件**

　　刚才我们也提到了，分析免疫浸润的软件有很多，十几种之多，今天我们讲讲里面比较常用的一个：CIBERSORT。

![img](C:\Users\Administrator\AppData\Local\YNote\data\297946506@qq.com\dc0fdba053fb4520b2cc14fe69a8e82f\clipboard.png)

为什么，这么多软件我们单独挑了CIBERSORT来讲解呢？原因就在于这是一款非常经典的软件，CIBERSORT是2015年发表于Nature Methods上的文章（IF：28.47）。

CIBERSORT 是基于线性支持向量回归（linear support vector regression）的原理对人类免疫细胞亚型的表达矩阵进行去卷积的一个R/网页版工具。多用于芯片表达矩阵，对未知混合物和含有相近的细胞类型的表达矩阵的去卷积分析优于其他方法 (LLSR,LLSR,PERT,RLR,MMAD,DSA) 。该方法是基于已知参考集，**提供了22种免疫细胞亚型的基因表达特征集：LM22.关于LM22的描述是：它包含547个基因，这些基因可以很好地区别22种人类血液细胞表型，包括7种T细胞，naive 和记忆B细胞，plasma细胞，NK细胞，和myeloid细胞。**

为了方便用户的使用，CIBERSORT被开发成一个网页版的工具，其网址链接：http://cibersort.stanford.edu/.不过，由于CIBERSORT初期版本不支持单细胞测序数据的分析，所以近期又升级到了CIBERSORTX，升级版的网址链接为：https://cibersortx.stanford.edu/

**CIBERSORT的使用方法**

**网页版**

用户只需要注册一个账号，就可获得500M存储数据和结果的空间。操作时，只需上传标准的表达矩阵文件即可分析免疫浸润；如果想要分析包含其他细胞类型的浸润比例，则需按照官网提示的格式上传相应的文件。步骤如下：

- 在网页注册账号
- 准备表达数据
- 需要分析的表达矩阵
- 参考数据集
- 上传数据，设置参数，运行CIBERSORT

**R语言版**

看上去比网页版要求要高一些，最起码你要知道R语言怎么用。不过R语言的CIBERSORT比网页版用上去方便很多，最起码没有数据量的限制，适合大数据运算，也直接运行，非常方便的。基本步骤如下：

- 准备数据
- 需要分析的表达矩阵
- 参考数据集
- 一键运行

可以说，CIBERSORT作者把代码做的非常方便易用，只需一行命令即可运行，下面就进入到我们的实战演练环节，给大家演示以下如何使用CIBERSORT进行免疫浸润的分析。

**准备数据**

　　我们选取的测试数据呢，是TCGA数据库当中LUAD肺腺癌的数据，我们的课题是，比较不同给肿瘤分期G1、G2、G3、G4期的肺腺癌样本中，免疫微环境的差异，探寻宿主免疫在肿瘤进展过程中的作用。先来看一下我们的测试数据：

![img](C:\Users\Administrator\AppData\Local\YNote\data\297946506@qq.com\e6d70ae3e4634334864f528a3a92dd4d\clipboard.png)

　　当然这个截图只是我们数据中很小的一部分，我们的数据有300多行，18000多列，分别对应300多个患者，18000多个基因。

下面就是进行分析了，在进行分析的时候我们需要准备三个文件：

![LM22.txt](C:/Users/Administrator/AppData/Local/YNote/data/297946506@qq.com/3acbb5d974e049f680f2b75b036e6282/attachment.png)

![cibersort.R](C:/Users/Administrator/AppData/Local/YNote/data/297946506@qq.com/6dac79fe7f654085b01a771e3e3c2e29/attachment.png)

1. LM22.txt（可以从CIBERSORT网站下载，这个就是22种免疫细胞的参考marker基因表达）
2. CIBERSORT.R（CIBERSORT源代码，从官网下载：https://cibersort.stanford.edu 账号：fengzhang@ncu.edu.cn）
3. CIBERSORT依赖e1071包。安装install.packages("e1071")
4. expression.txt（基因表达谱文件，就是上面说的肺腺癌表达谱，不需要归一化和log变换）

**R代码运行**

　　然后，运行CIBERSORT非常简单，三个文件放到一个文件夹中，在RStudio中设置工作路径，运行如下代码即可：

安装软件
```
source("CIBERSORT.R") # Define LM22 file LM22_file <- "LM22.txt" exp_file <- "datExp.processed.txt" TME_results = CIBERSORT(LM22_file, exp_file, perm = 1000, QN = TRUE) # output CIBERSORT results write.table(TME_results, "TME_results_output.txt", sep = "\t", row.names = T, col.names = T, quote = F)
```
这个代码看上去是不是很简单呢？没错，就是这么方便。那么，输出的结果长什么样子呢？我们来看一下：

![img](C:\Users\Administrator\AppData\Local\YNote\data\297946506@qq.com\fd81442fdfd84c91ac39fb4739ad7fee\clipboard.png)

每一行一个样本，每一列一种细胞，总共有22种细胞，这里的数值代表的是免疫细胞所占的比例，比如CD8+ T Cell在第一个肿瘤样本中是0.2282，那就代表着在该样本中CD8+ T Cell占总的免疫细胞的22.82%，所以，CIBERSORT输出的是一个比例，22种免疫细胞的比例加起来就等于1。好了，到这里为止，我们获取了300多个肺腺癌样本中的免疫浸润结果，分析到此就可以结束了。

**高级可视化**

首先，我们用箱线图表示22种免疫细胞在所有样本种的比例，在这里看到最高的应该是Naive B cells。
```
\# boxplot ggboxplot(  plot.info,  x = "CellType",  y = "Composition",  color = "black",  fill = "CellType",  xlab = "",  ylab = "Cell composition",  main = "TME Cell composition" ) +  theme_base() +  theme(axis.text.x = element_text(    angle = 90,    hjust = 1,    vjust = 1  ))
```
　　然后，为了比较不同分期之间的免疫细胞的差异，我们使用批量统计比较的箱线图。当然，在这里，不用我说大家都知道，为了比较不同分期之间的差异，我们还需要读入一个样本分期的表型文件。这里我就不做演示了，只把做图的代码放出来。

```
\# box plot group by GRADE ggboxplot(  plot.info,  x = "CellType",  y = "Composition",  color = "black",  fill = "GRADE",  xlab = "",  ylab = "Cell composition",  main = "TME Cell composition group by GRADE" ) +  stat_compare_means(    label = "p.signif",    method = "t.test",    ref.group = ".all.",    hide.ns = T  ) +  theme_base() +  theme(axis.text.x = element_text(    angle = 90,    hjust = 1,    vjust = 1  ))
```
同样的，为了更加直观地感受不同细胞在各个样本中的比例差异，在这里非常适合做一个堆积的比例柱状图，为啥？因为各种细胞比例加起来等于1呀，这个我们刚才讲过了。


```
\# Barplot of cell componment of each sample using hclust sample.index <-  hclust(dist(TME.data[, TME.cells]), method = "ward.D")$order sample.order <- TME.data$PATIENT_ID[sample.index] ggbarplot(  plot.info,  x = "PATIENT_ID",  y = "Composition",  size = 0,  fill = "CellType",  color = "CellType",  order = sample.order ) +  theme_base() +  theme(    axis.text.x = element_text(      angle = 90,      hjust = 1,      vjust = 1,      size = 1    ),    legend.position = "bottom"  )
```

　　好了，以上是我们给大家演示的三种图形，当然还有很多其他的图形可以用于免疫浸润结果的可视化，这些大家在我们的科研绘图板块中学习了这么久，应该可以自行发挥啦。

