---
layout: default
title: "The joint Dickman law for consecutive integers"
family: "012"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The joint Dickman law for consecutive integers

> 结果族 012：Independent largest prime factors of consecutive integers　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

无条件证明了相邻整数 \(n\) 与 \(n+1\) 的最大素因子在对数尺度上按自然密度渐近独立、边际均为 Dickman 分布，正面解决 Erdős–Pomerance 联合猜想，并得到 \(P^+(n)<P^+(n+1)\) 的密度恰为 1/2。

## 问题背景

设 \(P^+(n)\) 为 \(n\) 的最大素因子（largest prime factor）。从 Dickman（1930）经 Ramaswami 到 de Bruijn 的经典光滑数（smooth number）理论给出：\(n\le X\) 中满足 \(P^+(n)\le X^a\) 的比例为 \(\rho(1/a)\)，其中 \(\rho\) 是 Dickman–de Bruijn 函数。这确定了单个整数的对数光滑性分布。1978 年 Erdős 与 Pomerance 提出联合问题：相邻两整数的最大素因子大小是否渐近独立？他们只证得两种排序的自然下密度为正（显式下界 0.0099）。此后近五十年，下密度记录被逐步推高——de la Bretèche–Pomerance–Tenenbaum 与 Fouvry、Wang、Lü–Wang、直到 Yang 的 0.280——但这些都只是下密度界，不断言密度存在；Teräväinen（2018）在 对数密度 意义下证得乘积律；Tao–Teräväinen（2019、2026）在除去一列零对数密度的例外尺度后得到普通平均；Wang 则需假设 friable 整数版的 Elliott–Halberstam 猜想。卡点正在于：不附任何条件、在所有尺度上取得普通自然密度极限。

## 主要结果

主定理（联合 Dickman 律，joint Dickman law）：对任意固定的 \(a,b\in(0,1)\)，

\[\lim_{X\to\infty}\frac1X\#\{2\le n\le X:\ P^+(n)\le n^a,\ P^+(n+1)\le n^b\}=\rho(1/a)\,\rho(1/b),\]

极限沿全体实数 \(X\) 以普通无权计数取。等价地说，\(\log P^+(n)/\log n\) 与 \(\log P^+(n+1)/\log n\) 在自然密度下收敛为独立随机变量，公共分布函数为 \(D(t)=\rho(1/t)\)。经容斥还得到上尾独立性（upper-tail independence）：\(\Pr(P^+(n)>X^c,\ P^+(n+1)>X^d)=(1-D(c))(1-D(d))\)，即 Erdős–Pomerance 原猜想的形式。推论（比较问题，通常归于 Erdős–Turán）：\(P^+(n)<P^+(n+1)\) 与反序的自然密度均为 \(1/2\)。因极限律连续、乘积测度在对角线上零质量，由极限律的对称性即得，无需任何定量分离估计。

## 证明思路

全文是"编码—放大—换元—图比较"的反证长链。

先把最大素因子编码为有限组素因子计数：将 \((x^{1/J},x]\) 中的素数分为 \(J-1\) 个对数箱 \(\mathcal B_{k,x}\)，用完全乘性标签 \(f_x(n)=\prod_k\zeta_k^{\Omega_{\mathcal B_{k,x}}(n)}\) 记录各箱计数（\(\Omega_E\) 为计入重数的素因子个数），另取独立相位的标签 \(g_x\)，中心化为 \(F_x=f_x-\mu\)。有限 Fourier 反演把联合律归结为混合去相关：\(\frac1x\sum_{n<x}\overline{g_x(n)}F_x(n+1)\to0\)，两套相位可独立选取正是两列计数向量独立的来源。两个支柱性质：其一，固定乘子不变性 \(F_x(un)=F_x(n)\)，因为固定 \(u\) 的素因子最终都落在箱之外；其二，加权短平均消没：长度 \(L_B\to\infty\) 的区间上 \(F_x(n+i)G_{B,v}(n+i)\) 的平均在均方意义下趋零。后者先用 Vandermonde 型张量插值把 \(F_x\)（只依赖有限个箱计数）写成有限个实非负乘性函数的组合，再对剩余条件用 Dirichlet 特征分解：主特征部分用 Matomäki–Radziwiłł 实数短区间定理比较长平均，非主特征扭转用 Matomäki–Radziwiłł–Tao 复数定理控制，所需特征距离发散由 Vinogradov–Korobov 型 \(\zeta\) 上界保证。

再假设混合相关沿某子列不趋于零。在 \((0,\infty)\times\widehat{\mathbb Z}\)（profinite 整数，配 Haar 概率测度）上作紧性提取，得到有界剖面 \(W(t,w)\)，并选光滑截断 \(\phi\) 使 \(\beta_*=|\int\phi W|>0\)。随后构造除子放大器（divisor amplifier）\(D_B(n)\)：对分解 \(n=am\)、\(n+1=cl\)（\(e^B<c<e^{2B}\)、\(Tc<a<2Tc\)）取非负加权和。通过"每个辅助素数以 \(1/p\) 概率入选、再由公平硬币分给系数或余项"的比较模型，配合上界筛导出的加法乘积小球集中估计，证得 \(D_B\) 的 Haar 均值不低于某 \(d_0>0\) 且 \(L^2\) 范数有界；又因 \(D_B\) 只依赖趋于无穷的大素数剩余类，而 \(W\) 与每个固定剩余坐标渐近独立，放大后的相关积分仍约为 \((\int\phi W)(\int D_B)\)，相关性得以存活。

接着展开 \(n=am\)，用乘子不变性把模一因子 \(g_x(m)\) 提到内层和之外，Cauchy–Schwarz 将其消去，留下下界为正的二次能量 \(I_{2,x}\ge c_5BT\)，其对角项因系数上界 \(o(T)\) 而可忽略。非对角项中 \(c\mid am+1\) 与 \(c\mid bm+1\) 强制 \(a-b=jc\)（\(0<|j|\le T\)），精确换元 \(n'=bl_a\)、\(n'+j=al_b\)（\(l_a=(am+1)/c\)）把标签乘积化为 \(\overline{F_x(n')}F_x(n'+j)\)：能量变成尺度 \(Tx\) 上普通加性移位的加权图。

最后把端点处的真实整除集与独立模型集（每个素数以 \(1/p\) 入选）耦合，在期望切范数（cut norm）意义下把算术核与端点特征积核比较：特征 \(V_l\) 定义为对端点素数集合作公平分裂后 \(\log b/B\) 落入粗网格胞的条件概率；用 Fourier 检测方程 \(a-b=jc\)，把滞后 \(j\) 的奇性级数（singular series）与光滑滞后因子同端点分离，核近似为 \(\sum_l c_{l,B}(j,s)V_l(S_i)V_l(S_k)\)，再借 Frieze–Kannan 型列采样把比较升级到切范数。收尾时以多项式逼近把 \(V_l\) 表为 \(G_{B,v}(n)=\prod_{p\mid n}(1+p^{-v/B})/2\) 的有限组合，把奇性级数换成周期函数，并把位置块细分为长度不超过 \(\delta T\) 的小块：能量于是分解为前述短平均的乘积，而短平均消没，与正能量矛盾。由于坏子列任意抽取，全序列极限成立。末节从阶乘矩与延迟方程 \(uH'(u)=-H(u-1)\) 识别出 Dickman 边际 \(H=\rho\)，经挤压论证从固定阈值 \(X^c\) 过渡到移动阈值 \(n^a\)，并由乘积极限律的对称性导出排序推论。

## 可信度与备注

本篇是结果族 012 的唯一手稿，主结果暂无 Lean 形式化证明（族描述中的 Lean 链接属族级文档，不覆盖该定理），请以社区核验为准。论文技术自足，除子放大与素数整除图在 Tao、Helfgott–Radziwiłł、Pilatte、Tao–Teräväinen 等工作中有明确先例，而本文的粗糙除子图与端点核比较系局部新证。按 OpenAI 官方声明，未经形式化的结果可能存在问题，最终可信度有赖同行评议与独立复核。

{% endraw %}
