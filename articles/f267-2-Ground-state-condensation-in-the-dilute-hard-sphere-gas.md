---
layout: default
title: "Ground-state condensation in the dilute hard-sphere gas"
family: "267"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Ground-state condensation in the dilute hard-sphere gas

> 结果族 267：Positive-temperature Bose–Einstein condensation and exact quantum depletion　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对三维硬球（hard sphere）玻色气体，在固定排斥距离 `@@M@@a@@` 与固定密度 `@@M@@\rho@@`（气体参数 `@@M@@\rho a^3@@` 足够小）下取热力学极限，论文证明每一个基态——允许复值波函数、允许基态空间简并——的常数轨道凝聚分数都不低于绝对常数 `@@M@@c_0>0@@`。这回答了 Solovej 2025 年综述列为主要公开问题的固定密度基态凝聚。

## 问题背景

Bogoliubov（1947）的弱相互作用玻色气体理论以零模被宏观占据为前提；Lee–Huang–Yang（1957）进而预测硬球气的量子耗尽（depletion）分数为 `@@M@@\sqrt{\rho a^3}@@` 量级。能量侧的理论已相当完善：从 Dyson（1957）、Lieb–Yngvason（1998）到 Fournais–Solovej 的 Lee–Huang–Yang 下界与 Basti 等人的匹配上界。但能量渐近不决定单体轨道占据——单体谱隙随体积消失，Lieb–Yngvason 当年就明确把占据问题与能量定理分开。已有的占据结果要么在 Gross–Pitaevskii 标度下（Lieb–Seiringer 2002；Deuchert–Seiringer 2020），要么让稀薄程度与体积联合变化（Fournais 2021；Chong–Liang–Nam 2026；Junge 2026）；Sütő 的热力学极限定理需要 Fourier 变换非负等条件，恰恰排除真正的硬核。Solovej 的 2025 年综述（第 5 节）把固定密度的基态凝聚列为主要公开问题，本文在稀薄区域给出了肯定回答。

## 主要结果

硬球哈密顿量由允许位形集 `@@M@@\Omega_{N,L,a}=\{d_L(x_i,x_j)>a,\ i<j\}@@` 上的 Dirichlet 型 `@@M@@q_{N,L,a}[f]=\sum_i\int_{\Omega}|\nabla_i f|^2@@`（限制于置换对称函数）定义，波函数在禁位形处取零；`@@M@@a@@` 即散射长度（scattering length，外域零能散射解为 `@@M@@1-a/|x|@@`）。凝聚量度取 Penrose–Onsager 意义下的常数轨道占据

`@@M@@DB(\Psi)=\frac{\langle\varphi_{0,L},\Gamma^{(1)}_\Psi\varphi_{0,L}\rangle}{N}=\frac{1}{L^3}\int\Bigl|\int\Psi(x,Y)\,\dd x\Bigr|^2\dd Y.@@`

主定理：存在绝对常数 `@@M@@\varepsilon_0,c_0>0@@`，凡 `@@M@@\rho a^3<\varepsilon_0@@`，对任意满足 `@@M@@N_k\to\infty@@`、`@@M@@L_k\to\infty@@`、`@@M@@N_k/L_k^3\to\rho@@` 的序列及任意归一化玻色基态本征向量 `@@M@@\Psi_k@@`（可复值），有 `@@M@@\liminf_{k\to\infty}B(\Psi_k)\ge c_0@@`。同一 `@@M@@c_0@@` 对所有足够小的固定气体参数（gas parameter）通用；推论经凸性把结论推广到基态子空间上的任意混合态。论文只证正分数下界：不估计最优耗尽，也不证分数随 `@@M@@\rho a^3\to0@@` 趋于 1。

## 证明思路

先取模 `@@M@@\Phi=|\Psi|@@`：`@@M@@\Phi@@` 仍是基态函数，且在允许位形集的每个连通分支上 `@@M@@\Psi=e^{i\vartheta_C}\Phi@@`。证明先给 `@@M@@B(\Phi)@@` 一个一致下界，再用相位转移恢复 `@@M@@B(\Psi)@@`。第一步换长度单位，使每个单位胞平均含 `@@M@@D@@` 个粒子、排斥距 `@@M@@r=\alpha/D@@`（`@@M@@\alpha@@` 落在固定窗口），则气体参数 `@@M@@Dr^3=\rho a^3=\alpha^3/D^2@@`，"稀释"恰等价于 `@@M@@D@@` 变大。局部上，动能不等式与归一化的粒子插入估计表明"粒子过少或近邻过多"的胞联合概率很小；以 `@@M@@\Phi^2@@` 为位置边际的精确被杀布朗运动（killed Brownian motion）平稳律提供一批可整体替换的短轨迹。再把可动标号分成约与 `@@M@@D@@` 成正比的不交群，逐群冻结其余轨迹：胞"可用"当且仅当足够多剩余标号替换成功，未暴露部分的律是带个体截断、再以互相硬避让为条件的精确条件乘积律——归一化始终精确保留。远程上，对相距可比盒径的胞对，在保留的正概率环境中抽取随机格点路线：骨架（skeleton）律与两个相遇矩估计全部引自姊妹篇《A density-uniform condensate bound for dilute Bose gases》，是全文唯一外部输入；遇到不可用胞簇沿好的外壳绕行（Kesten 边界连通定理的 Timár 形式）。沿路线每个出发胞选一个标号并构造两份拷贝：第二份里每条选中轨迹的中点右移一胞；去掉第一份的初始标记与第二份的终端标记后，两份剩下完全相同的 `@@M@@N-1@@` 个中点"浴"（bath）。这一构造给出连接两个位置测度的公共有限测度，其平方根重叠（affinity，`@@M@@\mathsf H(P,Q)=\int\sqrt{pq}@@`）经精确恒等式 `@@M@@B(\Phi)=V^{-2}\sum_{v,w}\mathsf H(P_{vw},Q_{vw})@@` 直接进入占据。二阶矩的核心是"远离即抵消"引理：两条独立路线的似然乘积中，彼此远离部分的相互作用归一因子精确相消，代价只由相遇数与共享标号承担——相遇数为 `@@M@@J_R@@` 时代价如 `@@M@@(1-\chi_D)^{-4J_R}@@`；而两路线在同一公共胞选中同一标号的概率至多 `@@M@@2/M@@`，配合相遇数的退火指数矩界得到一致常数。每群亲和至少 `@@M@@1/(4C_2)@@`，群数与 `@@M@@D@@` 成正比恰好补偿单个标记的 `@@M@@1/D@@` 归一因子，最终 `@@M@@B(\Phi)\ge c_*=\upsilon_0\ell/(32MGC_{\rm path})@@`（`@@M@@\upsilon_0=1/2000@@`）。相位部分：用小闭立方体覆盖禁域球并填充连通簇的有界洞，剩余点经开的允许一粒子切片连通、故共享同一相位；小簇填弃体积小，大簇会迫使许多近邻粒子而被联合空间估计排除；弃去体积分数 `@@M@@\delta_{\rm geom}@@` 足够小时 `@@M@@B(\Psi)\ge B(\Phi)-4\sqrt{\delta_{\rm geom}}\ge c_*/2@@`。收尾取 `@@M@@K_k=\lfloor\sqrt{aN_k/(\alpha_0 L_k)}\rfloor@@` 换回原单位，使 `@@M@@\alpha_k\to\alpha_0@@`、`@@M@@D_k@@` 落入紧区间，完成任意热力学序列的论证。

## 可信度与备注

本文暂无形式化证明。它与族内《A density-uniform condensate bound for dilute Bose gases》构成姊妹篇：后者提供不含物理参数的骨架与相遇矩引擎，本文补上硬核能量估计、障碍适配、条件归一化计算与相位论证；两文共享"路径改测 + 二阶矩"的方法骨架，结论互相印证——一篇管软势正温，一篇管硬球基态。按 OpenAI 官方声明，未经形式化的结果可能存在问题，宜以社区核验为准。

{% endraw %}
