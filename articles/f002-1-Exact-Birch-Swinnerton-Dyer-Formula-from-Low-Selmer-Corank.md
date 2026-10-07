---
layout: default
title: "Exact Birch–Swinnerton-Dyer Formula from Low Selmer Corank"
family: "002"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Exact Birch–Swinnerton-Dyer Formula from Low Selmer Corank

> 结果族 002：The full BSD formula from low Selmer corank　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对 \(\Q\) 上任意椭圆曲线，只要某个素数 \(q\) 处的全 \(q\)-幂 Selmer 群余秩为 \(0\) 或 \(1\)，就证明了解析秩与 Mordell–Weil 秩都等于该余秩、Tate–Shafarevich 群有限，且含全部素因子的完全 BSD 首项公式无条件成立。

## 问题背景

BSD 猜想（Birch–Swinnerton-Dyer conjecture）断言：椭圆曲线 \(L\)-函数在中心点 \(s=1\) 的首非零泰勒系数由实周期、Mordell–Weil 群的高差体积（regulator）、Tamagawa 数（Tamagawa number）、挠子群与 Tate–Shafarevich 群之阶共同给出。Gross–Zagier 公式与 Kolyvagin 欧拉系统早已给出解析秩至多一时的秩等式与 \(\Sha\) 有限性，但零点阶数加有限性并不能确定首项系数本身：还需逐素数比较整系数信息，这就是"积分 BSD"难题。此前的整系数结果——Rubin 的 CM 主猜想、Kato 的 zeta 元素、Skinner–Urban、Jetchev–Skinner–Wan 等——都附加剩余表示不可约、半稳定或好约化等条件，无法对所有曲线、所有素数同时给出精确公式。本文以"某个全 Selmer 群余秩低"为唯一门槛，去掉了全部附加假设。

## 主要结果

设 \(\Sel_{p^\infty}(E/\Q)\) 为全 \(p\)-幂 Selmer 群（Selmer group），记 \(s_q(E)=\corank_{\Z_q}\Sel_{q^\infty}(E/\Q)\)，\(a(E)=\ord_{s=1}L(E,s)\)，\(r(E)=\rank E(\Q)\)。主定理（定理 1.1）：若对某素数 \(q\) 有 \(s_q(E)\in\{0,1\}\)，则
\[r(E)=a(E)=s_q(E),\qquad \#\Sha(E/\Q)<\infty,\]
且以含两个实连通分支的周期 \(\Omega_E\)、全格 \(\Reg_E\)、全部有限素处的分量数 \(c_\ell(E)\) 归一化后，
\[\frac{L^{(r)}(E,1)}{r!}=\frac{\Omega_E\,\Reg_E\,\#\Sha(E/\Q)\prod_{\ell}c_\ell(E)}{\#E(\Q)_{\rm tors}^{2}}.\]
公式对约化类型、有理挠子群、同源、复乘（complex multiplication）与剩余伽罗瓦表示均无附加假设。秩与有限性部分由同族"Selmer 逆定理"篇供给，\(2\)-进部分由"二进 BSD"篇供给，本文新证的是一切奇素数处的精确赋值。

## 证明思路

固定奇素数 \(p\)，令 \(Q_E\) 为把上式右边移到左边后的归一化商，定义偏差 \(X_p(E)=v_p(Q_E)-v_p(\#\Sha(E/\Q))\)，目标是在每个奇素数处证明 \(X_p(E)=0\)。证明拆成两个互补输出。

第一步（第 5 节）证单边不等式：非复乘曲线若 \(a(E)\le1\) 则 \(X_p(E)\ge0\)。先按 Kato 的构造，在带独立挠点的模曲线 \(Y(n_1,n_2)\) 上用他的 Siegel 型单元函数造出整体上同调类，经相对上同调的整格引理推入 \(T_pE\) 系数的伽罗瓦上同调；这些类活在整环 \(R=\Z_p[[t,u_1,\dots,u_m]]\) 上的有限自由复形模型里，\(t\) 为分圆变量，\(u_i\) 为"移动素数"引入的驯顺变量。再用 Chebotarev 选取 Frobenius 趋于幂单矩阵的辅助素数，以欧拉系统导子类做"线性切换"，证得归一化行列式坐标 \(U\in R\)。中心值的识别分两种情形：秩零用对偶指数映射与周期公式（坐标正比于 \(L(f,\nu,1)/\Omega_0\)）；秩一用一条精确的驯顺高差（tame height）对数比较，配合谱恒等式与 Gross–Zagier 公式完成。最后由整 Poitou–Tate 正合列逐项装配，被省略的 Euler 因子恰与局部 Haar 恒等式抵消，得 \(X_p(E)=v_p(U(0))\ge0\)。

第二步（第 6–10 节）证配对恒等式。用挠曲线密度定理选虚二次域 \(K=\Q(\sqrt D)\)，使 \(E\) 与其虚二次挠 \(E^D\) 的解析秩互补（和为 1）。设 \(p=w\bar w\) 在 \(K\) 中分裂，令 \(L_w\) 为"\(w\) 处取严格零条件、\(\bar w\) 处取全条件"的 Selmer 复形之行列式，\(B_w\) 为由普通（ordinary）模曲线上构造的整对数原函数沿环类域 CM 点做类群求和所得的有界解析级数，商 \(U_w=B_w/L_w\)。先在高特征标处做局部比较与水平切换证可除性，经 Weierstrass 除法得 \(U_w\in R\)；再以 Chai–Hida 刚性定理与 Zarhin 同源定理导出的单塑性（monodromy）论证证 \(p\nmid B_w\)。剩余的水平因子由 \(\theta\) 级数排除：在特征零除子处，\(\theta\) 级数与尖点形式的比较产生满足单边严格条件的非零上同调类，配合非增广特征测试与乘积特征论证，证得两个商的主理想相等；继而添加足够多的新驯顺变量，使可能的同时严格跳跃余维至少为 2，而商的除子余维只能为 1，故无除子残留，\(U_w\) 成为单位。最后第 10 节在中心点计算严格复形的行列式体积，得到把 Heegner 点指标、挠群与全部 Tamagawa 数装配起来的精确等式，代入由限制纯量分解 \(\mathrm{Res}_{K/\Q}E\sim E\times E^D\) 与 Gross–Zagier 高度公式导出的实恒等式，得 \(X_p(E)+X_p(E^D)=0\)。两个非负数之和为零，故 \(X_p(E)=0\)；复乘曲线秩零时援引 Burungale–Flach 定理，秩一经配对归结为秩零。于是 \(Q_E/\#\Sha\) 是所有素数处赋值皆零的正有理数，只能等于 1，公式得证。

## 可信度与备注

本文主结果暂无形式化证明，请以社区核验为准。它与同族两篇姊妹篇互相咬合："Selmer 逆定理"篇提供任意素数处低余秩的秩等式与 \(\Sha\) 有限性，"二进 BSD"篇提供 \(p=2\) 的首项等式，本文补齐全部奇素数，三者相加才是完整公式；再配合 Selmer 分布的密度结果，可对每条固定曲线的密度一二次挠族给出完全 BSD。作者也强调低 Selmer 余秩假设不可简单换成 Mordell–Weil 秩假设。按 OpenAI 官方声明，未经形式化的结果可能有问题，且本文论证链条极长，宜以社区核验为准。

{% endraw %}
