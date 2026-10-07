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

## 一句话结论

证明了量子近似优化算法（QAOA）在"先取热力学极限、再增加线路深度"的次序下能逼近 SK 自旋玻璃的 Parisi 基态能量：对任意精度，都存在与系统规模和无序实现无关的确定性角度的有限深度线路达到该精度，证实了 Basso 等人的"最终 Parisi 最优"猜想。

## 问题背景

Sherrington–Kirkpatrick（SK）模型是 1975 年提出的全连接伊辛自旋玻璃（spin glass）：自旋 \(\sigma\in\{-1,1\}^n\) 的能量为 \(h_{n,J}(\sigma)=\frac1{\sqrt n}\sum_{i<j}J_{ij}\sigma_i\sigma_j\)，耦合 \(J_{ij}\) 是独立标准高斯变量。其基态能量密度极限由 Parisi 变分公式（Parisi formula）刻画——Guerra 证上界、Talagrand 证等式——是自旋玻璃理论的基石。2014 年 Farhi、Goldstone、Gutmann 提出量子近似优化算法（QAOA, Quantum Approximate Optimization Algorithm）：从均匀叠加态出发，交替演化代价哈密顿量与横场混合器。此前已知两条结果：对每个固定实例，深度趋于无穷时 QAOA 趋于该实例的最优值；对固定深度，系统尺寸趋于无穷时其性能有精确的极限刻画（FGGZ，2022）。Basso、Farhi、Marwaha、Villalonga、Zhou（2022）由此猜想深度足够大时 QAOA 的热力学极限值收敛到 Parisi 最优 \(P_*\)。卡点在于：固定实例的结果给不出随 \(n\) 增大仍一致的有限深度，必须把"选定线路"与"取热力学极限"的先后次序严格对调。

## 主要结果

记代价哈密顿量 \(C_{n,J}=\frac1{\sqrt n}\sum_{i<j}J_{ij}Z_iZ_j\)（\(X,Y,Z\) 为 Pauli 矩阵），混合器 \(B_n=\sum_iX_i\)，深度 \(p\) 的 QAOA 态为
\[\ket{\psi_{n,p,J}(\gamma,\beta)}=e^{-\mathrm{i}\beta_pB_n}e^{-\mathrm{i}\gamma_pC_{n,J}}\cdots e^{-\mathrm{i}\beta_1B_n}e^{-\mathrm{i}\gamma_1C_{n,J}}\ket{+}^{\otimes n}.\]
对固定角度先取 \(n\to\infty\) 得每自旋期望能量 \(v_p(\gamma,\beta)\)，再对角度取上确界得 \(Q_p\)。主定理（Theorem 1.1）断言 \(\lim_{p\to\infty}Q_p=P_*\)，其中 \(P_*=\lim_{n\to\infty}\frac1n\E\max_\sigma h_{n,J}(\sigma)\) 是 SK 基态能量常数。等价地说：对每个 \(\varepsilon>0\)，存在有限深度 \(p\) 与确定性角度 \(\gamma,\beta\in\R^p\)——不依赖 \(n\) 与无序 \(J\)——使 \(v_p(\gamma,\beta)\ge P_*-\varepsilon\)。这正是上述猜想的固定参数热力学表述。推论（Corollary 1.2）进一步给出大度正则图 MaxCut 的首阶最优：对围长超过 \(2p+1\) 的 \((D+1)\)-正则图 \(G\)，同一组角度（按度数缩放为 \(2\gamma/\sqrt D\)）切掉的边比例至少为 \(\frac12+\frac{P_*-\eta}{\sqrt D}\)，且对随机正则图在相继极限下以概率达到首阶最优。

## 证明思路

上界是平凡的（计算基测量只能产生经典构型），且追加零角度层使 \(Q_p\) 单调，故整个定理化归为：对每个精度构造一个有限"字"。第一步选古典目标：取零温 Parisi 极小化子 \(\gamma(t)\)，其扩散 \(\dd X_t=\gamma(t)u\,\dd t+\dd B_t\) 的梯度鞅满足一致性 \(\E u^2=t\) 与值公式 \(P_*=\int_0^1\E a(t,X_t)\,\dd t\)（\(u=\Phi_x\)，\(a=\Phi_{xx}\)）；对扩散做 Euler 离散并用一个额外高斯把终端梯度取整为自旋，得到有限个独立高斯符号函数的系数恒等式，其值逼近 \(P_*\)——这一输入依赖姊妹篇的满支撑定理。第二步在根树上实现：把每个新高斯坐标实现为"下一层子代计算的归一化聚合"，用正交性归纳使联合高斯律精确成立；根部的能量恰为该函数的单粒子部分，值公式因此直接传递，无需单独的边展开。第三步磨光与类型排除：先把所有传递函数换成有界光滑函数，再给顶点划分"类型"（type），让每个聚合过程排除接收者自身类型、路径祖先类型与少量辅助类型，从而阻止编译出的操作反馈到自身参数。第四步线路合成：用代价门与混合器，辅以由高斯标签形成的纵向场，沿"接收者—发送者—辅助者—发送者"的回路取交换子来实现邻居和；当回路回到同一发送者时，保持初态的辅助自旋恰好给出所需项，而细分发送者类型使不同发送者的贡献随类型变细而消失。第五步去种子：对已选定的有限线路，用一次不完美的代价回波产生一个带大相干位移的小分量；选择性自旋旋转只改变该分量、同时抵消对其余状态的主阶作用；再用一次长回波把变化放大成有限的纵向场，从而把所有纵向场种子门替换为普通门，且保持根能量不变。最后装配：按 \(\varepsilon/4\)、\(\varepsilon/8\) 逐级分配误差，得到一个与 \(D,n,J\) 都无关的普通有限字；此时才引用 Basso 等人的固定字"树—SK"恒等式（Proposition 2.1），把树上的边值等同于固定参数的 SK 极限值，完成证明。

## 可信度与备注

本文暂无形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。构造的古典支柱正是同族姊妹篇《Full support of the zero-temperature Sherrington–Kirkpatrick order parameter》——满支撑所保证的扩散一致性与有限高斯系数公式是第一步的出发点；论文另给出一条不经由该篇的正温度替代路线（Montanari 与 El Alaoui–Montanari–Sellke 的消息传递框架，加上 Lopatto 的正温满支撑定理）。作者坦承：不给所需深度的定量上界，也不提供高效的选角程序，结论是期望能量意义下的。

{% endraw %}
