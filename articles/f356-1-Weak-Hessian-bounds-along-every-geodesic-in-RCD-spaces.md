---
layout: default
title: "Weak Hessian bounds along every geodesic in RCD spaces"
family: "356"
discipline: "Differential geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Weak Hessian bounds along every geodesic in RCD spaces

> 结果族 356：Gigli's characterization of Alexandrov curvature　·　学科：Differential geometry　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

看一张起伏地形图："任何地方的坡面弯曲都不超过上限"这句话，如果只是对全图平均意义成立，能否推出"沿任意指定直路走，坡的二阶变化也不超上限"？在光滑世界这是废话；在处处毛刺的非光滑空间里，这篇论文证明它依然成立——哪怕那条路整个掉进"零测度沟"里。

**关键词卡片**

- RCD 空间（RCD(K,N) space）：综合表达"Ricci 曲率 `@@M@@\ge K@@`、维数 `@@M@@\le N@@`"的非光滑度量空间。
- Hessian：函数的二阶导，刻画山坡"弯"得多厉害。
- 分布意义（distributional）：不求逐点导数，改用"对每个测试函数积分"定义的弱概念。
- 测地线（geodesic）：局部最短的路线。
- 满支撑（full support）：参考测度在任何开集上都取正值。

**看个具体例子**

困难在于：弱不等式只对参考测度检验，而一条测地线可能整条躺在零测集上，"几乎处处"对它毫无约束。定理完成提升，取常数上界 `@@M@@G\equiv c@@` 的特例：沿每条长 `@@M@@\ell@@` 的测地线 `@@M@@\sigma@@`，

`@@M@@D\varphi(t):=F(\sigma_t)-\tfrac{c\ell^{2}}{2}\,t^{2}\quad\Longrightarrow\quad\varphi''\le 0,@@`

即 `@@M@@\varphi@@` 是凹函数。代入 `@@M@@c=1@@`、`@@M@@\ell=2@@`：`@@M@@F(\sigma_t)-2t^{2}@@` 在 `@@M@@t\in[0,1]@@` 上凹——"平均说的上限"真的管住了"每一条路"。

**为什么值得关心**

把"几乎处处"升级为"每条测地线"，正是从分布分析通往几何比较定理的必经桥梁；它是姊妹篇解决 Gigli 刻画猜想的最后一块踏脚石。

> 已 Lean 形式化

## 一句话结论

在满支撑 `@@M@@\mathrm{RCD}(K,N)@@`（`@@M@@1<N<\infty@@`）空间上证明：有界全局 Lipschitz 函数的分布 Hessian 若被有界连续函数 `@@M@@G@@` 控制，则沿每条最短测地线 `@@M@@\sigma@@` 成立 `@@M@@(F\circ\sigma)''\le\ell^2G\circ\sigma@@`，把"对参考测度成立"的弱不等式提升为"对每条测地线成立"的逐条结论。

## 问题背景

光滑黎曼流形上，函数 Hessian（海瑟矩阵）的上界自动限制它沿每条测地线的二阶导数；但在 `@@M@@\mathrm{RCD}@@` 空间上，弱 Hessian 不等式是拿参考测度 `@@M@@m@@` 检验的分布陈述，而一条指定测地线可能整个落在 `@@M@@m@@`-零测集中，几乎处处成立的结论对它毫无约束。Brena–Gigli 提出用换测度配合弱 Bochner 不等式的路线，并指出必须补足正则性才能合法取极限；Ketterer、Sturm 与 Han 的大参数熵极限方法则都要求函数额外的二阶 Sobolev 正则性。本文在纯分布假设、且上界函数 `@@M@@G@@` 随空间变化的情形下完成这一提升，适用于包括坍缩（collapsed）空间在内的一切满支撑 `@@M@@\mathrm{RCD}(K,N)@@` 空间。这一"每条测地线"的结论是从分布分析通向几何比较的必经桥梁：把 Hessian 上界转化为距离函数沿测地线的微分不等式，恰恰需要逐条测地线的陈述。

## 主要结果

定理：设 `@@M@@(M,d,m)@@` 为满支撑 `@@M@@\mathrm{RCD}(K,N)@@` 空间，`@@M@@K\in\mathbb R@@`、`@@M@@1<N<\infty@@`；`@@M@@F@@` 有界且全局 Lipschitz，`@@M@@G@@` 有界连续。若对每个紧支撑的 `@@M@@g\in\Test(M)@@` 与非负 `@@M@@h\in\Lip_c(M)@@` 都有
`@@M@@DH_F(\nabla g,\nabla g)(h)\ \le\ \int_M h\,G\,\Gamma(g)\dd m,@@`
其中弱 Hessian 值由分部积分定义、只用到 `@@M@@F@@` 的一阶导数，试验类（test class）`@@M@@\Test(M)@@` 由有界全局 Lipschitz 且 `@@M@@\Delta g\in W^{1,2}(M)@@` 的 `@@M@@g\in D(\Delta)@@` 组成，则每条长为 `@@M@@\ell@@` 的常速最短测地线 `@@M@@\sigma\colon[0,1]\to M@@` 满足 `@@M@@(F\circ\sigma)''\le\ell^2G\circ\sigma@@`（分布意义）。特例 `@@M@@G\equiv c@@`：`@@M@@t\mapsto F(\sigma_t)-c\ell^2t^2/2@@` 是凹函数。`@@M@@F@@` 无需属于 `@@M@@L^2(m)@@`，`@@M@@m@@` 也允许有无限总质量。

## 证明思路

证明分两阶段。第一阶段换测度：固定 `@@M@@\lambda>0@@`，令 `@@M@@m_\lambda=e^{\lambda F}m@@`。主要障碍是正则性——Lipschitz 位势 `@@M@@V@@` 虽保持生成元域与漂移公式 `@@M@@\Delta_Vu=\Delta u+\Gamma(V,u)@@`，但 `@@M@@\Gamma(V,u)@@` 未必 Sobolev，原始试验类在换测度后不再封闭。作者的绕法是对原热半群用预解式（resolvent）`@@M@@R_a=(a-\Delta)^{-1}@@`：谱演算与热梯度估计给出从 `@@M@@L^2\cap L^\infty@@` 到 `@@M@@W^{1,2}\cap L^\infty@@` 的压缩性，从而映射 `@@M@@z\mapsto R_a(h+\Gamma(V,z))@@` 在 `@@M@@\{z:z,|\nabla z|\in L^\infty\}@@` 上有不动点，证得"有界且加权 Laplacian 有界 `@@M@@\Rightarrow@@` Lipschitz"这一乘子正则性。有了它，先在共同生成元图像域中封闭加权 Bochner 不等式——核心恒等式 `@@M@@\mathcal B_V(g,\xi)-\mathcal B_0(g,w\xi)=-H_V(\nabla g,\nabla g)(w\xi)@@` 把弱 Hessian 假设精确转化为曲率下降 `@@M@@K-\lambda G@@`——再援引 Braun–Habermann–Sturm 的变曲率（variable curvature）等价，得到 `@@M@@m_\lambda@@` 满足 `@@M@@\CD(K-\lambda G,\infty)@@`。第二阶段把熵不等式定位到指定测地线：固定 `@@M@@\sigma@@` 的一个严格内部子段，有限维 `@@M@@\mathrm{RCD}@@` 空间非分叉（nonbranching，Deng 定理）使该子段成为其端点间唯一的最短测地线；用缩小球上归一化的测度逼近端点，则所有传输路径被迫收敛于该子段。熵恒等式 `@@M@@\Ent_{m_\lambda}(\mu)=\Ent_m(\mu)-\lambda\int F\dd\mu@@` 把 `@@M@@\CD@@` 不等式改写为 `@@M@@F@@` 沿插值测度不低于端点弦、带 Green 核（Green kernel）修正的下界；取 `@@M@@\lambda_j@@` 远大于端点熵以消去剩余熵项，取极限并对一切严格子区间应用，令 `@@M@@a''=\ell^2G\circ\sigma@@`，Green 公式表明 `@@M@@F\circ\sigma-a@@` 位于其每条弦之上、即为凹函数，其分布二阶导数非正，定理得证。

## 可信度与备注

按任务信息，本文主结果已有 Lean 形式化证明。它是族 356 姊妹篇《Gigli's distributional curvature characterization of Alexandrov spaces》反向论证最后一步的核心输入：修改距离函数加上本定理即得模型微分不等式、进而三角形比较与 Alexandrov 刻画；本篇证明只用一般满支撑 `@@M@@\mathrm{RCD}(K,N)@@` 假设，与那篇的非坍缩和截面曲率结构无关，两篇结论彼此独立又互相支撑。族内旗舰篇尚未形式化，按 OpenAI 官方声明，未经形式化的结果可能有问题，整族引用时请以社区核验为准。

{% endraw %}
