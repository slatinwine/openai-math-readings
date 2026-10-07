---
layout: default
title: "Two limit cycles for quintic Liénard systems"
family: "143"
discipline: "Dynamical systems and ergodic theory"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Two limit cycles for quintic Liénard systems

> 结果族 143：Hilbert's sixteenth problem: uniform bounds for limit cycles　·　学科：Dynamical systems and ergodic theory　·　验证状态：主结果已 Lean 形式化

## 一句话结论

对经典 Liénard 系统 \(\dot x=y-F(x)\)、\(\dot y=-x\)，当 \(F\) 是次数至多 5 的实多项式时，系统至多有两个几何上不同的孤立周期轨道，且该界可以达到——精确最大值就是 2。这证明了 Lins Neto–de Melo–Pugh 猜想的五次情形。

## 问题背景

经典 Liénard 系统等价于标量方程 \(x''+F'(x)x'+x=0\)：阻尼项由多项式 \(F'(x)\) 给出，回复力恰为 \(x\)，因此长期被视为希尔伯特第十六问题第二部分中最著名、兼具简单性与代表性的试验场。1977 年 Lins Neto、de Melo 与 Pugh 猜想：\(\deg F=n\) 时极限环（limit cycle）至多 \(\lfloor(n-1)/2\rfloor\) 个。Rychkov 证明了奇五次原函数（odd primitive）的情形；此后 Dumortier–Panazzolo–Roussarie 在 7 次造出 4 个环，De Maesschalck–Dumortier 在 6 次造出 4 个环，De Maesschalck–Huzak 更在每个 \(n\ge6\) 造出至少 \(n-2\) 个环——猜想在 6 次及以上被推翻，唯独 5 次悬而未决。此前已知 Li–Llibre 的 4 次界为 1，Li–Lu 的结果只覆盖非退化慢-快（slow–fast）环的极限体制。论文还顺带澄清：Hernández Rosales 提议的五次 4 环例子经换元后恰是 Odani 的例子，实际只有两个环，其振幅计算有误。

## 主要结果

定理：若 \(\deg F\le5\)，则系统在全平面至多有两个极限环；类中存在恰有两个极限环的成员，故精确最大值为 2。证明对 \(F\) 不设奇偶性、系数符号或环振幅的限制，几何像只计一次；退化（多重、非双曲）环被直接计数，不借助通用扰动移除。由于 \(\lfloor(5-1)/2\rfloor=2\) 而反例从 6 次才开始，五次正是 Lins Neto–de Melo–Pugh 猜想的最后决胜点，本文给出肯定回答。

## 证明思路

上界证明采用"逐半轨比较"。偶次系数阻止化归到奇五次族，小振幅计算又管不住远处的环，于是在每个半平面令 \(u=x^2/2\)，把轨道改写成满足 \(u_y=\phi_\pm(u)-y\) 的拱，其中 \(\phi_\pm(u)=F(\pm\sqrt{2u})=d_0u+b_0u^2\pm p(u)\)，\(p(u)=eu^{1/2}+cu^{3/2}+au^{5/2}\)：偶系数给出两个剖面的公共二次部分，奇部分只变号。以二次剖面 \(q_{\lambda,\kappa}(u)=\lambda u+\kappa u^2/2\) 为比较族。先证全局插值定理：每个容许的中点数据 \((M,M_r)\)（\(r\) 为半宽）在 \(r>0\)、\(|M|<r\)、\(|M_r|<1\) 内被 \((\lambda,\kappa)\) 唯一拟合，且 Jacobi 行列式非零。拟合参数沿拱满足两条输运方程，其系数是二次中点函数的导数；核心的模型不等式 \((R/G)_r\le0\) 把符号控制化归为量 \(\mathcal W=RS_r-SR_r\) 的符号传输：小宽度展开提供初值，端点恒等式与 Riccati 线性化排除可能的零点，其证明还用到 Schwarzian 导数恒等式。沿拱输运后，\(\phi'''\) 与 \((\phi'-d)/u\) 的条件转化为拟合曲率与斜率截距的单调性、分离性命题（对一般光滑剖面成立）。周期轨道则是公共宽度区间上两个高度零中点函数之差 \(\Delta(r)\) 的零点。按 \(e,c\) 的符号分四种情形：\(e\ge0,c\ge0\) 时两拱不可能闭合，根本无周期轨道；\(e\ge0,c<0\) 时 \(p'''>0\) 使 \(q=\kappa_+-\kappa_-\) 非减，且 \(\Delta'=A\Delta+Bq\)（\(B>0\)），乘积分因子后 \(\Delta'\) 等于正因子乘非减函数，由计数引理至多两个孤立零；\(e<0,c\ge0\) 与 \(e<0,c<0\) 两种情形分别用曲率间隙与截距分离证得 \(\Delta\) 在每个零点处导数为正，至多一个零。下界取 \(F_\varepsilon(x)=\varepsilon\bigl(4x-\frac{20}{3}x^3+\frac85x^5\bigr)\)：能量恒等式 \(\dot E=-\varepsilon xf(x)\) 给出平均化位移 \(Q(s,0)=-\pi s^2(4-5s^2+s^4)\)，在 \(s=1,2\) 处有单零点，隐函数定理据此产生两个双曲环，内环斥、外环吸，最大值 2 达到。

## 可信度与备注

本篇主结果已附 Lean 形式化证明，是族 143 中目前获机器检验背书的断言。姊妹篇《Uniform bounds for planar polynomial limit cycles》在同一族内证明一般多项式向量场的一致有界性（常数有限但非有效），本篇则在最受限的 Liénard 子族给出精确常数，两篇共同支撑该族的核心叙事。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇上界推理已形式化，姊妹篇仍待社区核验。另外，对 Hernández Rosales 例子的澄清基于文献中 Odani 的经典结论，读者可独立核对。

{% endraw %}
