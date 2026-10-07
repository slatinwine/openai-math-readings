---
layout: default
title: "Prime Predecessors with an Even Number of Prime Factors"
family: "011"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Prime Predecessors with an Even Number of Prime Factors

> 结果族 011：Prime-factor statistics of `@@M@@p-1@@`　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明有无穷多个素数 `@@M@@p@@` 使 `@@M@@p-1@@` 无平方因子且素因子个数（计入重数）为偶数，等价地 `@@M@@\mu(p-1)=1@@` 无穷多次成立——素数前一项的奇偶性问题由此获得肯定回答。

## 问题背景

设 `@@M@@\Omega(n)@@` 计入重数地数素因子个数，`@@M@@\omega(n)@@` 只数不同素因子。筛法有一个先天的软肋——奇偶性问题（parity problem）：仅凭同余信息驱动的筛法原则上分不清一个数的素因子个数是偶还是奇，即区分不了两种 Liouville 符号。Friedlander 与 Iwaniec 的渐近筛（asymptotic sieve）表明，补充足够强的双线性（Type II）信息后这道障碍可以绕过，他们据此找到了 `@@M@@x^2+y^4@@` 型素数。对素数前一项施加乘法限制，已有 Baker–Harman、Lichtman 关于光滑移位素数（smooth shifted primes）的工作，但奇偶性是另一类限制，不能由光滑性推出。而"`@@M@@p-1@@` 有偶数个素因子且 `@@M@@p@@` 本身是素数"两头都撞在奇偶障碍上；本文对此给出肯定回答。

## 主要结果

主定理：存在无穷多个素数 `@@M@@p@@`，使 `@@M@@p-1@@` 无平方因子（squarefree）且 `@@M@@\Omega(p-1)@@` 为偶数；等价地，Möbius 函数（Möbius function）满足 `@@M@@\mu(p-1)=1@@` 的素数有无穷多个。无平方条件并非装饰：它消除 `@@M@@\Omega@@` 与 `@@M@@\omega@@` 两种计数约定的歧义，使结论在两种意义下同时成立。做法上写 `@@M@@p=2u+1@@`，在奇数 `@@M@@u@@` 上构造非负权 `@@M@@A(u)@@`：凡 `@@M@@A(u)>0@@` 的 `@@M@@u@@` 必有 `@@M@@\Omega(u)@@` 为奇数，从而 `@@M@@\Omega(2u)=1+\Omega(u)@@` 为偶数；再证明这些权中确有使 `@@M@@2u+1@@` 为素数的质量，且 `@@M@@2u@@` 不无平方的部分质量可忽略。

## 证明思路

整个证明是"先造权、再补两个解析引理、最后过筛抽取素数"的三段式。

先造权（第 4 节）。把构造用的素数按对数尺度分成两类：一类是几何衰减的普通带 `@@M@@Q_j@@`，每个被支撑的 `@@M@@u@@` 在每个带恰好占 `@@M@@r_0@@` 个素数槽，`@@M@@r_0@@` 取偶数，故普通部分的素因子个数恒为偶数；另一类是少数小素数群 `@@M@@\mathcal P_g@@`，其上放置带标记的权 `@@M@@W_1@@`，并用群素数的 Liouville 符号 `@@M@@\mathcal E(u)=(-1)^{\sum_{p\in\mathcal P}v_p(u)}@@` 做投影 `@@M@@A(u)=A_0(u)(1-\mathcal E(u))/2@@`，只保留群部分重数为奇的 `@@M@@u@@`。两厢相加，凡被支撑则 `@@M@@\Omega(u)@@` 为奇。权的总质量 `@@M@@X_A\asymp(x/L)H_QH_P\gg xL^{-C_A}@@`，含平方因子的事件概率仅 `@@M@@O(TL^{-20})@@`。

再补两个新引理，这是超出姊妹篇的部分。其一，长素数多项式（第 2 节）：在 `@@M@@L^{B_0}\le|t|\le x^2@@` 的一切高对数高度上一致地有 `@@M@@\sum_{p\in I}\chi(p)p^{-1+it}\ll L^{-A}@@`。证明链条是：先证次数一致、带双指数常数的 Vinogradov 均值估计（Linnik 的 `@@M@@p@@`-adic 迭代），推出等差数列上对数相位的衰减；经 Jensen 公式与三角恒等式 `@@M@@3+4\cos\theta+\cos2\theta\ge0@@` 建立高达 `@@M@@x^3@@` 高度的零点自由带（zero-free strip）`@@M@@\operatorname{Re}s\ge1-cT^2/L@@`；最后 Mellin 反演移围道收割。其二，公共符号的素数槽相关（第 3 节）：允许相关和的长槽里放素数（姊妹篇只放粗整数），且两端挂同一个完全乘性符号 `@@M@@\varepsilon@@`。核心恒等式是 `@@M@@\varepsilon(D_Rw)\varepsilon(D_Rw')=\varepsilon(D_R)^2\varepsilon(w)\varepsilon(w')=\varepsilon(w)\varepsilon(w')@@`：共享膨胀因子的符号因完全乘性而平方消失，膨胀图的图传递（transference）论证因此能原样保留奇偶敏感的权。剩余比较项按大弧—小弧分治：小弧用一个整数双线性估计；大弧上取一个小群标记、展开有理特征，化为局部 Fourier 能量，其中例外时刻的稀疏性由 `@@M@@P_s^{j_0}@@` 的阶乘系数范数与唯一分解给出，高频率交给长素数多项式、低频率交给系数序列的特征–Mellin 差值假设。

最后过筛（第 5–7 节）。相关估计先升级为 Type II 定理：满足差值假设的序列 `@@M@@\alpha@@` 给出 `@@M@@\sum_{mn=2u+1}\alpha_m\beta_nA(u)\Psi(u/x)\ll xL^{-D_*}@@`，对 `@@M@@\beta@@` 不设条件；同余分布定理则控制过筛剩余项。对 `@@M@@N_u=2u+1@@` 过三关：分块筛（block sieve）预筛掉 `@@M@@x^{b_1}@@` 以下的小素因子，留下质量 `@@M@@\gg\mathfrak SX_A/(b_1L)@@`；失衡合数借有界代理（proxy）与密度函数 `@@M@@D_\gamma@@` 减除；平衡半素数（semiprime）由代理加一个纯计数的双线性对界压至 `@@M@@C_{\mathrm{bal}}\kappa\,X_A/L@@`。取 `@@M@@\kappa@@` 使 `@@M@@C_{\mathrm{bal}}\kappa<\mathfrak S/4@@`，剩余素数质量 `@@M@@\ge(\mathfrak S/2-C_{\mathrm{bal}}\kappa-o(1))X_A/L\gg X_A/L@@`，其中 `@@M@@\mathfrak S@@` 为孪生素数常数（twin prime constant）。

## 可信度与备注

主结果暂无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。本文大量引用同族姊妹篇《Weighted dilation graphs, smooth shifted primes and totient fibers》的膨胀图传递、理想核、分块筛与代理估计，只引用不重证；其独有贡献是"长槽容许素数"与"两端同号"两项扩展，恰是推出奇偶结论所缺的拼图。同族另两篇分别证明 Ford–Konyagin–Luca 猜想（`@@M@@p-1@@` 素因子的 Poisson–Dirichlet 极限律）与 Erdős 的欧拉 `@@M@@\varphi@@` 函数纤维猜想，三篇共享同一套筛法机器、互相支撑。文中所有辅助常数都在 `@@M@@x\to\infty@@` 之前固定，参数选取次序亦有显式交代，便于逐项核查。

{% endraw %}
