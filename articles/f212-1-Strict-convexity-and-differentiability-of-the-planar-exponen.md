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

## 入门导读 🐣

在随机拥堵的路网里跑久了，司机会发现每个方向都有一个确定的"有效速度"。把各方向单位时间能到达的边界点连起来，就得到极限形状。这篇论文证明：当边权服从指数分布时，这条闭曲线既没有一段直边，也没有一个尖角——它像一个略歪的鸡蛋，而不是一枚方形印章。

**关键词卡片**

- 极限形状（limit shape）：长时间运行后可达区域收敛到的确定性凸体。
- 平边（flat face）：边界上共线的一段支撑线，定理证明它不存在。
- 角点（corner）：边界上切线不唯一的尖角，同样被排除。
- Fréchet 可微（Fréchet differentiable）："有效速度"函数处处光滑的严格说法。
- 指数边权（exponential edge weights）：通行时间服从指数分布，无原子且支撑下确界为 0，使旧方法全部失效。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="35" font-size="14" text-anchor="middle" fill="#222">指数边权下 ℤ² 首达渗流的极限形状</text>
  <path d="M 85 95 L 225 95 L 262 150 L 225 205 L 85 205 Z" fill="#f5f5f5" stroke="#333" stroke-width="2"/>
  <line x1="55" y1="95" x2="250" y2="95" stroke="#c0392b" stroke-width="1.5" stroke-dasharray="6 5"/>
  <circle cx="262" cy="150" r="4" fill="#c0392b"/>
  <text x="272" y="154" font-size="12" fill="#c0392b">角点</text>
  <text x="155" y="78" font-size="12" text-anchor="middle" fill="#c0392b">平边：整段支撑线都在边界上</text>
  <ellipse cx="440" cy="155" rx="90" ry="70" fill="#eaf3ea" stroke="#2c7a4b" stroke-width="2"/>
  <line x1="370" y1="85" x2="510" y2="85" stroke="#2c7a4b" stroke-width="1.5" stroke-dasharray="6 5"/>
  <circle cx="440" cy="85" r="3.5" fill="#2c7a4b"/>
  <text x="440" y="66" font-size="12" text-anchor="middle" fill="#2c7a4b">每点恰有一条切线</text>
  <text x="170" y="245" font-size="13" text-anchor="middle" fill="#333">不允许：有平边或角点</text>
  <text x="440" y="245" font-size="13" text-anchor="middle" fill="#2c7a4b">定理：严格凸且处处光滑</text>
</svg>

</div>

把定理写成"数字版"：对极限形状边界上任意两个不同点 x、y 与 0<t<1，都有 `@@M@@\mu((1-t)x+ty)<1@@`。比如取 `@@M@@t=\tfrac12@@`：`@@M@@\mu\big(\tfrac{x+y}{2}\big)<1@@`，中点被严格压回形状内部——边界上找不到任何一小段直线。此前的方法依赖分布最小值处带原子，而指数分布恰好无原子、支撑下确界又是 0，本文只能另起炉灶。

**为什么值得关心**

它解决了平面指数模型悬置多年的严格凸性与可微性两大猜想，说明"每个方向的最快路线"行为规矩，为理解随机度量几何立下标杆；固定方向下的测地线还有恰一条、必聚合等配套结论。

> 已 Lean 形式化

# 过渡 | Strict convexity and differentiability of the planar exponential first-passage limit shape

## 由浅入深：从类比走向定理

**第一级台阶**

导读把极限形状比作"略歪的鸡蛋，而不是方形印章"。翻译过来：对象是长时间运行后可达区域收敛到的那条确定性的闭曲线；要做的操作是逐点检查它的"直"与"尖"——鸡蛋不允许边界上出现一小段直线（平边），也不允许出现切线不唯一的尖角（角点）。

**第二级台阶**

用本科凸几何的语言精确化。形状定理说通行时间满足 `@@M@@T(0,\lfloor tv\rfloor)/t\to\mu(v)@@`，极限 `@@M@@\mu@@` 是一个范数，其单位球 `@@M@@\mathcal B@@` 就是极限形状。平边指某条支撑直线与 `@@M@@\partial\mathcal B@@` 交出一条线段；角点指某点处支撑直线不唯一。严格凸即边界上相异两点 `@@M@@x,y@@` 与 `@@M@@0<t<1@@` 恒有 `@@M@@\mu((1-t)x+ty)<1@@`；Fréchet 可微则要求 `@@M@@\mu@@` 在每个非零向量处有唯一的线性一阶近似。

**第三级台阶**

定理的语境：边权独立、服从速率 `@@M@@\lambda>0@@` 的指数分布。结论是 `@@M@@\mu@@` 在 `@@M@@\mathbb{R}^2\setminus\{0\}@@` 上 Fréchet 可微、`@@M@@\mathcal B@@` 严格凸、`@@M@@\partial\mathcal B@@` 是 `@@M@@C^1@@` 曲线；且可微性推广到一切形状与速率均为正的 Gamma 律。假设"指数（或 Gamma）律"挡住的麻烦是：旧方法全靠分布最小值处带原子，而指数律无原子、支撑下确界为零，必须另起炉灶。结论用凸几何的话说：每个方向的有效速度光滑地变化，支撑线逐点唯一——既无平边也无角点。

## 一句话结论
证明了 `@@M@@\mathbb{Z}^2@@` 上独立指数边权首达渗流的极限形状严格凸且边界为 `@@M@@C^1@@` 曲线，并把可微性推广到一切形状、速率均为正的 Gamma 边权，解决平面指数模型的严格凸性与可微性两大猜想。

## 问题背景
首达渗流中，形状定理（shape theorem）断言通行时间满足 `@@M@@T(0,\lfloor tv\rfloor)/t\to\mu(v)@@`，极限是确定性范数 `@@M@@\mu@@`，其单位球 `@@M@@\mathcal B@@` 称为极限形状（limit shape）。但这个凸体的精细几何极难确定：凸边界可能有平边（flat face，一条支撑线上含多个点）或角点（corner，一点处支撑线不唯一），分别破坏严格凸性与可微性。此前只有局部结果：Lalley 给出充分条件；Durrett–Liggett 在 Richardson 模型中证明近临界参数时确有平边；Marchand 与 Auffinger–Damron 处理的是最小值处带原子的分布，而指数分布无原子且支撑下确界为零，旧方法全部失效。严格凸性与可微性猜想因此在平面指数模型上长期悬置。

## 主要结果
定理一：边权为任意速率 `@@M@@\lambda>0@@` 的指数分布时，`@@M@@\mu@@` 在 `@@M@@\mathbb{R}^2\setminus\{0\}@@` 上 Fréchet 可微（Fréchet differentiable），单位球严格凸（strictly convex）——边界上相异两点 `@@M@@x,y@@` 与 `@@M@@0<t<1@@` 恒有 `@@M@@\mu((1-t)x+ty)<1@@`——且 `@@M@@\partial\mathcal B@@` 是 `@@M@@C^1@@` 曲线，每点有唯一支撑线。定理二：对任意形状 `@@M@@\kappa>0@@`、速率 `@@M@@\lambda>0@@` 的 Gamma 边权，`@@M@@\mu@@` 在每个非零向量处 Fréchet 可微，`@@M@@\partial\mathcal B@@` 为 `@@M@@C^1@@` 曲线。推论包括：固定方向 `@@M@@u@@` 下每个顶点恰有一条方向 `@@M@@u@@` 的无穷测地线、有限测地线局部收敛、不同起点的测地线聚合、无以 `@@M@@u@@` 为端方向的双无穷测地线，且 Busemann 极限满足 `@@M@@\E B_u(0,x)=\nabla\mu(u)\cdot x@@`；此外还给出 Benjamini–Kalai–Schramm 中点问题 `@@M@@\PP(\lfloor n/2\rfloor v\in\Gamma(0,nv))\to0@@`、Gamma 族的量化中点估计及 Richardson 锥尖竞争的临界半角 `@@M@@\pi/2@@`。

## 证明思路
排除角点（可微性）的骨架是"缺口即罚金"。取方向 `@@M@@u=(1,b)@@`，凸函数 `@@M@@t\mapsto\mu(u+te_2)@@` 在零处有左右导数 `@@M@@a_-\le a_+@@`，对应两个极端支撑泛函 `@@M@@f_\pm@@` 及其平均 `@@M@@f@@`；若角点存在，缺口 `@@M@@c=(a_+-a_-)/2>0@@`，而路径缺陷满足 `@@M@@\min\{H_+,H_-\}=H-c|r(\Delta P)|@@`，横向位移招致线性罚金。先证窄条穿越估计：限制在长窄条内的路径不可能比极端支撑省下条宽的固定倍数，否则用独立平行试验、再拼接与范数一阶接触的短路径，会得到低于该支撑的大尺度通行时间。其次用有限区域换测度（change of measure）对每个宽度 `@@M@@s@@` 造特征长度 `@@M@@L@@`，满足 `@@M@@L/s\to\infty@@` 且 `@@M@@L\le s^3@@`，经嵌套网格把估计延拓到任意端点且误差可求和。最后，每段便宜路径都含有一个稀疏下降事件的见证（witness），用 van den Berg–Kesten 不等式（BK inequality）处理对同一粗格子的重复访问，得到对所有长简单路径的一致下界，与形状定理沿 `@@M@@u@@` 的渐近矛盾。Gamma 推广内嵌于证明：把单条 Gamma 权乘以 `@@M@@1-\delta@@`，似然二阶矩恰为 `@@M@@(1-\delta^2)^{-\kappa}@@`；取 `@@M@@\delta@@` 约 `@@M@@s/n@@`、缩放 `@@M@@O(ns)@@` 条边、`@@M@@n=s^3@@` 时二阶矩一致有界。

排除平边（严格凸性）只用指数律。假设存在平边，Damron–Hanson 的平稳上闭链（cocycle）给出可加随机函数 `@@M@@B(x,y)@@`，均值为该支撑泛函且 `@@M@@|B(x,y)|\le T(x,y)@@`，故任意前向子路径的缺陷非负。构造沿平边两端方向行进的局部随机路径"道路"（roads），令 `@@M@@b(n)@@` 为尺度 `@@M@@n@@` 下每周期平均缺陷公共上界的下确界。一方面，局部扰动给出下界 `@@M@@b(n)\ge c_0>0@@`；另一方面，通过有限胞腔投影近似非局部上闭链的增量、物理路由论证控制局部捷径的总节省、保面积形变控制集中于极端方向附近的路径，并借助 Damron–Hanson–Sosoe 与 Damron–Kubota 的集中估计，得到固定整数 `@@M@@D@@` 与 `@@M@@\rho<1@@` 使 `@@M@@b(Dn)\le\rho b(n)@@`。迭代产生 `@@M@@c_0\le\rho^k b(n_0)\to0@@` 的矛盾，故支撑面退化为单点，即严格凸。速率 `@@M@@\lambda@@` 经耦合 `@@M@@\tau_e^{(\lambda)}=\lambda^{-1}\tau_e^{(1)}@@` 归一到 `@@M@@\lambda=1@@`。

## 可信度与备注
本文主结果已 Lean 形式化。姊妹篇（无测地线一文）证明在四权最小值二阶矩条件下双无穷测地线几乎必然不存在，覆盖全部 Gamma 律；本文则供给形状正则性，把方向固定的测地线结构收缩为单一方向并给出相应 Busemann 极限，两篇互补地刻画了平面首达度量的几何。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文关键结论已有形式化佐证，相对更可靠。

---

# 深挖 | Strict convexity and differentiability of the planar exponential first-passage limit shape

## 深入探讨：像审稿人一样追问 🔍

**问 1：可微性证明里最关键、最脆弱的一步是哪里？**

答：骨架是"缺口即罚金"：角点对应缺口 `@@M@@c=(a_+-a_-)/2>0@@`，横向位移招致线性罚金 `@@M@@H-c|r(\Delta P)|@@`。收尾一步最重：每段便宜路径含稀疏下降事件的见证，用 van den Berg–Kesten 不等式处理对同一粗格子的重复访问，得到对所有长简单路径的一致下界，再与沿 `@@M@@u@@` 的形状定理渐近矛盾。BK 不等式的"不交事件"使用与嵌套网格延拓中误差可求和的验证，是最可能出细节漏洞的地方。

**问 2：为什么假设"指数/Gamma 律"不能换成一般连续分布？**

答：换测度论证依赖显式计算：Gamma 律下似然二阶矩恰为 `@@M@@(1-\delta^2)^{-\kappa}@@`，取 `@@M@@\delta\approx s/n@@`、缩放 `@@M@@O(ns)@@` 条边、`@@M@@n=s^3@@` 时一致有界；一般分布没有这样的闭式。论文对一般无原子律未展开讨论。

**问 3：与已有工作相比真正的新意是什么？**

答：此前只有局部结果：Lalley 给充分条件，Durrett–Liggett 证明 Richardson 近临界确有平边，Marchand 与 Auffinger–Damron 处理最小值处带原子的分布。本文彻底解决指数模型的严格凸与可微两大猜想并推广到 Gamma 族，还附赠配套结论：每方向恰一条无穷测地线、测地线聚合、`@@M@@\E B_u(0,x)=\nabla\mu(u)\cdot x@@`、BKS 中点问题及 Richardson 锥尖竞争临界半角 `@@M@@\pi/2@@`。

**问 4：这类证明最可能出错的模式是什么？**

答：严格凸部分把 Damron–Hanson 平稳上闭链、Damron–Hanson–Sosoe 与 Damron–Kubota 集中估计等多件重器拼进一个迭代 `@@M@@b(Dn)\le\rho b(n)@@`，确定性重整化记账里常数若不慎依赖尺度即告失效。缓解因素是本文主结果已 Lean 形式化，但外部集中估计是否全在形式化范围内，论文未展开说明。

**问 5：从"无角点"到"`@@M@@C^1@@` 边界"之间的桥是什么？**

答：一条凸边界正则性引理：范数在非零向量处 Fréchet 可微 `@@M@@\iff@@` 单位球每点支撑线唯一 `@@M@@\iff@@` 单位球是正则 `@@M@@C^1@@` 曲线。正向用齐次性 `@@M@@D\mu(u)[u]=\mu(u)=1@@` 保证梯度非零，隐函数定理把水平集 `@@M@@\mu=1@@` 变成 `@@M@@C^1@@` 曲线。

**问 6：为什么严格凸性只对指数律、可微性却能到 Gamma？**

答：排除平边的"道路"构造与局部扰动下界 `@@M@@b(n)\ge c_0@@` 只在指数律下成立；可微性证明里 Gamma 推广是内嵌的（似然矩计算），平边部分则未推广，论文未展开 Gamma 严格凸性。

**总评**

这是平面指数模型两大概想的完全解决，且有 Lean 形式化背书，分量很高；残余风险集中在严格凸部分对外部集中估计的依赖与组合记账细节。

{% endraw %}
