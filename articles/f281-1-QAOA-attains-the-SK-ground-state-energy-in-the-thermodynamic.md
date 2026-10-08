---
layout: default
title: "QAOA attains the SK ground-state energy in the thermodynamic-first limit"
family: "281"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | QAOA attains the SK ground-state energy in the thermodynamic-first limit

> 结果族 281：QAOA attains the SK optimum in the thermodynamic-first limit　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

设想一场巨大聚会，任意两位客人合不合得来完全随机，你要安排所有人的座位使总冲突最小——这就是 SK 自旋玻璃模型。QAOA 是一台量子"调解机"：轮流做两件事，先顺着冲突能量演化，再随机晃一晃跳出局部最优。本文证明：先让聚会无限大、再让调解机的层数加深，它能做到理论极限的最优安排。

**关键词卡片**

- SK 自旋玻璃（Sherrington–Kirkpatrick spin glass）：所有点对随机相互作用，能量地形布满山谷
- QAOA（Quantum Approximate Optimization Algorithm）：交替执行"代价演化"与"横场混合"的量子优化线路
- 深度 p（depth）：交替演化的层数，越深越接近真正的退火
- Parisi 值 P*（Parisi formula）：SK 基态能量的精确理论极限
- 热力学优先极限（thermodynamic-first limit）：先取系统数 `@@M@@n\to\infty@@`、再取深度 `@@M@@p\to\infty@@` 的极限次序

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <line x1="60" y1="235" x2="520" y2="235" stroke="#000" stroke-width="1.5"/>
  <line x1="60" y1="235" x2="60" y2="40" stroke="#000" stroke-width="1.5"/>
  <text x="470" y="258" font-size="13" fill="#000">深度 p →</text>
  <text x="16" y="46" font-size="13" fill="#000">每自旋能量</text>
  <line x1="62" y1="70" x2="515" y2="70" stroke="#c00" stroke-width="1.5" stroke-dasharray="7,5"/>
  <text x="390" y="62" font-size="13" fill="#c00">Parisi 理论最优 P*</text>
  <circle cx="150" cy="192" r="5" fill="#000"/>
  <circle cx="230" cy="152" r="5" fill="#000"/>
  <circle cx="310" cy="122" r="5" fill="#000"/>
  <circle cx="390" cy="102" r="5" fill="#000"/>
  <circle cx="468" cy="86" r="5" fill="#000"/>
  <path d="M150 192 Q 310 128 468 86" fill="none" stroke="#666" stroke-width="1" stroke-dasharray="3,4"/>
  <text x="150" y="222" font-size="13" fill="#000">Q₁</text>
  <text x="230" y="182" font-size="13" fill="#000">Q₂</text>
  <text x="310" y="152" font-size="13" fill="#000">Q₃</text>
  <text x="390" y="132" font-size="13" fill="#000">Q₄</text>
  <text x="443" y="116" font-size="13" fill="#000">Q₅</text>
  <text x="88" y="120" font-size="13" fill="#000">深度增加，</text>
  <text x="88" y="140" font-size="13" fill="#000">Q_p 逼近 P*</text>
</svg>

</div>

公式卡（数字版定理）：`@@M@@\lim_{p\to\infty}Q_p=P_*@@`。等价地，任给精度 `@@M@@\varepsilon>0@@`，存在有限深度 `@@M@@p@@` 与一组固定的角度 `@@M@@(\gamma,\beta)@@`——不随 `@@M@@n@@`、不随随机耦合 `@@M@@J@@` 改变——使每自旋期望能量 `@@M@@v_p(\gamma,\beta)\ge P_*-\varepsilon@@`。

**为什么值得关心**

它证实了 Basso 等人"QAOA 终将 Parisi 最优"的猜想，但也坦承不给所需深度的定量上界、也没有高效的选角度程序——是定性层面的一锤定音。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了量子近似优化算法（QAOA）在"先取热力学极限、再增加线路深度"的次序下能逼近 SK 自旋玻璃的 Parisi 基态能量：对任意精度，都存在与系统规模和无序实现无关的确定性角度的有限深度线路达到该精度，证实了 Basso 等人的"最终 Parisi 最优"猜想。

## 问题背景

Sherrington–Kirkpatrick（SK）模型是 1975 年提出的全连接伊辛自旋玻璃（spin glass）：自旋 `@@M@@\sigma\in\{-1,1\}^n@@` 的能量为 `@@M@@h_{n,J}(\sigma)=\frac1{\sqrt n}\sum_{i<j}J_{ij}\sigma_i\sigma_j@@`，耦合 `@@M@@J_{ij}@@` 是独立标准高斯变量。其基态能量密度极限由 Parisi 变分公式（Parisi formula）刻画——Guerra 证上界、Talagrand 证等式——是自旋玻璃理论的基石。2014 年 Farhi、Goldstone、Gutmann 提出量子近似优化算法（QAOA, Quantum Approximate Optimization Algorithm）：从均匀叠加态出发，交替演化代价哈密顿量与横场混合器。此前已知两条结果：对每个固定实例，深度趋于无穷时 QAOA 趋于该实例的最优值；对固定深度，系统尺寸趋于无穷时其性能有精确的极限刻画（FGGZ，2022）。Basso、Farhi、Marwaha、Villalonga、Zhou（2022）由此猜想深度足够大时 QAOA 的热力学极限值收敛到 Parisi 最优 `@@M@@P_*@@`。卡点在于：固定实例的结果给不出随 `@@M@@n@@` 增大仍一致的有限深度，必须把"选定线路"与"取热力学极限"的先后次序严格对调。

## 主要结果

记代价哈密顿量 `@@M@@C_{n,J}=\frac1{\sqrt n}\sum_{i<j}J_{ij}Z_iZ_j@@`（`@@M@@X,Y,Z@@` 为 Pauli 矩阵），混合器 `@@M@@B_n=\sum_iX_i@@`，深度 `@@M@@p@@` 的 QAOA 态为
`@@M@@D\ket{\psi_{n,p,J}(\gamma,\beta)}=e^{-\mathrm{i}\beta_pB_n}e^{-\mathrm{i}\gamma_pC_{n,J}}\cdots e^{-\mathrm{i}\beta_1B_n}e^{-\mathrm{i}\gamma_1C_{n,J}}\ket{+}^{\otimes n}.@@`
对固定角度先取 `@@M@@n\to\infty@@` 得每自旋期望能量 `@@M@@v_p(\gamma,\beta)@@`，再对角度取上确界得 `@@M@@Q_p@@`。主定理（Theorem 1.1）断言 `@@M@@\lim_{p\to\infty}Q_p=P_*@@`，其中 `@@M@@P_*=\lim_{n\to\infty}\frac1n\E\max_\sigma h_{n,J}(\sigma)@@` 是 SK 基态能量常数。等价地说：对每个 `@@M@@\varepsilon>0@@`，存在有限深度 `@@M@@p@@` 与确定性角度 `@@M@@\gamma,\beta\in\R^p@@`——不依赖 `@@M@@n@@` 与无序 `@@M@@J@@`——使 `@@M@@v_p(\gamma,\beta)\ge P_*-\varepsilon@@`。这正是上述猜想的固定参数热力学表述。推论（Corollary 1.2）进一步给出大度正则图 MaxCut 的首阶最优：对围长超过 `@@M@@2p+1@@` 的 `@@M@@(D+1)@@`-正则图 `@@M@@G@@`，同一组角度（按度数缩放为 `@@M@@2\gamma/\sqrt D@@`）切掉的边比例至少为 `@@M@@\frac12+\frac{P_*-\eta}{\sqrt D}@@`，且对随机正则图在相继极限下以概率达到首阶最优。

## 证明思路

上界是平凡的（计算基测量只能产生经典构型），且追加零角度层使 `@@M@@Q_p@@` 单调，故整个定理化归为：对每个精度构造一个有限"字"。第一步选古典目标：取零温 Parisi 极小化子 `@@M@@\gamma(t)@@`，其扩散 `@@M@@\dd X_t=\gamma(t)u\,\dd t+\dd B_t@@` 的梯度鞅满足一致性 `@@M@@\E u^2=t@@` 与值公式 `@@M@@P_*=\int_0^1\E a(t,X_t)\,\dd t@@`（`@@M@@u=\Phi_x@@`，`@@M@@a=\Phi_{xx}@@`）；对扩散做 Euler 离散并用一个额外高斯把终端梯度取整为自旋，得到有限个独立高斯符号函数的系数恒等式，其值逼近 `@@M@@P_*@@`——这一输入依赖姊妹篇的满支撑定理。第二步在根树上实现：把每个新高斯坐标实现为"下一层子代计算的归一化聚合"，用正交性归纳使联合高斯律精确成立；根部的能量恰为该函数的单粒子部分，值公式因此直接传递，无需单独的边展开。第三步磨光与类型排除：先把所有传递函数换成有界光滑函数，再给顶点划分"类型"（type），让每个聚合过程排除接收者自身类型、路径祖先类型与少量辅助类型，从而阻止编译出的操作反馈到自身参数。第四步线路合成：用代价门与混合器，辅以由高斯标签形成的纵向场，沿"接收者—发送者—辅助者—发送者"的回路取交换子来实现邻居和；当回路回到同一发送者时，保持初态的辅助自旋恰好给出所需项，而细分发送者类型使不同发送者的贡献随类型变细而消失。第五步去种子：对已选定的有限线路，用一次不完美的代价回波产生一个带大相干位移的小分量；选择性自旋旋转只改变该分量、同时抵消对其余状态的主阶作用；再用一次长回波把变化放大成有限的纵向场，从而把所有纵向场种子门替换为普通门，且保持根能量不变。最后装配：按 `@@M@@\varepsilon/4@@`、`@@M@@\varepsilon/8@@` 逐级分配误差，得到一个与 `@@M@@D,n,J@@` 都无关的普通有限字；此时才引用 Basso 等人的固定字"树—SK"恒等式（Proposition 2.1），把树上的边值等同于固定参数的 SK 极限值，完成证明。

## 可信度与备注

本文暂无形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。构造的古典支柱正是同族姊妹篇《Full support of the zero-temperature Sherrington–Kirkpatrick order parameter》——满支撑所保证的扩散一致性与有限高斯系数公式是第一步的出发点；论文另给出一条不经由该篇的正温度替代路线（Montanari 与 El Alaoui–Montanari–Sellke 的消息传递框架，加上 Lopatto 的正温满支撑定理）。作者坦承：不给所需深度的定量上界，也不提供高效的选角程序，结论是期望能量意义下的。

{% endraw %}
