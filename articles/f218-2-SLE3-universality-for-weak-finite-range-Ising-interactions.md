---
layout: default
title: "SLE3 universality for weak finite-range Ising interactions"
family: "218"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | SLE3 universality for weak finite-range Ising interactions

> 结果族 218：Conformal universality for weakly interacting and random-bond Ising models　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

蒸馏水掺了微量杂质，冻出的冰花形状会变吗？这篇论文处理数学版的同一个问题：把伊辛磁铁的作用规则添上可正可负的微小"佐料"（有限程扰动，精确可解性随之破坏），临界时那条蜿蜒的相变边界线，放大后是否仍是同一条随机曲线。答案是肯定的——佐料不改变冰花。

**关键词卡片**

- 回路表示（contour representation）：把自旋构型改画成对偶格上的闭合回路，界面是其中一段。
- 有限程扰动（finite-range perturbation）：作用在有限大小自旋集团上的额外小作用项，可正可负。
- 弦 SLE₃（chordal SLE₃）：由布朗驱动 `@@M@@\sqrt3\,B_t@@` 经洛纳方程生成的随机曲线。
- 逆温度（inverse temperature）：温度的倒数；定理保证存在与区域无关的唯一临界值 `@@M@@\beta_c@@`。
- 共形不变（conformal invariance）：区域形状经共形映射改变后，曲线律按规则相应变形。

**看个具体例子**

两种微观规则，一条极限曲线（区域甚至不必光滑，任何若尔当域都行）：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <rect x="30" y="30" width="220" height="150" fill="none" stroke="#333" stroke-width="2"/>
  <path d="M40,170 C80,100 130,150 160,80 C190,60 210,120 240,60" fill="none" stroke="#27ae60" stroke-width="3"/>
  <text x="55" y="200" font-size="15" fill="#333">最近邻规则（可解）</text>
  <rect x="310" y="30" width="220" height="150" fill="none" stroke="#333" stroke-width="2"/>
  <rect x="340" y="50" width="26" height="26" fill="none" stroke="#e67e22" stroke-width="2"/>
  <rect x="470" y="120" width="26" height="26" fill="none" stroke="#e67e22" stroke-width="2"/>
  <path d="M320,170 C360,110 410,160 440,80 C470,60 500,120 520,70" fill="none" stroke="#27ae60" stroke-width="3"/>
  <text x="335" y="200" font-size="15" fill="#333">加扰动（橙色小块）</text>
  <path d="M150,212 L150,236" stroke="#333" stroke-width="2"/>
  <path d="M144,228 L150,240 L156,228" fill="none" stroke="#333" stroke-width="2"/>
  <path d="M410,212 L410,236" stroke="#333" stroke-width="2"/>
  <path d="M404,228 L410,240 L416,228" fill="none" stroke="#333" stroke-width="2"/>
  <text x="120" y="266" font-size="15" fill="#8e44ad">两种微观规则 → 同一条弦 SLE₃</text>
</svg>

</div>

数字版基准：`@@M@@\beta_c(J,U,0)=\ln(1+\sqrt2)/(2J)\approx 0.441/J@@`；扰动后 `@@M@@\beta_c@@` 会移动，但不再依赖区域形状与边界数据。

**为什么值得关心**

不可积模型的临界界面共形不变性是 Smirnov 纲领的终极考验之一，本文不依赖任何可积结构就抵达了 SLE₃。这也说明共形不变性并不是可解模型的专利，而是临界现象的内在属性。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了：平面伊辛回路能量加上充分小、平方对称、可正可负的有限程扰动后，存在与域无关的逆温度 `@@M@@\beta_c@@`，使自旋界面按完整定向曲线律收敛到弦 `@@M@@\mathrm{SLE}_3@@`——不可积情形的临界界面共形不变普适性成立。

## 问题背景

2000 年 Schramm 用洛纳演化（Loewner evolution）把共形不变随机界面描述为一维驱动过程；Smirnov 证明临界 FK-伊辛费米子观测量（fermionic observable）的共形协变后，CDHKS（2014）证明了最近邻临界伊辛自旋界面收敛到弦 `@@M@@\mathrm{SLE}_3@@`。普适性问题是：破坏可积性的微观相互作用是否保留这一极限？关联函数层面已有构造性重整化结果（GGM 2012、AGG 2023 等），但完整界面律难度更高：Greenblatt–Peltola（2024）把探索过程的局部鞅表为 Grassmann 关联比并提出通往 `@@M@@\mathrm{SLE}_3@@` 的猜想 4.5，其困难之一是估计必须从固定几何推广到探索产生的不规则边界。此外，带符号的扰动会破坏铁磁单调比较，使常规单调性论证失效。

## 主要结果

模型：位势 `@@M@@U@@` 赋予对偶边有限子集实值，有限程且具方格对称性；在允许内部回路集 `@@M@@\mathcal P_\Omega^\xi@@` 上取律 `@@M@@\mu\propto\exp\{-2\beta J|P|-\beta\lambda\sum_{\varnothing\ne X\subseteq P}\sum_{Y\subseteq P_o}U(X\cup Y)\}@@`，其中 `@@M@@P_o@@` 是含两个外部短柄的任意容许外部回路，界面 `@@M@@\gamma(P)@@` 按固定规则解析偶价点并定向。定理：对 `@@M@@|\lambda|<\lambda_0(J,U)@@`，存在正逆温度 `@@M@@\beta_c(J,U,\lambda)@@`，与域和边界数据无关，`@@M@@\beta_c(J,U,0)=\frac{\log(1+\sqrt2)}{2J}@@`，使得对任意有界若尔当域（Jordan domain，不要求光滑）、边界点 `@@M@@a,b@@`、一致逼近边界的任意网格域列与任意容许外部回路列，`@@M@@\delta_n\gamma(P_n)@@` 在"模掉递增重参数化的均匀距离"度量下依分布收敛到 `@@M@@D@@` 中从 `@@M@@a@@` 到 `@@M@@b@@` 的弦 `@@M@@\mathrm{SLE}_3@@`（由驱动过程 `@@M@@\sqrt3 B_t@@` 的洛纳轨迹经共形映射定义）。结论是完整定向曲线律，不预设任何可观测量收敛或紧性猜想。

## 证明思路

先做精确的自旋换算：偶回路集与"无穷远处加号、每穿越一条占据对偶边变号"的自旋构型一一对应，回路律恰是带外部自旋 `@@M@@\tau@@` 的有限程偶自旋相互作用的吉布斯条件律；两条边界弧外部符号恒定且相反，外部回路只通过真实外部自旋起作用，不引入额外体参数。第二步定义线性转移算子：把方块内有界自旋函数条件到 `@@M@@L@@` 倍同心方块的边界自旋上并乘 `@@M@@L^2@@`。首要障碍是反复转移生成依赖任意多自旋的函数，固定插入数的公式控制不了。作者让每个自旋通过微弱高斯信号被观测，条件律仍保持铁磁性；再用工具篇的有序源传输与邻近预测压过正向间隙，把任意有界自旋函数的转移归结为显式自旋公式；反射正性（reflection positivity）与一个行列式恒等式表明，偶的方格不变密度中恰有一个标量方向在此转移下增长。第三步用"反向生成元恒等式"把线性转移升级为精确尺度流：位势移向条件期望可由速率与自旋无关的局部刷新反向实现；正的长程能量协方差使温度方向与衰减轨迹集合横截，故仅凭体数据即可选出与域无关的 `@@M@@\beta_c@@`。倒向运行此流，环面自旋律与纯模型律耦合，误差只来自标记概率随尺度衰减的独立标记方块。第四步证明这些修改以趋于 1 的概率保持一切有限多边形穿越、回路与四通道测试：方块内的修改只有在四条长回路段同时抵达时才能改变测试答案，其概率衰减快于位置数目增长，严格阈值来自自旋四臂指数（four-arm exponent）`@@M@@21/8>2@@`；对尺度的自举使结论对标记方块内任意事后选定的赋值成立。第五步处理边界：把小相互作用用近邻键上的附加二元变量表示，其条件概率在"减钉扎、自由、加钉扎"的改变间有严格边际，由此恢复边界比较并给出密度比控制。最后构造两个分别有利于相反颜色的纯模型比较域；任何子列极限中，屏障与目标轨迹的连通性把两条极限简单弦排序，两者同为 `@@M@@\mathrm{SLE}_3@@` 故重合并识别出轨迹；持续反向绕行会在小环内造成六次穿越，被四通道估计排除，从而得到完整定向曲线度量下的收敛。

## 可信度与备注

本文结果未形式化，属长程构造性论证，请以社区核验为准；OpenAI 声明"未经形式化的结果可能有问题"。姊妹篇中，体关联篇在同一"精确尺度流 + 温度分支"框架下得到混合关联极限，工具篇提供有序源传输等纯模型输入，三篇互相印证。注意本文并未证明 Greenblatt–Peltola 猜想 4.5 中的费米子渐近公式，而是经由有界自旋观测量与稀疏修改的另一条路线。

{% endraw %}
