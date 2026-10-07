---
layout: default
title: "Uniform Permanence in Weakly Reversible Mass-Action Systems"
family: "149"
discipline: "Dynamical systems and ergodic theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Uniform Permanence in Weakly Reversible Mass-Action Systems

> 结果族 149：Classwise permanence for weakly reversible mass-action systems　·　学科：Dynamical systems and ergodic theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明了弱可逆质量作用系统的持久性（permanence）猜想：速率固定为正时，每个正化学计量相容类——哪怕本身无界——都拥有一个公共的紧凸前向不变吸收集，类内所有正轨迹最终共享同一组正的下界与有限的上界。

## 问题背景

化学反应网络由有限个络合物（complex，即非负整数格点）与其间的有向反应组成；若每条反应都存在有向返回路径，则称网络弱可逆（weakly reversible）。在质量作用动力学（mass-action kinetics）下，反应速率正比于反应物浓度的幂，给出一个多项式向量场，正轨迹被锁定在化学计量相容类（stoichiometric compatibility class）内，而该类可以无界。自 Horn–Jackson 与 Feinberg（1972）奠基以来，核心问题是：仅凭弱可逆这一图论条件，能否排除物种浓度趋零（灭绝）或爆炸？Feinberg（1987）明确提出持久性（persistence）问题，Anderson（2011）将其拆解为有界性与持久性两个猜想。已有结果均带限制：单连通类（Anderson 2011；Gopalkrishnan–Miller–Shiu 2014；Boros–Hofbauer 2020）、两物种（Craciun–Nazarov–Pantea 2013）、二维化学计量空间（Pantea 2012），或需预设轨迹有界（Craciun 2026 的环面微分包含方法）。而"类持久性"比逐条轨迹的持久性更强：同一类中所有轨迹须共享同一组界与一个公共吸收集——这正是本文补齐的最后一块拼图。

## 主要结果

主定理（introduction.tex 定理 1.1）：设有限络合物集 \(C\subset\Z_{\geq0}^d\)，反应集 \(R\) 弱可逆，速率常数 \(k_{y\to y'}\) 固定为正。则对每个正相容类 \(P=(c+S)\cap\R_{>0}^d\)（\(S\) 为化学计量子空间），存在非空紧凸集 \(K_P\subset P\)，满足三条：每个初值 \(x^0\in P\) 的解唯一、整体存在且恒正；存在有限时间 \(T(x^0)\)，使 \(x(t)\in K_P\) 对一切 \(t\geq T(x^0)\) 成立；\(K_P\) 前向不变（forward invariant）。特别地，存在 \(\eps_P\in(0,1)\) 使类内每条解在进入时间之后满足 \(\eps_P\leq x_i(t)\leq\eps_P^{-1}\)（对所有坐标）。一致性是"逐类"的：\(K_P\) 与 \(\eps_P\) 只依赖网络、速率与类 \(P\)，不依赖初值；进入时间允许依赖初值。即使 \(P\) 无界，结论依然成立。

## 证明思路

证明分四步：仿射逼近、平台构造、切割通量估计、尺度迭代。

先做仿射逼近（第 2 节）。把盒子 \(B_h=[h,h^{-1}]^d\) 中的点写成对数坐标 \(x=X_h(p)=(h^{p_1},\dots,h^{p_d})\)。核心工具是姊妹篇的仿射逼近引理（引理 2.1，本文完整复现其证明）：存在有限仿射族 \(F_h(x)=\min_\lambda(r_\lambda\cdot x+b_\lambda(h))\)，斜率与 \(h\) 无关，且在 \(x\) 处取到最小值的活跃标签（active label）满足 \(\norm{p-r_\lambda}_\infty<E(r_\lambda)\)——容差 \(E\) 可以是任意正函数，允许不连续。这一自由度至关重要：可令 \(E\) 在比较超平面 \(r\cdot v=0\) 附近收缩，而超平面上不设限。取比较方向集 \(D\) 为坐标向量与全部络合物之差，选 \(E\) 使非零斜率比较与指数比较同号，再由斜率族有限得到一致符号间隙 \(H>0\)，即低层络合物的单项式（monomial）压制高层：\(x^z\leq h^H x^y\)。

再构造平台（第 3 节）。固定类代表元 \(c\)，取尺度 \(h\) 使 \(c\) 的对数坐标范数小于 \(H\)，则 \(c\) 处活跃标签的斜率必为零，\(F_h(c)=M_h\) 成为全局最大值，其平台 \(K_h=\{F_h=M_h\}\) 是含 \(c\) 的紧凸集，且嵌入更小的盒子：\(K_h\subset\operatorname{int}B_{\sqrt h}\)。关键的严格性来自类结构：斜率落在 \(S^\perp\) 的仿射函数在 \(c+S\) 上恒为常数、值不小于 \(M_h\)，故不可能在 \(P\setminus K_h\) 处活跃——平台之外的一切活跃斜率都横截于 \(S\)。

接着做切割通量估计。对活跃斜率 \(r\)，将络合物按水平 \(r\cdot y\) 排序并逐层切割。若有反应向下穿割，弱可逆性在其返回路径上给出一条向上穿越；由单项式压制，单条向上通量即压过全部向下通量之和，故每个切割的净向上通量非负、有穿越时严格为正。按切割分解求和得 \(r\cdot f(x)\geq0\)，且当 \(r\notin S^\perp\) 时严格为正；固定尺度上的紧性将严格性一致化为固定速度 \(\delta_h>0\)。于是 \(F_h\) 沿盒内解段单调不降，并在 \(B_h\cap(P\setminus K_h)\) 上以固定速率上升——留在盒内的轨迹必在有限时间进入 \(K_h\) 并被锁住。

最后迭代尺度（第 4 节）。先取 \(h_0\) 使 \(x^0\in K_{h_0}\)，得到整体存在性；再利用 \(K_{h_j}\subset\operatorname{int}B_{\sqrt{h_j}}\subset B_{h_{j+1}}\)，令 \(h_{j+1}=\min\{\sqrt{h_j},h_P\}\) 逐级推进：上一尺度的紧集保证轨迹留在下一尺度的盒内，有限进入引理再把轨迹送进下一尺度的平台。反复开平方使 \(h\) 趋于 1，故有限步后到达由类预先选定的 \(h_P\)。取 \(K_P=K_{h_P}\cap(c+S)\)：它紧凸、前向不变、吸收类内一切正轨迹，且不依赖初值。

## 可信度与备注

本文与姊妹篇（2026 年 9 月 25 日手稿，文中引作 [OpenAI2026]）构成递进关系：姊妹篇证明了逐轨迹的有界性与持久性（界依赖初值），本文完整复现其仿射引理并改造其陷阱构造，新增"平台外严格上升"与"跨尺度衔接"两个论证，把个体界升级为逐类一致的持久性；两文共享同一套"水平切割 + 返回路径通量占优"机制，互为印证。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文主结果暂无 Lean 形式化证明，请以社区核验为准。

{% endraw %}
