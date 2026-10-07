---
layout: default
title: "A Fock-space inequality and the Laughlin spectral gap"
family: "269"
discipline: "Mathematical physics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Fock-space inequality and the Laughlin spectral gap

> 结果族 269：Uniform Laughlin gap and stability under bounded scalar disorder　·　学科：Mathematical physics　·　验证状态：主结果已 Lean 形式化

## 一句话结论

正面解决球面费米 Laughlin 谱隙猜想：满 `@@M@@V_1@@` 相互作用、1/3 填充下，Laughlin 态之上的谱隙对所有充分大系统至少 `@@M@@1/25@@`；更强的 Fock 空间不等式 `@@M@@H_Q^2\ge\gamma H_Q@@`（`@@M@@\gamma>1/25@@`）与粒子数无关。

## 问题背景

1983 年 Laughlin 给出分数量子霍尔效应 1/3 填充态的显式波函数；Haldane 的球面几何与赝势（pseudopotential）给出极简的父哈密顿量：每对电子在相对角动量（relative angular momentum）1 时付出能量一。其精确零模早已知晓，但谱隙猜想——正谱的一致下界——要求控制与零模正交的所有竞争态，这一直是悬案：Haldane 与 Rezayi 1985 年的有限尺寸研究只提供数值证据，Girvin–MacDonald–Platzman 的密度波变分发只给上界。此前严格的一致谱隙仅见于细柱、细环几何上的截断赝势（Nachtergaele–Warzel–Young、Warzel–Young）；本文处理的是膨胀球面上的满（未截断）相互作用，正是 Rougerie 综述中记录的球面谱隙猜想。

## 主要结果

设 `@@M@@U_Q@@` 为球面上带 `@@M@@Q@@` 个磁通量子的最低朗道能级（lowest Landau level），即自旋 `@@M@@Q/2@@` 表示；哈密顿量 `@@M@@H_{N,Q}=\sum_{i<j}P_{ij}^{(1)}@@`，每对系数为一、不做任何依赖 `@@M@@N@@` 或 `@@M@@Q@@` 的重标度。把它直和延拓成 Fock 空间 `@@M@@\mathcal F_Q@@` 上的 `@@M@@H_Q@@`。主定理：取 `@@M@@\gamma_*=\frac{4616733319001}{10^{14}}>\frac1{25}@@`，对每个 `@@M@@0<\gamma<\gamma_*@@` 存在 `@@M@@Q_\gamma@@`，使得 `@@M@@Q\ge Q_\gamma@@` 时在整个 `@@M@@\mathcal F_Q@@` 上有 `@@M@@H_Q^2\ge\gamma H_Q@@`，阈值与粒子数无关，谱因而含于 `@@M@@\{0\}\cup[\gamma,\infty)@@`。推论：在 Laughlin 磁通 `@@M@@Q=3(N-1)@@` 处零模唯一，恰为 `@@M@@\Psi_{\mathrm L,N}=\prod_{i<j}(u_iv_j-u_jv_i)^3@@`，故 `@@M@@H_{N,Q}\ge\frac1{25}(I-P_{\mathrm L,N})@@`，即通常意义的基态谱隙至少 `@@M@@1/25@@`。文中还导出固定磁通下电荷隙（charge gap）与中性隙的比较 `@@M@@\Delta_N\ge N/[25(N-1)]@@`，并把结果转移到平面情形，证明 Rougerie 综述 Conjecture A.1 的费米三次情形。

## 证明思路

证明 `@@M@@H^2-\gamma H\ge0@@` 是通向谱隙的经典路线（Knabe 型判据）。先把 `@@M@@H_Q^2@@` 正规序展开为二、三、四体项，再与一个显式正算子 `@@M@@\mathcal K_Q=(2Q-1)\int_{SU(2)}\sum_{\rho=1}^7F_\rho(g)^\dagger F_\rho(g)\,dg@@` 比较：每个 `@@M@@F_\rho@@` 是对湮灭算子与"灭三生一"算子的指定线性组合，辅助算子只涉及有限个轨道模，哈密顿量本身从不截断。先由旋转对称把比较约化到固定自旋块：三体块有显式谱，尾部贡献收敛于 `@@M@@61/4096@@`。四体块是真正的难点——把相互作用对耦合到另一对的自旋扇区会产生同一总自旋的多份拷贝，它们的外积（wedge）图像可能线性相关，极限 Gram 矩阵有核，正定性无法靠连续性转移。作者先用七行有理数据证书直接验证极限块上的有限不等式，再解决转移问题：在固定的 25 个轨道模上作精确的对角变量代换 `@@M@@\Delta_Q@@`，把有限磁通的湮灭子精确改写为极限形式，使一切误差都被局部对能量控制，相对误差 `@@M@@\rho_Q\to0@@`；模外粒子只是旁观者，局域不等式经张量积恒等延拓到整个 Fock 空间。另一巧妙观察是先对正交的最高向量求和、再作外积，用 Bessel 不等式一次性处理所有等价自旋拷贝，把四体误差压到 `@@M@@1222\varepsilon@@`（`@@M@@\varepsilon=3\times10^{-6}@@`）。各项合账得 `@@M@@H_Q^2\ge\mathcal K_Q+(\gamma_*-o(1))H_Q@@`，全部误差与收敛阈值均与粒子数无关。最后用基于高斯引理与唯一分解的初等整除论证证明 Laughlin 磁通处核恰为 Laughlin 线，把 Fock 不等式转成基态谱隙；并借助 Lemm–Nachtergaele–Warzel–Young 的递归谱关系推出电荷隙比较。

## 可信度与备注

主结果已 Lean 形式化（见结果族文档 lean/docs/269.md），是本族的基石；姊妹篇《Uniform Stability of the Spherical Laughlin Gap》以本文的一致 Fock 谱隙为无微扰输入，证明无序稳定性并把本文的四体比较强化为保留块版本。文中阈值均为存在性常数，未给出显式磁通下限。按 OpenAI 官方声明，未经形式化的结果可能有问题——本篇主结果已有形式化背书，姊妹篇则仍待社区核验。

{% endraw %}
