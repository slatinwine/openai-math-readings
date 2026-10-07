---
layout: default
title: "Strict convexity and differentiability of the planar exponential first-passage limit shape"
family: "212"
discipline: "Probability and statistical mechanics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Strict convexity and differentiability of the planar exponential first-passage limit shape

> 结果族 212：Planar first-passage geometry and the absence of bigeodesics　·　学科：Probability and statistical mechanics　·　验证状态：主结果已 Lean 形式化

## 一句话结论
证明了 \(\Z^2\) 上独立指数边权首达渗流的极限形状严格凸且边界为 \(C^1\) 曲线，并把可微性推广到一切形状、速率均为正的 Gamma 边权，解决平面指数模型的严格凸性与可微性两大猜想。

## 问题背景
首达渗流中，形状定理（shape theorem）断言通行时间满足 \(T(0,\lfloor tv\rfloor)/t\to\mu(v)\)，极限是确定性范数 \(\mu\)，其单位球 \(\mathcal B\) 称为极限形状（limit shape）。但这个凸体的精细几何极难确定：凸边界可能有平边（flat face，一条支撑线上含多个点）或角点（corner，一点处支撑线不唯一），分别破坏严格凸性与可微性。此前只有局部结果：Lalley 给出充分条件；Durrett–Liggett 在 Richardson 模型中证明近临界参数时确有平边；Marchand 与 Auffinger–Damron 处理的是最小值处带原子的分布，而指数分布无原子且支撑下确界为零，旧方法全部失效。严格凸性与可微性猜想因此在平面指数模型上长期悬置。

## 主要结果
定理一：边权为任意速率 \(\lambda>0\) 的指数分布时，\(\mu\) 在 \(\R^2\setminus\{0\}\) 上 Fréchet 可微（Fréchet differentiable），单位球严格凸（strictly convex）——边界上相异两点 \(x,y\) 与 \(0<t<1\) 恒有 \(\mu((1-t)x+ty)<1\)——且 \(\partial\mathcal B\) 是 \(C^1\) 曲线，每点有唯一支撑线。定理二：对任意形状 \(\kappa>0\)、速率 \(\lambda>0\) 的 Gamma 边权，\(\mu\) 在每个非零向量处 Fréchet 可微，\(\partial\mathcal B\) 为 \(C^1\) 曲线。推论包括：固定方向 \(u\) 下每个顶点恰有一条方向 \(u\) 的无穷测地线、有限测地线局部收敛、不同起点的测地线聚合、无以 \(u\) 为端方向的双无穷测地线，且 Busemann 极限满足 \(\E B_u(0,x)=\nabla\mu(u)\cdot x\)；此外还给出 Benjamini–Kalai–Schramm 中点问题 \(\PP(\lfloor n/2\rfloor v\in\Gamma(0,nv))\to0\)、Gamma 族的量化中点估计及 Richardson 锥尖竞争的临界半角 \(\pi/2\)。

## 证明思路
排除角点（可微性）的骨架是"缺口即罚金"。取方向 \(u=(1,b)\)，凸函数 \(t\mapsto\mu(u+te_2)\) 在零处有左右导数 \(a_-\le a_+\)，对应两个极端支撑泛函 \(f_\pm\) 及其平均 \(f\)；若角点存在，缺口 \(c=(a_+-a_-)/2>0\)，而路径缺陷满足 \(\min\{H_+,H_-\}=H-c|r(\Delta P)|\)，横向位移招致线性罚金。先证窄条穿越估计：限制在长窄条内的路径不可能比极端支撑省下条宽的固定倍数，否则用独立平行试验、再拼接与范数一阶接触的短路径，会得到低于该支撑的大尺度通行时间。其次用有限区域换测度（change of measure）对每个宽度 \(s\) 造特征长度 \(L\)，满足 \(L/s\to\infty\) 且 \(L\le s^3\)，经嵌套网格把估计延拓到任意端点且误差可求和。最后，每段便宜路径都含有一个稀疏下降事件的见证（witness），用 van den Berg–Kesten 不等式（BK inequality）处理对同一粗格子的重复访问，得到对所有长简单路径的一致下界，与形状定理沿 \(u\) 的渐近矛盾。Gamma 推广内嵌于证明：把单条 Gamma 权乘以 \(1-\delta\)，似然二阶矩恰为 \((1-\delta^2)^{-\kappa}\)；取 \(\delta\) 约 \(s/n\)、缩放 \(O(ns)\) 条边、\(n=s^3\) 时二阶矩一致有界。

排除平边（严格凸性）只用指数律。假设存在平边，Damron–Hanson 的平稳上闭链（cocycle）给出可加随机函数 \(B(x,y)\)，均值为该支撑泛函且 \(|B(x,y)|\le T(x,y)\)，故任意前向子路径的缺陷非负。构造沿平边两端方向行进的局部随机路径"道路"（roads），令 \(b(n)\) 为尺度 \(n\) 下每周期平均缺陷公共上界的下确界。一方面，局部扰动给出下界 \(b(n)\ge c_0>0\)；另一方面，通过有限胞腔投影近似非局部上闭链的增量、物理路由论证控制局部捷径的总节省、保面积形变控制集中于极端方向附近的路径，并借助 Damron–Hanson–Sosoe 与 Damron–Kubota 的集中估计，得到固定整数 \(D\) 与 \(\rho<1\) 使 \(b(Dn)\le\rho b(n)\)。迭代产生 \(c_0\le\rho^k b(n_0)\to0\) 的矛盾，故支撑面退化为单点，即严格凸。速率 \(\lambda\) 经耦合 \(\tau_e^{(\lambda)}=\lambda^{-1}\tau_e^{(1)}\) 归一到 \(\lambda=1\)。

## 可信度与备注
本文主结果已 Lean 形式化。姊妹篇（无测地线一文）证明在四权最小值二阶矩条件下双无穷测地线几乎必然不存在，覆盖全部 Gamma 律；本文则供给形状正则性，把方向固定的测地线结构收缩为单一方向并给出相应 Busemann 极限，两篇互补地刻画了平面首达度量的几何。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文关键结论已有形式化佐证，相对更可靠。

{% endraw %}
