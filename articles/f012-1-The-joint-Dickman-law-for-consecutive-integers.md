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

## 入门导读 🐣

问一栋楼里的两户邻居：各自家里"最大的一件家具"有多大？知道第一家的情况，能帮你猜第二家吗？这篇论文证明：对相邻整数 `@@M@@n@@` 与 `@@M@@n+1@@` 各自的最大素因子而言，答案是完全帮不上忙——两者渐近独立，像独立抛硬币。这正面解决了 Erdős–Pomerance 在 1978 年提出的联合猜想。

**关键词卡片**

- 最大素因子（largest prime factor `@@M@@P^+(n)@@`）：`@@M@@n@@` 的素数分解里最大的那个素数。
- 光滑数（smooth number）：所有素因子都不超过某个界的数，如 `@@M@@72=2^3\times3^2@@`。
- Dickman 函数（Dickman function `@@M@@\rho@@`）：衡量随机整数"足够光滑"概率的函数，`@@M@@\rho(2)=1-\ln 2@@`。
- 渐近独立（asymptotic independence）：样本趋于无穷时，两组统计量互不提供信息。
- 自然密度（natural density）：不加权、按普通比例取的极限频率，数论中最强的密度概念。

**看个具体例子**

具体数字：不超过 `@@M@@X@@` 的整数中约 `@@M@@30.7\%@@` 没有超过 `@@M@@\sqrt{X}@@` 的素因子（即 `@@M@@\rho(2)\approx0.307@@`）。定理给出乘积律：相邻两数同时这么光滑的比例趋于 `@@M@@\rho(2)^2\approx9.4\%@@`，恰是两个百分比相乘；由此还得到 `@@M@@P^+(n)<P^+(n+1)@@` 的密度恰为 `@@M@@\tfrac12@@`。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="34" font-size="15" text-anchor="middle">n=20 与 n+1=21：各自的最大素因子（深色块）</text>
  <rect x="110" y="76" width="90" height="34" fill="#f0b95a" stroke="#345"/>
  <text x="155" y="98" font-size="15" text-anchor="middle">5</text>
  <rect x="110" y="112" width="90" height="34" fill="#dfe3e8" stroke="#345"/>
  <text x="155" y="134" font-size="15" text-anchor="middle">2</text>
  <rect x="110" y="148" width="90" height="34" fill="#dfe3e8" stroke="#345"/>
  <text x="155" y="170" font-size="15" text-anchor="middle">2</text>
  <line x1="95" y1="184" x2="215" y2="184" stroke="#345"/>
  <text x="155" y="210" font-size="14" text-anchor="middle">n=20</text>
  <text x="155" y="230" font-size="13" text-anchor="middle">P⁺(20)=5</text>
  <rect x="350" y="76" width="90" height="34" fill="#f0b95a" stroke="#345"/>
  <text x="395" y="98" font-size="15" text-anchor="middle">7</text>
  <rect x="350" y="112" width="90" height="34" fill="#dfe3e8" stroke="#345"/>
  <text x="395" y="134" font-size="15" text-anchor="middle">3</text>
  <line x1="335" y1="148" x2="455" y2="148" stroke="#345"/>
  <text x="395" y="174" font-size="14" text-anchor="middle">n+1=21</text>
  <text x="395" y="194" font-size="13" text-anchor="middle">P⁺(21)=7</text>
  <line x1="235" y1="150" x2="330" y2="150" stroke="#889" stroke-dasharray="6,5"/>
  <polygon points="235,150 247,145 247,155" fill="#889"/>
  <polygon points="330,150 318,145 318,155" fill="#889"/>
  <text x="282" y="138" font-size="13" text-anchor="middle">互不影响</text>
  <text x="280" y="262" font-size="14" text-anchor="middle">定理：相邻整数的最大素因子渐近独立，且 P⁺(n)＜P⁺(n+1) 的密度 = 1/2</text>
</svg>

</div>

**为什么值得关心**

这种"邻居互不干扰"在纯随机模型里天经地义，但在确定性的整数世界里证明它极难：此前近五十年人们只得到各种"正下界"或需附加猜想的版本，本文首次无条件地、在所有尺度上给出完整极限律——"相邻整数的因子结构各过各的"从此是定理。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

无条件证明了相邻整数 `@@M@@n@@` 与 `@@M@@n+1@@` 的最大素因子在对数尺度上按自然密度渐近独立、边际均为 Dickman 分布，正面解决 Erdős–Pomerance 联合猜想，并得到 `@@M@@P^+(n)<P^+(n+1)@@` 的密度恰为 1/2。

## 问题背景

设 `@@M@@P^+(n)@@` 为 `@@M@@n@@` 的最大素因子（largest prime factor）。从 Dickman（1930）经 Ramaswami 到 de Bruijn 的经典光滑数（smooth number）理论给出：`@@M@@n\le X@@` 中满足 `@@M@@P^+(n)\le X^a@@` 的比例为 `@@M@@\rho(1/a)@@`，其中 `@@M@@\rho@@` 是 Dickman–de Bruijn 函数。这确定了单个整数的对数光滑性分布。1978 年 Erdős 与 Pomerance 提出联合问题：相邻两整数的最大素因子大小是否渐近独立？他们只证得两种排序的自然下密度为正（显式下界 0.0099）。此后近五十年，下密度记录被逐步推高——de la Bretèche–Pomerance–Tenenbaum 与 Fouvry、Wang、Lü–Wang、直到 Yang 的 0.280——但这些都只是下密度界，不断言密度存在；Teräväinen（2018）在 对数密度 意义下证得乘积律；Tao–Teräväinen（2019、2026）在除去一列零对数密度的例外尺度后得到普通平均；Wang 则需假设 friable 整数版的 Elliott–Halberstam 猜想。卡点正在于：不附任何条件、在所有尺度上取得普通自然密度极限。

## 主要结果

主定理（联合 Dickman 律，joint Dickman law）：对任意固定的 `@@M@@a,b\in(0,1)@@`，

`@@M@@D\lim_{X\to\infty}\frac1X\#\{2\le n\le X:\ P^+(n)\le n^a,\ P^+(n+1)\le n^b\}=\rho(1/a)\,\rho(1/b),@@`

极限沿全体实数 `@@M@@X@@` 以普通无权计数取。等价地说，`@@M@@\log P^+(n)/\log n@@` 与 `@@M@@\log P^+(n+1)/\log n@@` 在自然密度下收敛为独立随机变量，公共分布函数为 `@@M@@D(t)=\rho(1/t)@@`。经容斥还得到上尾独立性（upper-tail independence）：`@@M@@\Pr(P^+(n)>X^c,\ P^+(n+1)>X^d)=(1-D(c))(1-D(d))@@`，即 Erdős–Pomerance 原猜想的形式。推论（比较问题，通常归于 Erdős–Turán）：`@@M@@P^+(n)<P^+(n+1)@@` 与反序的自然密度均为 `@@M@@1/2@@`。因极限律连续、乘积测度在对角线上零质量，由极限律的对称性即得，无需任何定量分离估计。

## 证明思路

全文是"编码—放大—换元—图比较"的反证长链。

先把最大素因子编码为有限组素因子计数：将 `@@M@@(x^{1/J},x]@@` 中的素数分为 `@@M@@J-1@@` 个对数箱 `@@M@@\mathcal B_{k,x}@@`，用完全乘性标签 `@@M@@f_x(n)=\prod_k\zeta_k^{\Omega_{\mathcal B_{k,x}}(n)}@@` 记录各箱计数（`@@M@@\Omega_E@@` 为计入重数的素因子个数），另取独立相位的标签 `@@M@@g_x@@`，中心化为 `@@M@@F_x=f_x-\mu@@`。有限 Fourier 反演把联合律归结为混合去相关：`@@M@@\frac1x\sum_{n<x}\overline{g_x(n)}F_x(n+1)\to0@@`，两套相位可独立选取正是两列计数向量独立的来源。两个支柱性质：其一，固定乘子不变性 `@@M@@F_x(un)=F_x(n)@@`，因为固定 `@@M@@u@@` 的素因子最终都落在箱之外；其二，加权短平均消没：长度 `@@M@@L_B\to\infty@@` 的区间上 `@@M@@F_x(n+i)G_{B,v}(n+i)@@` 的平均在均方意义下趋零。后者先用 Vandermonde 型张量插值把 `@@M@@F_x@@`（只依赖有限个箱计数）写成有限个实非负乘性函数的组合，再对剩余条件用 Dirichlet 特征分解：主特征部分用 Matomäki–Radziwiłł 实数短区间定理比较长平均，非主特征扭转用 Matomäki–Radziwiłł–Tao 复数定理控制，所需特征距离发散由 Vinogradov–Korobov 型 `@@M@@\zeta@@` 上界保证。

再假设混合相关沿某子列不趋于零。在 `@@M@@(0,\infty)\times\widehat{\mathbb Z}@@`（profinite 整数，配 Haar 概率测度）上作紧性提取，得到有界剖面 `@@M@@W(t,w)@@`，并选光滑截断 `@@M@@\phi@@` 使 `@@M@@\beta_*=|\int\phi W|>0@@`。随后构造除子放大器（divisor amplifier）`@@M@@D_B(n)@@`：对分解 `@@M@@n=am@@`、`@@M@@n+1=cl@@`（`@@M@@e^B<c<e^{2B}@@`、`@@M@@Tc<a<2Tc@@`）取非负加权和。通过"每个辅助素数以 `@@M@@1/p@@` 概率入选、再由公平硬币分给系数或余项"的比较模型，配合上界筛导出的加法乘积小球集中估计，证得 `@@M@@D_B@@` 的 Haar 均值不低于某 `@@M@@d_0>0@@` 且 `@@M@@L^2@@` 范数有界；又因 `@@M@@D_B@@` 只依赖趋于无穷的大素数剩余类，而 `@@M@@W@@` 与每个固定剩余坐标渐近独立，放大后的相关积分仍约为 `@@M@@(\int\phi W)(\int D_B)@@`，相关性得以存活。

接着展开 `@@M@@n=am@@`，用乘子不变性把模一因子 `@@M@@g_x(m)@@` 提到内层和之外，Cauchy–Schwarz 将其消去，留下下界为正的二次能量 `@@M@@I_{2,x}\ge c_5BT@@`，其对角项因系数上界 `@@M@@o(T)@@` 而可忽略。非对角项中 `@@M@@c\mid am+1@@` 与 `@@M@@c\mid bm+1@@` 强制 `@@M@@a-b=jc@@`（`@@M@@0<|j|\le T@@`），精确换元 `@@M@@n'=bl_a@@`、`@@M@@n'+j=al_b@@`（`@@M@@l_a=(am+1)/c@@`）把标签乘积化为 `@@M@@\overline{F_x(n')}F_x(n'+j)@@`：能量变成尺度 `@@M@@Tx@@` 上普通加性移位的加权图。

最后把端点处的真实整除集与独立模型集（每个素数以 `@@M@@1/p@@` 入选）耦合，在期望切范数（cut norm）意义下把算术核与端点特征积核比较：特征 `@@M@@V_l@@` 定义为对端点素数集合作公平分裂后 `@@M@@\log b/B@@` 落入粗网格胞的条件概率；用 Fourier 检测方程 `@@M@@a-b=jc@@`，把滞后 `@@M@@j@@` 的奇性级数（singular series）与光滑滞后因子同端点分离，核近似为 `@@M@@\sum_l c_{l,B}(j,s)V_l(S_i)V_l(S_k)@@`，再借 Frieze–Kannan 型列采样把比较升级到切范数。收尾时以多项式逼近把 `@@M@@V_l@@` 表为 `@@M@@G_{B,v}(n)=\prod_{p\mid n}(1+p^{-v/B})/2@@` 的有限组合，把奇性级数换成周期函数，并把位置块细分为长度不超过 `@@M@@\delta T@@` 的小块：能量于是分解为前述短平均的乘积，而短平均消没，与正能量矛盾。由于坏子列任意抽取，全序列极限成立。末节从阶乘矩与延迟方程 `@@M@@uH'(u)=-H(u-1)@@` 识别出 Dickman 边际 `@@M@@H=\rho@@`，经挤压论证从固定阈值 `@@M@@X^c@@` 过渡到移动阈值 `@@M@@n^a@@`，并由乘积极限律的对称性导出排序推论。

## 可信度与备注

本篇是结果族 012 的唯一手稿，主结果暂无 Lean 形式化证明（族描述中的 Lean 链接属族级文档，不覆盖该定理），请以社区核验为准。论文技术自足，除子放大与素数整除图在 Tao、Helfgott–Radziwiłł、Pilatte、Tao–Teräväinen 等工作中有明确先例，而本文的粗糙除子图与端点核比较系局部新证。按 OpenAI 官方声明，未经形式化的结果可能存在问题，最终可信度有赖同行评议与独立复核。

{% endraw %}
