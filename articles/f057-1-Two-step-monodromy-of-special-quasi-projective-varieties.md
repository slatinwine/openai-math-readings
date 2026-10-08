---
layout: default
title: "Two-step monodromy of special quasi-projective varieties"
family: "057"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Two-step monodromy of special quasi-projective varieties

> 结果族 057：Fundamental groups of special complex varieties and root orbifolds　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

上一篇说"温和的封闭空间"绕圈目录近乎交换；这次空间是敞开的（挖掉了点或曲线），目录允许更乱一些：可以像上三角矩阵那样不交换，但乱不出两层结构。论文证明：把这种开空间的基本群用矩阵具体写出来，矩阵群在有限指标后必是"两步幂零"——乱不到第三层。

**关键词卡片**

- 拟射影簇（quasi-projective variety）：射影空间挖掉一块之后得到的开几何
- 幂零类（nilpotency class）：换位子链叠几层归零；类 ≤2 即三重换位子恒为零
- 线性表示（linear representation）：把抽象群实现成具体矩阵的方式
- Heisenberg 群：3×3 上三角单位矩阵群，"两步幂零"的标准样板
- 拟-Albanese 映射（quasi-Albanese map）：开空间到"环面＋线性空间"的万有平均映射

**看个具体例子**

样板群就是 Heisenberg 群：元素由三个整数 (a,b,c) 记账，乘法把坐标相加；两个元素的换位子永远缩到最角落的中心格，再往外套一层换位子必为零。

`@@M@@DH_3(\mathbb{Z})=\left\{\begin{pmatrix}1&a&c\\0&1&b\\0&0&1\end{pmatrix}\right\},\qquad [A,B]=\begin{pmatrix}1&0&1\\0&1&0\\0&0&1\end{pmatrix}\ \text{（落在中心）}@@`

定理断言：special 拟射影簇的基本群，其任何复矩阵像都含这个形状的有限指标子群。几何原型：椭圆曲线去掉一个点，基本群正是 Heisenberg 型中心扩张，说明"两步"是不可再降的界。论文还造出反例开曲面：special 曲面的拟-Albanese 一般纤维可以不 special，修正了先前文献的断言。

**为什么值得关心**

它给出开情形"群能乱到几层"的精确上限，提供了独立于原宣布证明的新路线，并顺带纠正了相关猜想的错误表述。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
独立证明：连通光滑 special 拟射影簇的基本群，其任何复线性表示的像都有幂零类至多二（"两步"）的有限指标子群；并构造一般拟-Albanese 纤维不 special 的 special 开曲面，修正了相关文献的纤维 specialness 断言。

## 问题背景
紧情形的 Campana 交换性猜想（本族姊妹篇已在任意维数证明）断言 special 紧 Kähler 流形的基本群虚拟交换，但开情形（拟射影簇）允许真正的非交换幂零群：Cadorel–Deng–Yamanoi（CDY）构造过 special 拟射影曲面——椭圆曲线上度一线丛挖去零截面的补集——其基本群是 Heisenberg 型中心扩张，不虚拟交换，故"二步幂零"是开情形的正确且最优的界。CDY 先证明了线性像虚拟幂零；Cao–Deng–Hacon–Păun（CDHP）随后宣布了最优的二步结论。本文从 CDY 的几何输入出发，配合一个新的单幂零完备结构定理，给出不依赖 CDHP 论证的独立证明；同时用反例指出 CDHP 论文里另一断言（一般拟-Albanese 纤维 special）有误。本文的 special 采用 CDY 的开簇约定：任意真双有理修改后，每个连通纤维化到正维正规拟射影底的 orbifold 底小平维数严格小于底维数。

## 主要结果
定理一（两步线性单态，thm:linear）：设 `@@M@@V@@` 为连通光滑 special 复拟射影簇，则对任意 `@@M@@d@@` 与表示 `@@M@@\rho:\pi_1(V)\to\GL_d(\C)@@`，像 `@@M@@\rho(\pi_1(V))@@` 含幂零类 `@@M@@\le2@@` 的有限指标子群（即虚拟二步幂零）。定理二（拟-Albanese 正合下的完备定理，thm:completion）：设代数拟-Albanese 映射（quasi-Albanese map，到半阿贝尔簇 semiabelian variety 的万有映射）`@@M@@a:V\to A@@` 占优、一般纤维 `@@M@@F@@` 光滑连通，且普通基本群序列 `@@M@@\pi_1(F)\to\Gamma=\pi_1(V)\xrightarrow{a_*}\pi_1(A)\to1@@` 正合，则 `@@M@@\Gamma@@` 的有理单幂零完备（rational unipotent completion）的每个典范商幂零类 `@@M@@\le2@@`，完备本身有限维，且每个复单幂零表示的像类 `@@M@@\le2@@`。推论：对数小平维数 `@@M@@\bar\kappa(V)=0@@` 的光滑拟射影簇同样成立。定理三（反例曲面，thm:example）：在 `@@M@@E\times\PP^1@@`（`@@M@@E@@` 椭圆曲线）中爆破 `@@M@@n\ge3@@` 个点 `@@M@@(e_i,q_i)@@` 后删去 `@@M@@n@@` 条水平椭圆曲线 `@@M@@E\times\{q_i\}@@` 的严格变换得 `@@M@@X@@`，则 `@@M@@(Y,D)@@` 在 CDHP 约定（含一切 upper model）下 special，`@@M@@X\to E@@` 是拟-Albanese 映射，一般纤维 `@@M@@\PP^1\setminus\{n\text{ 点}\}@@` 对数典范度 `@@M@@n-2>0@@` 不 special，且 `@@M@@\pi_1(X)\simeq\Z^2@@`。

## 证明思路
完备定理的核心是混合 Hodge 结构（mixed Hodge structure，MHS）的权论证。对每个典范 `@@M@@c@@` 步商 `@@M@@U_c=\exp(\mathfrak g_c)@@`，设 `@@M@@\mathfrak k_c@@` 为纤维群像的 Zariski 闭包的李代数。先证 `@@M@@\mathfrak k_c=[\mathfrak g_c,\mathfrak g_c]@@`：拟-Albanese 映射在 `@@M@@H_1@@` 上是同构，故 `@@M@@[\Gamma,\Gamma]\subseteq N@@`（纤维群像）；反之 `@@M@@N@@` 中每个元有正幂落入换位子群，而单幂零群的交换化是无挠向量群，故 `@@M@@N@@` 在商 `@@M@@U_c/[U_c,U_c]@@` 中像为零，结合稠密性与正规性得反包含。再看 `@@M@@\mathfrak k_c@@` 的交换化 `@@M@@B_c@@`：它既是 `@@M@@H_1(F,\Q)@@`（光滑拟射影纤维，权只有 `@@M@@-1,-2@@`）的商，又位于权 `@@M@@\le-2@@` 的层内，由 MHS 态射的严格性知 `@@M@@B_c@@` 纯权 `@@M@@-2@@`——这是纤维几何进入证明的唯一入口。随后括号 `@@M@@\mathfrak g_c\otimes\mathfrak k_c\to B_c@@` 是 MHS 态射，源权 `@@M@@\le-3@@` 而靶 `@@M@@W_{-3}=0@@`，故为零，即 `@@M@@[\mathfrak g_c,\mathfrak k_c]\subseteq[\mathfrak k_c,\mathfrak k_c]@@`；代入 Jacobi 型下中心列估计得 `@@M@@\gamma_3\mathfrak g_c\subseteq\gamma_4\mathfrak g_c@@`，幂零性逼出 `@@M@@\gamma_3\mathfrak g_c=0@@`。取逆向极限后完备在 `@@M@@c=2@@` 处稳定，再经基域扩张的泛性质把界传给任意复单幂零表示。定理一的推导：先用 CDY 定理 A 把 Zariski 闭包单位元分量写成 `@@M@@U\times T@@`（单幂零乘环面），经代数 Riemann 存在定理取对应 `@@M@@\rho^{-1}(L^0)@@` 的有限覆盖 `@@M@@V_0@@`；specialness 有限覆盖保持，CDY 引理又给出 `@@M@@V_0@@` 上拟-Albanese 的占优与正合性（此步关键：单幂零完备在限指标子群上可能改变，必须对新覆盖重新用正合性），于是完备定理适用，单幂零部分类 `@@M@@\le2@@`、环面部分交换，三重换位子消失。反例曲面的验证则用完全椭圆圆截线与 orbifold Riemann–Hurwitz 在每个 upper model 上检验 specialness，用完全截面与无非常数可逆函数确立拟-Albanese 泛性质，穿过被保留例外曲线的局部圆盘杀死穿刺环得 `@@M@@\pi_1(X)\simeq\Z^2@@`；其机制在于每个 `@@M@@q_i@@` 上方的完全纤维同时含一条被删与一条被保留的分量一分支，直接 orbifold 重数为 `@@M@@1@@`，而先收缩再算底会遗忘被保留分支的贡献——这正是 Campana 组合规则（composition rule）记录的例外除子条件，也是 CDHP Claim 7.17 把 Iitaka 底上的平坦性误用作另一收缩中间空间平坦性的错误所在。

## 可信度与备注
主结果暂无形式化证明。二步结论的首功属于 CDHP（本文明确声明）；本文的独立价值在于新完备定理、更透明的 MHS 证明，以及对 CDHP 纤维 specialness 断言（arXiv:2603.14539v2 定理 E）的反例修正。普通基本群本身的虚拟二步幂零性（CDHP 猜想 2.12）仍是公开问题，障碍是完备映射可能不忠实。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
