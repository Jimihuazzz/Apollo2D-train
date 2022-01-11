# 一些简单的人工智能指路 For Apollo 2D

### 作者  很多深度学习/数学大神

>做了一点微小的整理工作 鸡米花（Sy03）

## 前置知识以及废话

### 前置知识

概率论基础

信息论基础

Python基础

线性代数和高数

>假如上面都没有，那么耐心，求知欲和时间就够了

### 废话
    
    于总的push让我意识到，我需要做一些简单的整理工作，方便为2D组内的大神们开辟道路。

    这个文档里面包括简单的概念，简单的应用（无代码，但是会有详细的教程整理给出）。
    
    最后我会给出Apollo可以应用的一些想法，或许我在Apollo的时间我不能完成这些想法。
    但是希望如果有可以实际应用的好的想法，可以被后来人实现。

    最后的最后，感谢于总（KawhiCurry），和林总（叁或）以及2D组内组外很多人的帮助。

## 简简单单一个配置环境
Mac：
https://www.bilibili.com/video/BV11h411Q7yK?from=search&seid=10948316564457744323&spm_id_from=333.337.0.0

Win:
https://www.bilibili.com/video/BV1oz411v7cv?from=search&seid=2686095124124084599&spm_id_from=333.337.0.0

https://www.bilibili.com/video/BV1Lv41177BW?from=search&seid=2686095124124084599&spm_id_from=333.337.0.0

    Anaconda必须装 python多版本管理很有用
    Cuda Cudnn也是必须安装

    框架按需选择 TensorFlow（python）/caffe（C++） 

    推荐前者，谷歌爸爸好（不过Apollo实际需要用到这些吗...?）

    

## 贝叶斯滤波器

**先看百度百科或者Wiki**
    
    百度的可以自行搜索但是看了意义不大（个人观点）

    贝叶斯概率 这个和分类器关系不大，但是我推荐一看（至少收藏）
    https://en.wikipedia.org/wiki/Bayesian_probability

    （朴素）贝叶斯分类器
    https://en.wikipedia.org/wiki/Naive_Bayes_classifier

    wiki后面的paper很有用，有兴趣的可以看看



**下面是推荐阅读的Paper**

我的选择原则满足其一 

1.门槛不高  2.门槛较高，但略去推导也至少可以帮助你理解思想

    待更新


**言归正传到贝叶斯**

简单的人话理解（必看）

    https://zhuanlan.zhihu.com/p/75880143

朴素推导（推荐） 

    https://zhuanlan.zhihu.com/p/139215491

这部分是公式的展开部分，纯数学（按需）

    https://blog.csdn.net/love__live1/article/details/83307814


###### 简单总结：
    概念 
    Smoothing（没有很好的翻译，我称为平滑更新）
    prediction（很好理解）
    初始化+预测步（动态）+更新步（动态）+后期工作
    贝叶斯分类器只是一种方法，很难完全使用这个进行复杂的深度学习
## 马尔科夫模型/树 （决策树的基础）

**我的个人理解，这是现在很多“复杂决策分支算法”的基础。**

### 概念
    视频讲解（全面，中文讲解，英文展示，建议有时间看完）
    https://www.bilibili.com/video/BV1Et4y167Ak?p=19
## 欠拟合/过拟合
    前者 数据集不够或者种类太过于单一
    后者 学训练集学傻了，最后呈现的模型基本都是噪声数据


## 关于梯度消失/爆炸
    这是两个完全对立的概念，但是方便起见我就一起说了。
    https://zhuanlan.zhihu.com/p/25631496

## 有趣的实例/资料

### 卡尔曼滤波+OpenCv预测小球轨迹 

    https://www.bilibili.com/video/BV1dQ4y1m7ZC?spm_id_from=333.1007.top_right_bar_window_default_collection.content.click

这个是卡尔曼滤波和OpenCV的结合，很有必要动手试试看

我的想法，可以通过这个，以及记录对方站位的数据集来预测对方站位可以达到

1.快速切换模式（比如说，进攻中的快速反击/控球），我认为单纯的通过持球与否来改变阵型还不够

2.改变一些参数，和1想法一致但是更为细节

3.甚至说利用预测对方站位，来训练2V5能力（即进攻）


### HFUT视频培训-Robocup2D

Yushan的培训

很有意思，讲的挺好

    https://space.bilibili.com/10322956?spm_id_from=333.788.b_765f7570696e666f.1

### 运动规划的课 

专门分析轨迹的，我没有看完所以判断不了是否完全有用，不过讲的还算清晰。

有兴趣的做自动驾驶的同学其实用处会很大
    https://github.com/teamo1996/Motion-plan

