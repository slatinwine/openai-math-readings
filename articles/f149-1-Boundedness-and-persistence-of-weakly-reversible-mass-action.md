---
layout: default
title: "Boundedness and persistence of weakly reversible mass-action systems"
family: "149"
discipline: "Dynamical systems and ergodic theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Boundedness and persistence of weakly reversible mass-action systems

> 结果族 149：Classwise permanence for weakly reversible mass-action systems　·　学科：Dynamical systems and ergodic theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明了弱可逆质量作用系统的有界性猜想与持久性猜想：对任意正初值与任意正速率常数，解整体存在，且每个浓度始终被同一对正的上下界夹住；界可依赖初值，且完全不对化学计量相容类施加有界性假设。

## 问题背景

化学反应网络中，若每条反应都存在有向返回路径，则称网络弱可逆（weakly reversible）。质量作用动力学（mass-action kinetics）给出多项式向量场，其正轨迹被困在化学计量相容类（stoichiometric compatibility class）内，而该类可以无界——无界类上的轨迹会不会爆炸，或让某物种浓度趋零，是 Horn–Jackson 与 Feinberg 奠基理论以来悬而未决的核心问题。Anderson（2011）把它拆成两个猜想：有界性猜想（boundedness conjecture，轨迹有界）与持久性猜想（persistence conjecture，有界轨迹远离边界坐标平面）。August 与 Barahona（2010）曾宣布一般结论，但本文指出其证明第 III 部分由"指数和最大、浓度乘积大"推出单项式占优的一步并不成立（文中给出反例 `@@M@@2A\rightleftarrows B@@`、速率全一、`@@M@@(a,b)=(T,T^3)@@`：`@@M@@ab\to\infty@@` 而 `@@M@@a^2<b@@`，且 `@@M@@\dot a+\dot b=T^3-T^2>0@@`）；不过由于该例中 `@@M@@a+2b@@` 守恒，这只是证明的缺口，并不推翻其定理陈述。既有严格结果各带限制：单连通类（Anderson 2011；Gopalkrishnan–Miller–Shiu 2014；Boros–Hofbauer 2020）、两物种（Craciun–Nazarov–Pantea 2013）、二维化学计量空间（Pantea 2012），或需预设轨迹有界（Craciun 2026 的环面微分包含方法）。本文在常速率下同时证明两个猜想，不限物种维数与连通类（linkage class）个数。

## 主要结果

主定理（01-introduction.tex 定理 1.1）：对任意正初值 `@@M@@x^0\in\R_{>0}^d@@`，解对一切 `@@M@@t\geq0@@` 整体存在，且存在 `@@M@@\varepsilon\in(0,1)@@`（依赖网络、速率与 `@@M@@x^0@@`）使 `@@M@@\varepsilon\leq x_i(t)\leq\varepsilon^{-1}@@` 对所有 `@@M@@t\geq0@@` 与所有坐标成立——注意是从零时刻起的全程界，而非仅渐近界。由此每个 `@@M@@\omega@@` 极限集非空且避开卦限边界。几何强化（03-dynamics.tex 命题 prop:polytope）：每个正点 `@@M@@x^0@@` 都属于某个含于正卦限的紧凸多胞形（polytope）`@@M@@K@@`，从 `@@M@@K@@` 出发的解整体存在且永驻 `@@M@@K@@`；`@@M@@K@@` 在环境物种空间中构造，可以横跨多个相容类。两个推论：把 `@@M@@K@@` 与相容类相交后用 Brouwer 不动点定理，恢复 Boros（2019）"每个正相容类都含正平衡点"的存在定理；在复杂平衡（complex-balanced）假设下，配合 Horn–Jackson 熵型 Lyapunov 函数与 LaSalle 不变性原理，得到每条正轨迹收敛到其类中唯一正平衡点的全局吸引子结论（对一切亏格零（deficiency zero）网络自动适用）。文中明确声明：不断言同一个 `@@M@@\varepsilon@@` 对全类初值通用——该升级由姊妹篇完成。

## 证明思路

整个证明围绕一个核心障碍：需要一族有限线性不等式同时控制浓度过小与过大，但单条反应未必指向区域内部，估计必须落在"跨越反应图各层切割的组合通量"上；而近平局时任意的法向逼近都可能翻转比较，因此逼近必须尊重所有平局。为此选择顺序严格固定：`@@M@@D\to E\to\Lambda\to(h_0,H)\to h@@`，即先定容差、再定斜率族、最后才定尺度，使符号间隙 `@@M@@H@@` 是不随 `@@M@@h@@` 消失的常数。

先构造仿射族（第 2 节）。把盒子 `@@M@@B_h=[h,h^{-1}]^d@@` 参数化为 `@@M@@X_h(p)=(h^{p_1},\dots,h^{p_d})@@`，构造有限仿射最小 `@@M@@F_h(x)=\min_\lambda(r_\lambda\cdot x+c_\lambda(h))@@`：对任意给定的正容差 `@@M@@E@@`（允许不连续），活跃标签（active label）满足 `@@M@@\norm{p-r_\lambda}_\infty<E(r_\lambda)@@`。容差取比较方向集 `@@M@@D@@`（坐标向量与所有络合物之差——因为通量比较须在全部络合物对之间进行，甚至跨连通类）上的符号保护值，使非零斜率比较与指数比较同号且带一致间隙；指数空间中的近平局被活跃斜率做成精确平局。于是低层源的单项式（monomial）压制高层：`@@M@@r_\lambda\cdot y<r_\lambda\cdot z\Rightarrow x^z\leq h^H x^y@@`。

再做抽象的切割通量引理（第 3 节 lem:cut-flux）：有限有向图上每条边都有返回路径，顶点水平为 `@@M@@a@@`、权重 `@@M@@w>0@@` 满足"低层权重压制高层"，且 `@@M@@\delta\sum\kappa<\min\kappa@@`，则总通量 `@@M@@\sum_e\kappa_e w_{s(e)}(a(t(e))-a(s(e)))\geq0@@`。证明将边按水平切割分解：弱可逆性保证有下穿就有上穿，且权重压制使单条向上边的通量压过全部向下通量之和。以 `@@M@@a(y)=r_\lambda\cdot y@@`、`@@M@@w_y=x^y@@`、`@@M@@\delta=h^H@@` 代入，得 `@@M@@r_\lambda\cdot f(x)\geq0@@` 对一切活跃标签成立。

最后组装陷阱（第 3 节末）。有限仿射最小沿可微曲线的右导数等于活跃支导数的最小值，故 `@@M@@F_h@@` 沿盒内解段不降。取 `@@M@@h@@` 使 `@@M@@x^0@@` 的对数坐标范数小于 `@@M@@H@@`，则 `@@M@@x^0@@` 处活跃斜率全为零，得到常数支与全局天花板 `@@M@@M=F_h(x^0)@@`；最大集 `@@M@@K=\{F_h=M\}@@` 与盒边界不相交（否则活跃性迫使 `@@M@@\norm{p}_\infty<1/2@@`），再用凸性把整块 `@@M@@K@@` 关进盒内部，成为紧凸多胞形。从 `@@M@@K@@` 出发的解因"`@@M@@F_h@@` 不降 + 天花板 `@@M@@M@@`"被钉在 `@@M@@K@@` 上；首次逃逸论证排除触碰盒边界，紧集上向量场有界给出延拓，解整体存在。全程不需要盒子之外的任何活跃标签估计。

## 可信度与备注

本文暂无形式化证明，按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。姊妹篇（2026 年 10 月 5 日手稿）在本文基础上把逐轨迹的界升级为逐类一致的持久性：它完整复现本文的仿射逼近引理与推论（即其引理 2.1、推论 2.2 的出处）并改造陷阱构造，两文共享同一套"水平切割 + 返回路径通量占优"机制，互为支撑。另注：本文对 August–Barahona（2010）的分析只指出其证明中一步推理的缺口，并给出了具体反例，但并未否定其定理陈述本身。

{% endraw %}
