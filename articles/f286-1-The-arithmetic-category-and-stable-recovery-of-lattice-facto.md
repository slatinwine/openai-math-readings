---
layout: default
title: "The arithmetic category and stable recovery of lattice factors"
family: "286"
discipline: "Operator algebras"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The arithmetic category and stable recovery of lattice factors

> 结果族 286：Rigidity and arithmetic of lattice von Neumann algebras　·　学科：Operator algebras　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明格点扭群因子的"稳定典范恢复"：稳定同构强迫放大尺度相等，并恢复群、cocycle 与映射本身（相差共轭与上链）；此类因子基本群平凡，且一切有限对应的映射级演算被完整算出。

## 问题背景

群因子同构不必保持群单位向量，Connes 与 Popa 的重构问题由此而来（背景详见姊妹篇解读）。此前的障碍在于：姊妹篇的穷尽定理只说对应被初等模型覆盖，并未识别全部闭和项与有界交缠子；要把几何输入变成"恢复群与映射"的定理，还需要一套完整的对应范畴 (correspondence category) 演算。Cowling–Haagerup 不变量只能从因子读出 \(\Sp(n,1)\) 型格点的参数；Vaes、Donvil–Vaes 与 CFOT 分别在广义 Bernoulli、左右 wreath 积与 wreath-like 群类中建立过类似分类，但局部域格点类加上任意源 cocycle 的情形此前空缺。

## 主要结果

沿用姊妹篇的类 \(\mathscr K\)（与特征零局部域半单群乘积中性质 (T) 格子抽象交换的 ICC 群）。定理一（稳定典范恢复）：对 \(\Lambda\in\mathscr K\)、任意可数 ICC 群 \(\Pi\) 与任意正规标量 cocycle \(\omega,\nu\)，有 \(L_\omega(\Lambda)^t\cong L_\nu(\Pi)^s\)（\(t,s>0\) 为放大尺度）当且仅当 \(t=s\)，且存在群同构 \(\delta:\Lambda\to\Pi\) 与正规上链 (cochain) \(b\) 使 \(\omega(g,h)=b(g)b(h)b(gh)^{-1}\nu(\delta g,\delta h)\)；给定的同构在矩阵角上必形如 \(\theta(x)=z\varphi^{(n)}(x)z^*\)，其中 \(\varphi(u_g)=b(g)v_{\delta(g)}\)，\(z\) 为实现偏等距。特别地，此类因子的基本群 (fundamental group) 平凡，且被比较群 \(\Pi\) 也必落回 \(\mathscr K\)。定理二（全部因子端点）：可分 \(\mathrm{II}_1\) 因子 \(P\) 与 \(L_\mu(\Gamma)\) 存在非零双有限对应，当且仅当 \(P\cong L_\omega(\Lambda)^t\)，其中 \(\Lambda\in\mathscr K\)，且匹配的子群同构上 cocycle 比值 \(\mu|_A/\delta^*\omega|_B\) 容许非零有限维射影表示。定理三（全部有限对应）：每个对应有到"全芽轨道丛" \(H(d,\sigma_d)\) 的有限正交分解（\(d\) 是虚同构芽 (virtual-isomorphism germ)，\(\sigma_d\) 是其全稳定化子上关于联合乘子 \(\alpha\) 的有限维射影表示），全部有界双模映射逐纤维为 \(\oplus_d\Hom_{C_d,\alpha}(\sigma_d,\tau_d)\)，两个模维数恒为正整数；共轭与 Connes 融合 (Connes fusion) 对应于双陪集诱导。推论包括 \(\operatorname{Out}(L(\Gamma))\cong\Hom(\Gamma,\mathbb T)\rtimes\operatorname{Out}(\Gamma)\)、唯一迹条件下从约化 C*-代数恢复群，以及 \(L(\mathrm{SL}_3(\mathbb Z))\) 的有限指标 *-自同态必满射。

## 证明思路

代数演算分三步。第一步建立映射级分类：图模型按陪集分解为正交的有限维纤维，具有同一虚同构芽的纤维必须先归组——全稳定化子在芽空间只有一个有限轨道，而有界交缠子的每一列平方可和，迫使映射保持每个归组纤维；由此得到 Hom 公式，并使两个模维数成为"纤维维数乘子群指标"的整数和。第二步恢复未知因子：双有限对应先经交换子实现为有限指标扩张 \(M\subset Q=P^r\)；算术穷尽把 \(L^2(Q)\) 按芽分次为子空间 \(K_d\)。关键一击是 Pimsner–Popa 有限指标不等式：对 \(\xi\in K_d\) 的平方做谱截断并单调收敛，证得 \(K_d\) 全由有界算子组成，且乘法满足 \(K_dK_f\subset K_{df}\)——分次与真实乘法相容。恒等次 \(K_1\) 是有限维单位 *-代数；取其极小投影压缩角 \(pQp\)，每个非零次 \(pK_dp\) 成为一维酉线，这些线的乘法系数定义出群 \(\Lambda\) 与 cocycle \(\omega\)，使 \(pQp\cong L_\omega(\Lambda)\)；恒等矩阵块给出 cocycle 比值的射影表示，芽的论证再证 \(\Lambda\) 含有限指标子群同构于 \(\Gamma\) 的子群且为 ICC。第三步处理稳定同构：其等价对应的双维数互倒 \((t/s,s/t)\)，而定理三断言它们是正整数，故同为 \(1\)——放大尺度相等、只剩一条全图与一维纤维，纤维正给出上链 \(b\)；最后在给定矩阵角中比较投影得到矩形偏等距 \(z\)，对应识别把 \(z\) 校正为所给映射的实现。\(L(\mathrm{SL}_3(\mathbb Z))\) 的满射性另需 Prasad 强刚性加经典协体积论证：有限指标像格点与原格点在 \(\mathrm{SL}_3(\mathbb R)\) 中同协体积，故指标必为 \(1\)。

## 可信度与备注

本文暂无形式化证明，按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。本文的模型演算部分不依赖几何输入，但恢复类定理以姊妹篇的算术穷尽定理为前提，两文合成完整链条；方法上改造了 Vaes 的射影诱导演算与 Donvil–Vaes 的齐次积—极小角构造。文中亦自陈这些是结构性分类，并不给出对任意群表示或 cocycle 类的判定程序。

{% endraw %}
