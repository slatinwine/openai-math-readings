---
layout: default
title: "Quantum Depletion and Momentum Distribution in the Dilute Hard-Sphere Bose Gas"
family: "267"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Quantum Depletion and Momentum Distribution in the Dilute Hard-Sphere Bose Gas

> 结果族 267：Positive-temperature Bose–Einstein condensation and exact quantum depletion　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对三维硬球玻色气体的精确多体基态证明了完整的 Bogoliubov 动量分布：先取固定密度的热力学极限、再取稀薄极限，非零动量占据在标度 \(\sqrt{8\pi\rho a}\) 下收敛到 Bogoliubov 剖面，总质量 \(\frac{8}{3\sqrt\pi}\)，给出损耗定律 \(\frac{8}{3\sqrt\pi}\sqrt{\rho a^3}+o(\sqrt{\rho a^3})\)，对一切基态一致。

## 问题背景

即使处在零温，相互作用也会把粒子"挤出"凝聚体，被挤出的部分称为量子损耗（quantum depletion）。Bogoliubov 1947 年的准粒子（quasiparticle）理论与 Lee–Huang–Yang 1957 年的硬球赝势计算预言：稀薄三维气体的损耗占比为 \(\frac{8}{3\sqrt\pi}\sqrt{\rho a^3}\)，且损耗粒子按确定的动量剖面分布。能量侧的严格理论已推进到 Lee–Huang–Yang 阶（Dyson、Lieb–Yngvason、Yau–Yin、Fournais–Solovej，直到硬球的精确系数），但能量与占据是两回事：普通热力学极限下长波粒子的动能任意小，能谱展开不能自动给出轨道占据。此前的占据与损耗结果或处于散射长度量级 \(N^{-1}\) 的单盒设定（Boccato–Brennecke–Cenatiempo–Schlein；Brennecke–Lee–Nam），或盒子尺寸与稀薄度耦合增长（Fournais、Junge），或针对近似方程"simple equation"（Carlen–Jauslin–Lieb、Jauslin）。对精确硬球基态、在"先热力学后稀薄"的迭代极限下同时确定损耗总量及其动量分布，是本文完成的任务。

## 主要结果

在环面 \(\Lambda_L=(\mathbb R/L\mathbb Z)^3\) 上取硬球哈密顿量（对硬球，排除距离 \(a\) 同时就是散射长度）。设 \(\mathcal G_{N,L,a}\) 为最低玻色子本征空间上的迹一正算子集合，\(n_{\Gamma,L}(k)\) 为动量 \(k\) 平面波的占据数，\(B_{N,L,a}(\Gamma)\) 为常值轨道 \(u_{0,L}\) 的占据占比，\(\eta=\rho a^3\)。定理 1.1：对每个 \(a>0\)、每个有界连续实函数 \(f\) 与 \(\eps>0\)，存在 \(\rho_0>0\)，使得固定 \(0<\rho<\rho_0\) 后，沿一切 \(N_j/L_j^3\to\rho\) 的序列有

\[\limsup_{j\to\infty}\ \sup_{\Gamma\in\mathcal G_{N_j,L_j,a}}\left|\frac{1}{N_j\sqrt\eta}\sum_{k\ne0}f\!\left(\frac{k}{\sqrt{8\pi\rho a}}\right)n_{\Gamma,L_j}(k)-\int_{\mathbb R^3}f\,\dd\nu_{\rm Bog}\right|\le\eps,\]

其中 \(\nu_{\rm Bog}(\dd t)=\frac{(8\pi)^{3/2}}{(2\pi)^3}g(t)\dd t\)，\(g(t)=\frac{|t|^2+1}{2\sqrt{|t|^4+2|t|^2}}-\frac12\)，是总质量为 \(\frac{8}{3\sqrt\pi}\) 的有限正测度。取 \(f=1\) 得推论 1.2：在同样迭代极限下，\(1-B_{N,L,a}(\Gamma)=\frac{8}{3\sqrt\pi}\sqrt{\rho a^3}+o(\sqrt{\rho a^3})\)，对一切纯态与混合基态一致。定理控制占据的一切热力学聚积值而不要求固定正密度下占据极限存在，并确定损耗粒子在动量标度 \(\sqrt{8\pi\rho a}\)（逆 healing length）上的分布。

## 证明思路

核心是精确拆分恒等式 \(1-B=\langle\Psi,(1-P_\ell)_1\Psi\rangle+\|(P_\ell-P_0)_1\Psi\|^2\)：把损耗分成"尺度 \(\ell\) 盒内变化"与"盒间平均值变化"两块，\(P_\ell\) 是投影到逐盒常值函数、\(P_0\) 投影到全局常值。第一块用能量控制，但普通能量下界只给标量自由能；本文从 Fournais–Junge–Girardot–Morin–Olivieri–Triay 的中间算子估计中保留一个度量 Bogoliubov 激发数目的正算子项，配合硬球 Lee–Huang–Yang 阶能量上界（Basti–Brooks–Cenatiempo–Olgiati–Schlein），提取出对盒内局域激发一致的单体算子估计，连复值、动量非对角的算子都覆盖。第二块能量无能为力，改用删除测度（Palm 型测度）：\(s_v(Y')^2=\frac{V}{|v|}\int_v\Phi(y,Y')^2\dd y\) 是"按在盒 \(v\) 中的出现权重选出一个粒子并积掉其位置"后的浴分布，比较远盒的 \(s_v\) 即控制波函数的空间变化。比较通过粒子链运输删除：把两份构型耦合，一份删首粒子、另一份删末粒子后剩余构型完全相同；短 Brown 桥在保住精确硬球约束下实现重排，条件桥律的归一化在似然比中相消；长链两端附近的路径保持不变，以消除端点相互作用的误差；随机路线（Benjamini–Pemantle–Peres 的指数交尾路径，辅以 Kesten 外边界绕行）使该误差小于损耗标度。随后用三个估计接通投影：相邻小盒的四阶矩比较、小盒上的占据估计、远盒的二阶矩比较，把第二块压到 \(o(\sqrt{\rho a^3})\)；实部虚部分解把结论推广到任意基向量。最后识别动量分布：平移算子的期望恰是占据测度的 Fourier 变换，于是把平移限制在大盒内、并对盒分划的全体平移取平均——只有少数平移会把点与其平移像分进不同盒子；用局域激发投影夹住平移算子，使切割误差正比于损耗密度而非总粒子密度（这一替换在所选尺度下不可或缺）；局域单体估计随即给出 Bogoliubov 剖面的 Fourier 变换，配合总损耗的界得紧性，从而对一切有界连续 \(f\) 收敛；混合态由凸性得到。

## 可信度与备注

本篇暂无形式化证明，结论以社区核验为准。删除能量与空间计数等输入取自同族姊妹篇——硬球基态凝聚定理，它给出常值轨道的一致正占据与计数矩估计——本篇在其上建立损耗与动量分布；同族有界势姊妹篇把同一框架推广到固定有界位势，三篇在尺度层级与路径技术上互洽互持。按 OpenAI 官方声明，未经形式化的结果可能存在问题。

{% endraw %}
