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

## 一句话结论

在满支撑 \(\mathrm{RCD}(K,N)\)（\(1<N<\infty\)）空间上证明：有界全局 Lipschitz 函数的分布 Hessian 若被有界连续函数 \(G\) 控制，则沿每条最短测地线 \(\sigma\) 成立 \((F\circ\sigma)''\le\ell^2G\circ\sigma\)，把"对参考测度成立"的弱不等式提升为"对每条测地线成立"的逐条结论。

## 问题背景

光滑黎曼流形上，函数 Hessian（海瑟矩阵）的上界自动限制它沿每条测地线的二阶导数；但在 \(\mathrm{RCD}\) 空间上，弱 Hessian 不等式是拿参考测度 \(m\) 检验的分布陈述，而一条指定测地线可能整个落在 \(m\)-零测集中，几乎处处成立的结论对它毫无约束。Brena–Gigli 提出用换测度配合弱 Bochner 不等式的路线，并指出必须补足正则性才能合法取极限；Ketterer、Sturm 与 Han 的大参数熵极限方法则都要求函数额外的二阶 Sobolev 正则性。本文在纯分布假设、且上界函数 \(G\) 随空间变化的情形下完成这一提升，适用于包括坍缩（collapsed）空间在内的一切满支撑 \(\mathrm{RCD}(K,N)\) 空间。这一"每条测地线"的结论是从分布分析通向几何比较的必经桥梁：把 Hessian 上界转化为距离函数沿测地线的微分不等式，恰恰需要逐条测地线的陈述。

## 主要结果

定理：设 \((M,d,m)\) 为满支撑 \(\mathrm{RCD}(K,N)\) 空间，\(K\in\mathbb R\)、\(1<N<\infty\)；\(F\) 有界且全局 Lipschitz，\(G\) 有界连续。若对每个紧支撑的 \(g\in\Test(M)\) 与非负 \(h\in\Lip_c(M)\) 都有
\[H_F(\nabla g,\nabla g)(h)\ \le\ \int_M h\,G\,\Gamma(g)\dd m,\]
其中弱 Hessian 值由分部积分定义、只用到 \(F\) 的一阶导数，试验类（test class）\(\Test(M)\) 由有界全局 Lipschitz 且 \(\Delta g\in W^{1,2}(M)\) 的 \(g\in D(\Delta)\) 组成，则每条长为 \(\ell\) 的常速最短测地线 \(\sigma\colon[0,1]\to M\) 满足 \((F\circ\sigma)''\le\ell^2G\circ\sigma\)（分布意义）。特例 \(G\equiv c\)：\(t\mapsto F(\sigma_t)-c\ell^2t^2/2\) 是凹函数。\(F\) 无需属于 \(L^2(m)\)，\(m\) 也允许有无限总质量。

## 证明思路

证明分两阶段。第一阶段换测度：固定 \(\lambda>0\)，令 \(m_\lambda=e^{\lambda F}m\)。主要障碍是正则性——Lipschitz 位势 \(V\) 虽保持生成元域与漂移公式 \(\Delta_Vu=\Delta u+\Gamma(V,u)\)，但 \(\Gamma(V,u)\) 未必 Sobolev，原始试验类在换测度后不再封闭。作者的绕法是对原热半群用预解式（resolvent）\(R_a=(a-\Delta)^{-1}\)：谱演算与热梯度估计给出从 \(L^2\cap L^\infty\) 到 \(W^{1,2}\cap L^\infty\) 的压缩性，从而映射 \(z\mapsto R_a(h+\Gamma(V,z))\) 在 \(\{z:z,|\nabla z|\in L^\infty\}\) 上有不动点，证得"有界且加权 Laplacian 有界 \(\Rightarrow\) Lipschitz"这一乘子正则性。有了它，先在共同生成元图像域中封闭加权 Bochner 不等式——核心恒等式 \(\mathcal B_V(g,\xi)-\mathcal B_0(g,w\xi)=-H_V(\nabla g,\nabla g)(w\xi)\) 把弱 Hessian 假设精确转化为曲率下降 \(K-\lambda G\)——再援引 Braun–Habermann–Sturm 的变曲率（variable curvature）等价，得到 \(m_\lambda\) 满足 \(\CD(K-\lambda G,\infty)\)。第二阶段把熵不等式定位到指定测地线：固定 \(\sigma\) 的一个严格内部子段，有限维 \(\mathrm{RCD}\) 空间非分叉（nonbranching，Deng 定理）使该子段成为其端点间唯一的最短测地线；用缩小球上归一化的测度逼近端点，则所有传输路径被迫收敛于该子段。熵恒等式 \(\Ent_{m_\lambda}(\mu)=\Ent_m(\mu)-\lambda\int F\dd\mu\) 把 \(\CD\) 不等式改写为 \(F\) 沿插值测度不低于端点弦、带 Green 核（Green kernel）修正的下界；取 \(\lambda_j\) 远大于端点熵以消去剩余熵项，取极限并对一切严格子区间应用，令 \(a''=\ell^2G\circ\sigma\)，Green 公式表明 \(F\circ\sigma-a\) 位于其每条弦之上、即为凹函数，其分布二阶导数非正，定理得证。

## 可信度与备注

按任务信息，本文主结果已有 Lean 形式化证明。它是族 356 姊妹篇《Gigli's distributional curvature characterization of Alexandrov spaces》反向论证最后一步的核心输入：修改距离函数加上本定理即得模型微分不等式、进而三角形比较与 Alexandrov 刻画；本篇证明只用一般满支撑 \(\mathrm{RCD}(K,N)\) 假设，与那篇的非坍缩和截面曲率结构无关，两篇结论彼此独立又互相支撑。族内旗舰篇尚未形式化，按 OpenAI 官方声明，未经形式化的结果可能有问题，整族引用时请以社区核验为准。

{% endraw %}
