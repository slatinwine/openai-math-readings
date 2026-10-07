---
layout: default
title: "From partial permutation information to Fourier bounds"
family: "238"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | From partial permutation information to Fourier bounds

> 结果族 238：Optimal logarithmic mixing of the Thorp shuffle　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明一条抽象传递定理：当 \(n\) 沿 8 的倍数增大时，若均匀随机 \(7n/8\) 张牌的像在平均总变差下接近均匀注入分布、且符号均值趋于零，则两个独立同律排列的乘积收敛到 \(S_n\) 上的均匀分布，把"部分置换信息"升级为"全牌混合"。

## 问题背景

一个排列可以在绝大多数标签上看起来均匀、却远非均匀：交错群（alternating group）上的均匀分布在任何至多 \(n-2\) 张牌的像上都均匀，障碍正是奇偶性（符号表示）。因此"部分置换信息何时能控制整个排列律"需要额外论证。动机来自 Thorp 洗牌：姊妹篇们能够证明"大部分牌的联合位置接近均匀"这类边际估计，本篇提供从这类估计通往全群收敛的通用表示论机器，延续 Diaconis–Shahshahani 分析随机游走的 Fourier 方法传统，但不预设任何具体洗牌模型或物理时间。

## 主要结果

主定理（互补陪集控制 Fourier 矩阵）：把 \(n\) 个标签分成 \(b\) 块，\(H_i\) 为在块外恒等的块子群；若非负测度 \(f\)（质量至多 1）在每个左陪集上满足封顶 \(f(gH_i)\le B/[G:H_i]\)，则对任意 \(u>0\) 与任意维数 \(D\) 的不可约表示 \(\rho\)，有 Hilbert–Schmidt 范数平方界 \(\|\widehat f(\rho)\|_{\mathrm{HS}}^2\le bBC_uD^{-1+(u+2)/b}\)，其中 \(C_u=\sup_m\sum_{\lambda\vdash m}D_\lambda^{-u}\) 是有限常数（互逆维数和；去掉平凡与符号表示后趋于零，文中给出初等证明）。主要推论：\(n\to\infty\) 经过 8 的倍数时，若 \(\mu_n\) 的均匀随机 \(7n/8\) 张牌像组的平均总变差误差为 \(o(1)\)、且符号均值为 \(o(1)\)，则 \(\|\mu_n^{*2}-U\|_{\mathrm{TV}}\to0\)；只用较弱的轨道路线则需要四次卷积。

## 证明思路

核心困难是限制的多重性（multiplicity）：把 \(\rho\) 限制到 \(H_1\times\cdots\times H_b\) 后分解为张量类型 \((V_{\tau_1}\otimes\cdots\otimes V_{\tau_b})\otimes\mathcal A\)，多重空间 \(\mathcal A\) 可以任意大。第一条轨道引理破解了它：单个向量的轨道张成维数至多为各类型维数的平方和，因为群在某一类型的所有拷贝上的作用都是 \(\tau\otimes I\)，轨道落在维数 \(a^2\) 的矩阵空间 \(\operatorname{End}(V_\tau)\) 的像里——多重性放大环境空间，却不放大移动一个固定向量所需的矩阵空间。

先看轨道证明：每个张量类型的因子维数乘积不超过 \(D\)，必有某因子维数不超过 \(D^{1/b}\)；把整个同构分量指派给一个小因子，得到正交分解 \(V_\rho=E_1\oplus\cdots\oplus E_b\)。固定 \(v_i\in E_i\)，其轨道张成 \(W_i\) 的维数用 \(C_u\) 控制为至多 \(C_uD^{(u+2)/b}\)。再用 Schur 引理：对均匀群平均的投影满足 \(\mathbb E_U\rho(g)\Pi_i\rho(g)^*=(\dim W_i/D)I\)；陪集封顶把这一均值转换成对 Fourier 系数的逐向量界。

第二条 isotypic 证明更强，控制整个矩阵：用子群中心幂等元 \(e_{H,\tau}=\frac{a}{|H|}\bar\chi_\tau\) 做卷积，它在每个陪集内单独作用，陪集式 Plancherel 恒等式给出对所有环境不可约表示求和的平方范数界 \(Bza^2\)（\(z\) 为质量）；小类型投影满足覆盖不等式 \(I\preceq\sum_i\sum_{\tau}\ P_{\rho,H_i,\tau}\)，对正算子 \(\widehat f(\rho)^*\widehat f(\rho)\) 取迹即得全矩阵界。Hilbert–Schmidt 范数控制整矩阵时，正则表示的权重是 \(D\) 而非 \(D^2\)，这正是卷积次数从四降到二的原因。

应用链条为：平均边际假设先选出八块划分（误差之和 \(o(1)\)），修剪出公共的次概率测度（质量 \(1-o(1)\)、陪集封顶 1），取 \(b=8\)、\(u=1\) 得平方界 \(8C_1D^{-5/8}\)；两次卷积后非符号贡献以 \((8C_1)^2\sum D^{-1/4}\) 计趋于零，符号与丢失质量另行消去。论文其余部分把同一框架推广到双侧（像与逆像）控制、等变核、逐排列选择省略集、熵比较与稀有事件条件化、以及半副牌的条件乘积结构（带符号 tabloid 基）等多种部分信息类型，并明确区分各假设的适用范围。

## 可信度与备注

本篇是族内的"抽象机器"篇：不证明任何洗牌混合的数值结论，只建立从部分信息到全群收敛的传递定理；姊妹篇"随机坐标架"的 \(512d\) 推论即引用本篇的同构估计与互逆维数和结果。主结果尚未形式化，按 OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。互逆维数和的初等证明与 Liebeck–Shalev 的 Witten zeta 渐近相互对照，且轨道与 isotypic 两条证明路线彼此独立，可互相校验。

{% endraw %}
