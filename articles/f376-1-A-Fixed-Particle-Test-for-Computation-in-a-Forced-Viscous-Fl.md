---
layout: default
title: "A Fixed Particle Test for Computation in a Forced Viscous Flow"
family: "376"
discipline: "Partial differential equations"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Fixed Particle Test for Computation in a Forced Viscous Flow

> 结果族 376：Universal computation in forced Navier–Stokes flows　·　学科：Partial differential equations　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

在固定平坦环面、任意固定正可计算粘度、零初速的强迫 Navier–Stokes 流中，本文把普通（不可逆）图灵机直接编译为光滑外力：固定粒子进入固定开集当且仅当机器停机，且力与速度的一切混合导数在时间上既有界又平方可积，事件本身不可判定。

## 问题背景

流体中的通用计算此前需改编度规或使用非零初速；固定几何、固定粘度、从静止出发的强迫情形是空白。还有两个技术痛点：模拟图灵机的连续构造里，不同指令的平面像会重叠，这是机器不可逆性的几何体现；而保留历史的机制往往让空间门越用越细、导数估计越变越坏。本文的两项新意正是把可逆性所需的历史藏进第三个空间坐标的进制展开，并用超长的后续时间步换取所有混合导数的时间平方可积性。与同族改用可逆记录器的姊妹篇不同，这里直接使用机器的原始指令表，且粒子、探测区域、几何与粘度全部事先固定，只有力的有限程序依赖机器与输入。

## 主要结果

主定理：存在算法把确定单带图灵机 \(M\) 与有限词 \(w\) 编译为有效光滑零均值外力 \(f_{M,w}\)：(1) 方程 \(\partial_tu+(u\cdot\nabla)u=-\nabla p+\nu\Delta u+f\)、\(u(0)=0\) 在 \(\T^3\) 上有全局光滑解，古典类中唯一；(2) 对每个时间阶 \(h\ge0\) 与空间多重指标 \(\mu\)，\(\|\partial_t^h\partial_X^\mu u_{M,w}(t)\|_\infty\) 与 \(\|\partial_t^h\partial_X^\mu f_{M,w}(t)\|_\infty\) 都属于 \(L^\infty(0,\infty)\cap L^2(0,\infty)\)；(3) 粒子 \(a_*=(1/8,3/8,0)\) 进入 \(O=\{1/2<x<1\}\) 当且仅当 \(M\) 停机于 \(w\)。外力还可经 Helmholtz–Leray 投影（projection）改取无散度版本，速度与观测事件不变；装载区间之后，速度机制只依赖 \(M\) 而不依赖 \(w\)。推论：该固定粒子事件不可判定。

## 证明思路

先做位置编码：带头两侧的带子写成 \(B\) 进制小数 \((\ell,r)\)，状态方块按 \(x\) 分层——非停机状态 \(x\le1/4\)、停机状态 \(x\ge3/4\)，探测带 \(O\) 居中于 \(1/2<x<1\)。每条指令 \((q,l,a)\) 化为仿射分支 \(F_j\)，线性部分 \(\diag(\lambda_j,\lambda_j^{-1})\)、\(\lambda_j\in\{B^{-1},B,1\}\)；不同分支的像允许重叠。为区分重叠的历史，把已选分支的编号 \(j\in\{1,\dots,J\}\)（记 \(\Lambda=J+1\)）逐位记入第三坐标：\(z_n=\sum_{i<n}j_i\Lambda^{-i-1}\)，于是 \(\Lambda^nz=j_n/\Lambda\pmod 1\)，周期门 \(b_j(\Lambda^nz)\) 恰好选出当前指令；旧数位化作整数部分不再影响门，却未被擦除——这是 Bennett 历史带（history tape）的连续版。执行一步用两个脉冲：先"记录"，平面坐标不动、\(z\) 增加 \(j_n\Lambda^{-n-1}\)；再"执行"，\(z\) 不动、门选出对应的哈密顿场（Hamiltonian field）\(V_{j_n}\)，粒子沿路径 \(\Psi_{j,s}\)——中心线性插值配上互逆伸缩 \(\diag(g_j(s),g_j(s)^{-1})\)——精确到达下一个机器码；凸性保证非停机到非停机的路径全程 \(x\le1/4\)。最精细的一步是导数估计：对门 \(b_j(\Lambda^nz)\) 求高阶 \(z\) 导数需付出 \(\Lambda^{n\mu_z}\) 的因子，于是取步长 \(S_n=2^{n^2}\) 并在速度中放入 \(1/S_n\)，得 \(\|\partial_t^h\partial_X^\mu U(t)\|_\infty\le C_{h,\mu}S_n^{-1-h}\Lambda^{n\mu_z}\)；平方求和后级数 \(\sum_n2^{-(1+2h)n^2}\Lambda^{2n\mu_z}\) 收敛（\(n\ge4\Lambda\mu_z\) 时 \(\Lambda^{2n\mu_z}\le2^{n^2/2}\)），故一切混合导数属于 \(L^\infty\cap L^2\)。力由 \(f=\partial_tU+(U\cdot\nabla)U-\nu\Delta U\) 直接给出；速度公式同时列出所有分支、不引用实际选中的分支序列，配合 \(e^{-1/t}\) 型光滑断面（profile）的有效导数界与周期化的有限平移集，实现"不先运行机器再回放"的有效求值；无散度版本由有效的傅里叶投影引理给出。唯一性仍用差能量比较加 Gronwall 不等式。

## 可信度与备注

本文暂无形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。文中明确引用同族"Eventually Stationary"姊妹篇来处理外力最终定常的问题，另一姊妹篇则用可逆记录器加剪切流得到压强恒为零的周期机制；三篇在相同固定几何与观测设定下互相支撑。结论针对精确轨线，作者也声明不提供任意长运行的一致扰动容限与效率保证。

{% endraw %}
