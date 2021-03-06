### 人工智能课程作业

#### 第一章-绪论

##### 实验课-01

1. 请简要描述图灵测试以及它的重要特征。

   **图灵测试：一台机器要通过图灵测试，它需要有下面的能力**：

   * 自然语言处理：实现用自然语言与计算机进行交流。
   * 知识表示：存储它知道的或听到的、看到的。
   * 自动推理：能根据存储的信息回答问题，并提出新的结论。
   * 机器学习：能适应新的环境，并能检测和推断新的模式。
   * 计算机视觉：可以感知物体。
   * 机器人技术：可以操纵和移动物体。

   **图灵测试重要特征如下**：

   * 它给出了一个客观的智能概念，也就是根据对一系列特定问题的反应来决定是否是智能体的行为。这为判断智能提供了一个标准，从而避免了相关的必然争论。
   * 这项实验使我们免于受到诸如以下目前无法回答的问题的牵制：计算机使用的内部处理方法是否恰当或者机器是否真的意识到其动作。
   * 通过使询问者只关注回答问题的内容，消除了有利于生物体的偏置.

   因为图灵测试具有这些重要特征，它已成为许多现代人工智能程序评价方案的基础。

2. 什么是人工智能？它的研究目标是什么？

   **人们试图用4种方法给出人工智能的定义**：

   * 类人行为系统(Systems that act like human)

     这种观点与**图灵测试**的观点很吻合。

   * 类人思维系统(Systems that think like human)

     主要采用的是认知模型的方法 -- 关于人类思维工作原理的可检测的理论。目的是要对人类大脑的工作原理给出准确和可测试的模型。

   * 理性思维系统(Systems that think rationally)

   * 理性行为系统(Systems that act rationally)

   **人工智能的研究目标**：
   
   人工智能主要研究用人工的方法和技术，模仿、延伸和扩展人的智能，实现机器智能。人工智能的长期目标是实现人类水平的人工智能。
   
3. 请列举出人工智能研究的主要应用领域。

   * 机器学习
   * 知识发现和数据挖掘
   * 专家系统
   * 识别模式
   * 自然语言处理
   * 智能决策支持系统
   * 人工神经网络
   * 自动定理证明
   * 机器人学
   * 分布式人工智能与智能体
   
4. 请简述知识工程。

   知识工程可以看成是人工智能在知识信息处理方面的发展，研究如何由计算机表示知识，进行问题的自动求解。知识工程的研究使人工智能的研究从理论转向应用，从基于推理的模型转向基于知识的模型，包括了整个知识信息处理的研究，知识工程已成为一门新兴的边缘学科。

#### 第二章-知识表示

##### 实验课-02

一. 用谓词公式将下列语句表示出来

1. 有的人喜欢梅花，有的人喜欢菊花，有的人既喜欢梅花又喜欢菊花。

   定义谓词 Person(X)：X是人；Like(X,Y)：X喜欢Y。其中Y的个体域为：{梅花，菊花}

   将知识用谓词表示为：∃(x)(Person(x)→Like(x，梅花)∨Like(x，菊花)∨Like(x，梅花)∧L(x，菊花)))

2. 老李每天下午都去玩足球。

   定义谓词 Time(X):X是某个时间；Play(X,Y):X去玩Y。

   将知识用谓词表示为：∀(Time(下午))→Play(老王，足球)

3. 曹县的夏天干燥又炎热。

   定义谓词 Summer(X)：X地的夏天；Dry(X)：X是干燥的；Hot(X)：X是炎热的。

   将知识用谓词表示为:Dry(Summer(曹县))∧Hot(Summer(曹县))

4. 所有人都有饭吃。

   定义谓词 Person(X)：X是人；Eat(X)：X有饭吃。

   将知识用谓词表示为: ∀(x)(Person(x)→Eat(x))

5. 喜欢玩篮球的人必喜欢玩排球。

   定义谓词 Person(X)：X是人；Like(X,Y)：X喜欢玩Y。

   将知识用谓词表示为: ∀(x)(Person(x)→Like(x,篮球)∧Like(x,排球))

二. 用语义网络表示下列知识:

(1)所有的鸽子都是鸟;

![QQ截图20210526121639](https://gitee.com/bai_xiao_fei/picture/raw/master/pic//QQ%E6%88%AA%E5%9B%BE20210526121639.png)

(2)所有的鸽子都有翅膀;

![image-20210520170320758](https://gitee.com/bai_xiao_fei/picture/raw/master/pic//image-20210520170320758.png)

(3)信鸽是一种鸽子,它有翅膀,能识途。

![image-20210520170457921](https://gitee.com/bai_xiao_fei/picture/raw/master/pic//image-20210520170457921.png)

**总图：**

![QQ截图20210526080430](https://gitee.com/bai_xiao_fei/picture/raw/master/pic//QQ%E6%88%AA%E5%9B%BE20210526080430.png)

三. 试写出“学生框架”的描述。

框架名：<学生>

类属：<在学校接受教育的人>

工作：范围：（学习知识，掌握技能，交朋友）

​			缺省：学习知识

性别：（男，女）

类别：（<幼儿园学生>、<小学生>、<中学生>、<高等院校学生>）

#### 第三章-搜索策略

##### 实验课-03

用启发式搜索算法A或者A*解决下面的八数码问题，并给出搜索结束时OPEN表和CLOSE表内容

评价函数 f(x) = g(x) + h(x)，其中h(x)的含义可以自己定义。

![eight-figure-puzzle](https://gitee.com/bai_xiao_fei/picture/raw/master/pic//eight-figure-puzzle.png)

**解：**

![Astar](https://gitee.com/bai_xiao_fei/picture/raw/master/pic//Astar.png)

![OC](https://gitee.com/bai_xiao_fei/picture/raw/master/pic//OC.png)

##### 实验课-04

1. 把下面的谓词公式化成子句集

![lab4-q1](https://lqin2333.gitee.io/artificial_intelligence_class/images/lab4-q1.JPG)

解：原式=>(∀x)(∃y)(P(x, y)v(~Q(x,y)vR(x,y)))

=>(∀x)(P(x,f(x))v(~Q(x, f(x) )vR(x, f (x))))

所求子句集为S={P(x,f(x))v(~Q(x,f(x))vR(x,f(x,y)))

2. 用归结反演法证明下面公式的永真性

[提示:先否定它，然后化成子句集，再实施归结和置换，得到最终的NIL(空子句)] 

![lab4-q2](https://lqin2333.gitee.io/artificial_intelligence_class/images/lab4-q2.JPG)

(∃x) {[P(x)→P(A)]∧[P(x)→P(B)]}

目标取反化子句集:

~ (∃x){[P(x)→P(A)]∧[P(x)→P(B)]}

~ (∃x){[~ P(x)∨P (A) ]∧[~ P(x)∨P(B)]}

(∀x){[P(x)∧~ P(A)]∨[P(x)∧~ P(B)]}

(∀x){[P(x)∧~ P(A)]∨P(x)}^{[P(x)∧~ P(A)]∨~ P(B)}}

(∀x){P(x)∧[~ P(A)∨P(x)]^[P (x)∨~ P(B)]^[~ P(A)∨~ P(B)]}

P(x)∧[~ P(A)∨P(x)]∧[P(x)∨~ P(B)]^[~ P(A)∨~ P(B)]

得子句集:

1、P(x1)

2、~P(A)∨P{x2}

3、P(x3)∨~P(B)

4、~ P(A)∨~ P(B)

![image-20210603164651177](https://gitee.com/bai_xiao_fei/picture/raw/master/pic//image-20210603164651177.png)

#### 第三章-确定性推理

##### 实验课-05

1.设有如下知识:

R: IF E1 THEN (20,1) H1(0.06)
R2: IF E2 THEN (10,1) H2(0.05)
R3: IF E3 THEN (1,0.08) H3(0.4)

求: 当证据E1, E2, E3存在时, P(Hi | Ei) 的值各是多少?

![image-20210616232752111](https://gitee.com/bai_xiao_fei/picture/raw/master/pic//image-20210616232752111.png)

2.设有如下规则:

R1: IF E1 THEN H (0.8)
R2: IF E2 THEN H (0.6)
R: IF E3 THEN H (-0.5)
R4: IF E4 AND (E5 OR E6) THEN E1 (0.7)
Rs :IF E7 AND E8 THEN E3 (0.9)
且已知
CF(E2) = 0.8, CF(E4) = 0.5, CF(E5) = 0.6, CF(E6) = 0.7, CF(E7) = 0.6, CF(E8) = 0.9

求: H 的综合可信度 CF(H)。

![image-20210616232637352](https://gitee.com/bai_xiao_fei/picture/raw/master/pic//image-20210616232637352.png)

![image-20210616232707621](https://gitee.com/bai_xiao_fei/picture/raw/master/pic//image-20210616232707621.png)

3.设 Ω = {红,黄,绿}, 有如下概率分配函数

m({∅},{红}, {黄}, {红, 黄}, {绿}, {红, 黄, 绿}) = (0, 0.5, 0.2, 0.1, 0.1, 0.1)
设 A = {红, 黄},

求:m(Ω)、Bel(A) 和 Pl(A) 的值。

![image-20210616232727684](https://gitee.com/bai_xiao_fei/picture/raw/master/pic//image-20210616232727684.png)
