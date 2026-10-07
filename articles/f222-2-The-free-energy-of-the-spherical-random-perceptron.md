---
layout: default
title: "The free energy of the spherical random perceptron"
family: "222"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The free energy of the spherical random perceptron

> 结果族 222：Perceptron free energies and microscopic jamming exponents　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文对球面随机感知机（spherical random perceptron）证明了极限压强的精确变分公式：任意正密度与逆温度下，压强收敛于"α×单模式控制值＋球面熵"的下确界，且对任意有界连续势不加凸性或对称性假设。

## 问题背景

感知机（perceptron）是最简的随机模式储存模型。Gardner 1988 年开创用统计力学研究随机约束下权重空间体积的方向；球面版本把权重限制在半径 \(\sqrt N\) 的球面上，约束由 \(M_N=\lfloor\alpha N\rfloor\) 个独立高斯模式给出，\(\alpha\) 为模式密度（pattern density），\(\beta\) 为逆温度（inverse temperature）。核心问题是压强（配分函数对数的极限）有无精确变分描述。Györgyi 与 Reimann 在 2000 年给出连续副本对称破缺（replica-symmetry breaking）预测，其方程恰对应本文公式的两项；严格结果此前仅有 Shcherbina–Tirozzi 对非负间隔、存储阈值以下可行体积的公式。卡壳根源：模式虽是高斯量，经非线性势 \(\phi\) 求和后却不是 \(x\) 的高斯过程，自旋玻璃的现成压强公式无法套用；任意 \(\phi\) 又无比较插值所需的凸性。

## 主要结果

**定理 1**：对任意 \(\alpha,\beta>0\) 与任意有界连续函数 \(\phi\in C_b(\mathbb R;\mathbb R)\)，压强

\[p_N=\frac1N\log\int_{S_N}e^{\beta H_N(x)}\,d\sigma_N(x),\qquad H_N(x)=\sum_{a=1}^{M_N}\phi\Big(\frac{g^a\cdot x}{\sqrt N}\Big)\]

在期望与依概率两种意义下都收敛到同一极限

\[\mathcal P(\alpha,\beta,\phi)=\inf_{m\in\U}\big\{\alpha V_{\beta\phi}(m)+S(m)\big\}.\]

这里 \(\U\) 是全体非降可测函数 \(m:[0,1]\to[0,1]\)（Parisi 型序参数，order parameter）；熵项 \(S(m)=\frac12\int_0^1\big(\frac1{D_m(t)}-\frac1{1-t}\big)\,dt\)（\(D_m(t)=\int_t^1m\)）是 Crisanti–Sommers 型球面熵（spherical entropy）的严格化；\(V_f(m)\) 是一个随机控制（stochastic control）值：在标准布朗运动上取循序可测控制 \(v\)，最大化 \(\mathbb E[f(B_1+\int_0^1m v)-\frac12\int_0^1m v^2]\)。熵为无穷的试探函数值为 \(+\infty\)，且不要求 \(m\) 在 \(1\) 附近取值 \(1\)。作为合理性检验：常值势 \(\phi\equiv c\) 时初等上下界 \(\alpha\mathbb E f(G)\le\mathcal P\le\alpha\log\mathbb E e^{f(G)}\) 重合于 \(\alpha\beta c\)，与公式一致。

## 证明思路

证明用两类增量上下夹逼变分公式：加一个随机模式（上界）、加一批自旋坐标（下界）。先做准备：用 Ruelle 级联（cascade）编码极限重叠律（overlap law）；把"加入一个新模式"的配分增量精确算成控制值 \(V\)——核心是倒向 Parisi 型方程 \(\partial_tU+\frac12\partial_{xx}U+\frac{m(t)}2(\partial_xU)^2=0\)（终值 \(U(1)=f\)），经 Boué–Dupuis 变分表示，级联积分恰与控制问题等值；继而证明尾序性质：若 \(p\) 的尾积分处处不小于 \(q\)，则 \(V(p)\le V(q)\)。再计算球面上带级联高斯场的线性场配分，得熵项 \(S\) 的对偶公式，其在重叠一致有界于 \(B<1\) 的类上一致收敛，供空腔趋于无穷使用。

上界采用 Mourrat 的接触点论证：把模式数泊松化、以密度为时间，构造带级联场与扰动的目标泛函并取最小。最小点处的曲率界与集中现象强制 Ghirlanda–Guerra 恒等式逐点成立；经同步化（synchronization），自旋与标签重叠单调耦合，真实重叠律的尾积分从而被试探 \(q\) 控制，尾序性质给出 \(V(p)\le V(q)\)，而时间方向导数又给出反向不等式，矛盾即得上界。

下界用 Aizenman–Sims–Starr 式固定块空腔（cavity）方法：先抹去两个模式、再作为独立标记恢复，由一、二阶矩知新坐标所受场的协方差是自旋重叠的确定性函数 \(a(R_{\ell j})\)；球面上的切向散度积分给出 Wronskian 型恒等式，解出 \(a\) 恰为球面熵的平稳场 \(A_q(r)=\int_0^r dt/D_q(t)^2\)，且重叠律支撑一致小于 \(1\)。最后把维数 \(N+L\) 与 \(N\) 的配分差写成空腔增量，按模 \(L\) 剩余类裂项求和，先令 \(N\to\infty\)、再令 \(L\to\infty\)，得变分下界。收尾从光滑势逼近到一般有界连续势，并用有界差分不等式得 \(\operatorname{Var}(p_N)=O(1/N)\)，完成依概率收敛。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，请以社区核验为准。论文与 Montanari–Zhou（2024）附录 B 的副本计算有规范化对照（\(\alpha\beta A=\alpha\Psi(0,0)+S(m)\)），与 Györgyi–Reimann 2000 年的物理预测吻合。本文是结果族 222"感知机自由能与微观阻塞指数"的球面分支，族内 Ising 感知机自由能、双正交不变无序推广及 margin \(-1\) 阻塞（jamming）阈值、gap 与力律等姊妹篇共享这套变分框架。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
