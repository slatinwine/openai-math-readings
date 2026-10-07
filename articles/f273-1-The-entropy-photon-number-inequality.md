---
layout: default
title: "The entropy photon-number inequality"
family: "273"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The entropy photon-number inequality

> 结果族 273：The entropy photon-number inequality　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明 Guha–Erkmen–Shapiro 2007 年提出的熵光子数不等式：分束器混合两个独立有限能量输入后，输出的熵光子数不小于两输入按透射率加权的平均，允许输入内部任意多模纠缠；并据此确定热衰减信道的精确最小输出熵与纯损耗广播信道的容量域。

## 问题背景

一个 \(n\) 模玻色态（bosonic state）的熵光子数（entropy photon number），指与它总熵相同的 \(n\) 个全同单模热态（thermal state）乘积的每模平均光子数，即 \(g^{-1}(S(\rho)/n)\)，其中 \(S\) 为冯·诺依曼熵（von Neumann entropy），\(g(t)=(t+1)\log(t+1)-t\log t\) 是平均光子数为 \(t\) 的热态的熵。2007 年 Guha、Erkmen 与 Shapiro 猜想：两个独立输入经分束器（beam splitter）混合后，该量满足凹性不等式。它是经典熵功率不等式（entropy power inequality）的量子对应，关系玻色信道（bosonic channel）的最小输出熵与容量。此前的线性熵下界（König–Smith）与指数熵功率下界（De Palma–Mari–Giovannetti）只在两输入熵相等时够用；高斯输入情形已知，但允许模间任意纠缠（entanglement）的一般输入悬而未决。

## 主要结果

**主定理（EPnI）**：设 \(\rho_A,\rho_B\) 为 \(n\) 模、平均能量有限的状态，\(\rho_C\) 为按 \(c_j=\sqrt\eta\,a_j+\sqrt{1-\eta}\,b_j\) 以透射率 \(\eta\) 被动混合后的输出，则
\[g^{-1}\!\Big(\frac{S(\rho_C)}{n}\Big)\ge\eta\,g^{-1}\!\Big(\frac{S(\rho_A)}{n}\Big)+(1-\eta)\,g^{-1}\!\Big(\frac{S(\rho_B)}{n}\Big).\]
对输入内部模间结构零假设：允许任意纠缠，不必高斯；每端口内部全同的热态乘积取等，两端口熵值还可不同。**推论一**：\(n\) 模热衰减器（thermal attenuator）\(\mathcal E_{\eta,N_B}^{\otimes n}\) 在固定输入熵 \(S(\rho)=ns\) 时，最小输出熵恰为 \(n\,g(\eta g^{-1}(s)+(1-\eta)N_B)\)，由热态乘积达到。**推论二**：退化（degraded）双接收者纯损耗广播信道在平均光子约束 \(\bar N\) 下的容量域，是满足 \(R_B\le g(\eta_B\beta\bar N)\)、\(R_C\le g(\eta_C\bar N)-g(\eta_C\beta\bar N)\)（\(0\le\beta\le1\)）的速率对的闭凸包。

## 证明思路

全文用反证法，骨架为"正则化极小化—二阶估计—生成元恒等式—热态极限"。先设存在严格反例，经数截断逼近换成有限光子数支撑的见证对，并在其熵水平附近固定热参考参数 \(r_1,r_2\)。再引入三重辅助结构：固定热端口、输出按比例 \(\kappa\) 替换为参考热态、相对熵（relative entropy）惩罚 \(\varepsilon D(\rho_i\Vert\tau_{r_i})\) 与四阶矩惩罚 \(\zeta\Tr\rho_iW_i^4\)，得到以"线性化光子尺度"\((S-ng(r))/h(r)\)（\(h=g'\)）为单位的泛函 \(J_\zeta\)。熵随能量至多对数增长，故能量惩罚保证强制性（coercivity），泛函取到严格负最小值；Gibbs 正则性引理表明最小点是 \(e^{-(kW^4+\cdots)}\) 型 Gibbs 态（忠实、七阶矩有限），并满足对数恒等式：输入对数=输出对数的条件切片+惩罚项+常数。

对最小点做二阶分析：一次只变动一个输入，相对熵展开抵消全部一次项，再经 Gibbs 变分原理配中心化输出观测，得切片映射在以对数平均（logarithmic mean）\(\ell(p_l,p_r)\) 为权的 Bogoliubov–Kubo–Mori 度量下的压缩。第 4 节把两个乘积端口方差估计与这些分量压缩拼合，恰好凑成插值定理的四条假设（该节技术性较强，此处按论文引言概括）：权为 \(mf(x)e^{\pm x}\)、\(mf(y)e^{\pm y}\)（\(f=x/\sinh x\)）的四组对角二次型（diagonal quadratic form）比较，蕴含权 \(mf(x)f(y)/f(x+y)\) 的比较，解析核心是 \(B(f(x)^2)=x\coth x\) 导数的 Stieltjes 表示（经 Herglotz 定理）；结论控制"中心化热平衡缺陷"（产生–湮灭平衡的偏差泛函）的范数。最后配热弛豫生成元（量子 Ornstein–Uhlenbeck 生成元，零化热态）：协方差恒等式缝合三端口，与 Gibbs 恒等式配对后中心化能量项严格相消，得 \(0=\|q_0\|^2-(1+\varepsilon)A_*^2-\varepsilon M_*^2-\kappa(1-\kappa)|\mu_\gamma|^2+\zeta P\)，于是 \(0\le-\tfrac\varepsilon2(A_*^2+M_*^2)+C\zeta\)。令 \(\zeta\to0\)，缺陷与均值趋于零，数基递推 \((r_i+1)\,d\,\hat\rho_i=r_i\,\hat\rho_i\,d\) 逼出极限必为热态，熵连续性使目标值趋于零，与负的最小值矛盾。

## 可信度与备注

主结果暂无 Lean 形式化证明，请以社区核验为准；按 OpenAI 官方声明，未经形式化的结果可能有问题。插值定理、Gibbs 正则化与极限过渡等专门引理均在文内证明；本批仅此一篇，两个推论均由主定理直接导出：广播容量域反界正是用 EPnI 的真空端口特例，补齐 Guha–Shapiro–Erkmen 2007 年分析所缺的熵输入。本解读核对了六个章节；未细读的第 4 节按论文引言概括转述。

{% endraw %}
