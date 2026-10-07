---
layout: default
title: "The symmetric Mahler conjecture and its equality cases"
family: "087"
discipline: "Convex and metric geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The symmetric Mahler conjecture and its equality cases

> 结果族 087：The Mahler conjectures, functional inequalities and polar-product symplectic width　·　学科：Convex and metric geometry　·　验证状态：主结果已 Lean 形式化

## 一句话结论
论文在一切维数上证明了中心对称 Mahler 猜想（symmetric Mahler conjecture）：原点对称凸体 \(K\subset\mathbb R^n\) 的体积乘积满足 \(|K|\,|K^\circ|\ge 4^n/n!\)，等号当且仅当 \(K\) 是 Hanner 多胞体的可逆变线性像，下界与全部等号情形一并解决。

## 问题背景
凸体（convex body）\(K\) 的极体（polar body）定义为 \(K^\circ=\{y:\langle x,y\rangle\le1,\ \forall x\in K\}\)，体积乘积 \(P(K)=|K|\,|K^\circ|\) 是可逆线性变换下的不变量。Mahler 于 1939 年在数的几何（geometry of numbers）的转移定理研究中提出：对称凸体的 \(P(K)\) 能小到多少？立方体与其极体（交叉多胞体）给出 \(4^n/n!\)，猜想这就是最小值。此前只有平面情形完全解决（Mahler 的不等式，Reisner 刻画平行四边形等号），三维由 Iriyeh–Shibata（2020）攻克；高维仅有 Bourgain–Milman 反向 Blaschke–Santaló 不等式、Kuperberg 的显式下界、Nazarov 的复分析方法等不带精确常数的指数阶估计。Saint-Raymond 对无条件凸体（unconditional body）证得精确不等式（Meyer–Reisner 随后在该类识别出 Hanner 等号），Reisner 对 zonoid 亦证得精确不等式（等号为平行多胞体），但一般对称凸体既无组合结构也无解析结构可用，问题悬置逾八十年。

## 主要结果
主定理：对每个整数 \(n\ge1\) 与每个原点对称凸体 \(K\subset\mathbb R^n\)，有 \(|K|\,|K^\circ|\ge 4^n/n!\)；等号成立当且仅当 \(K\) 是 Hanner 多胞体（Hanner polytope）的可逆变线性像。Hanner 多胞体由中心对称线段出发递归生成：取笛卡尔积（\(\oplus_\infty\) 和）或凸包直和（\(\oplus_1\) 和），立方体、交叉多胞体及混合体皆属此类。由 Fradelizi–Meyer 的几何到泛函的蕴涵式，还得到偶泛函 Mahler 不等式（functional Mahler inequality）：对偶的正常下半连续凸函数 \(\varphi\)，\((\int e^{-\varphi})(\int e^{-\varphi^*})\ge 4^n\)，常数在 \(\varphi(x)=\sum_i|x_i|\) 处取到；以及对称熵–运输不等式（entropy–transport inequality）\(H(\eta_1)+H(\eta_2)\le -n\log(4e^2)+\mathcal T(\nu_1,\nu_2)\)。

## 证明思路
证明的解析心脏是一个平面"透镜"共形映射：\(F(z)=\frac8{\pi^2}\sum_{j\ge0}\frac{(-1)^jz^{2j+1}}{(2j+1)^2}\) 把单位圆盘双全纯地映到凸透镜域 \(\overline D=\{v+it:|t|\le1,\ |v|\le\lambda(t)\}\)，半宽 \(\lambda\) 严格凹。它满足关键边界律：圆周上均匀分布的角度恰被送到 \([-1,1]\) 上均匀分布的虚坐标加一个独立公平符号，即 \(F(e^{i\Theta})\stackrel{\mathrm{law}}{=}\varepsilon\lambda(T)+iT\)。这是 Gross 共形 Skorokhod 嵌入中均匀分布例子的旋转。

先对有限条带定义的多胞体 \(A=\{X:|b_i\cdot X|\le1\}\)（极体 \(A^\circ=\operatorname{conv}\{\pm b_i\}\)）证明。第一步证全纯质量估计（holomorphic mass estimate）：若全纯映射 \(f\) 以原点为唯一零点、最低齐次主部次数为 \(k\) 且次水平集紧，则水平集上 Jacobian 子式平方和的积分 \(\ge(\pi k)^d/d!\)——论文用 Stokes 定理与齐次通量比较直接证明，背景是广义 Lelong 数理论。第二步对 \(f_k=(g(b_jz))^k\)（\(g=F^{-1}\)）令 \(k\to\infty\)：径向变量代换 \(u_i=\rho_i^{1/k}e^{i\theta_i}\) 把积分质量集中到边界采样点，Fatou 引理给出可行性概率之和 \(S=\sum_I P_I\ge1\)。第三步用透镜边界律把概率精确翻译成实体积：每个可行基与符号组对应极体内一个以 0 和带符号行为顶点的单纯形，其并 \(\Sigma_X\subset A^\circ\)，于是 \(1\le S=\frac{d!}{4^d}\int_A|\Sigma_X|\,dX\le\frac{d!}{4^d}|A|\,|A^\circ|\)，不等式随之成立。最后用极体的内接对称多胞体逼近 \((1-\delta)Q\subset Q_j\subset Q\) 过渡到任意对称凸体，不需要任何光滑性或一般位置假设。

等号分类另起一幕。设 \(P(K)=4^n/n!\)，令 \(Q=K^\circ\) 并升维为 \(B=K\oplus_1[-1,1]\)（其极体为 \(Q\times[-1,1]\)），范数和公式保持等号；于是可行单纯形的缺失体积积分趋于零，迫使每个内部点、每个方向都有取到透镜边界的最优表示。在趋近 \(B\) 顶点处，透镜端点渐近 \(\lambda(1-\eta)\sim\frac2\pi\eta\log\frac1\eta\) 给出支撑函数不等式，经凸分离转化为：以 \(Q\) 为单位球的赋范空间中任意三点都有度量中点（metric median）。由 Lima 的范数可加分解判据，这等价于三球交性质（3.2 intersection property）——两两相交的三闭球必有公共点；Hansen–Lima 的经典分类定理断言此类有限维 Banach 空间恰为实直线经有限次 \(\ell_1/\ell_\infty\) 直和得到者，其单位球正是 Hanner 多胞体，故 \(Q\) 从而 \(K\) 是线性 Hanner 体。

## 可信度与备注
主结果已由 Lean 形式化证明。本篇与同族两篇姊妹篇互补：一般凸体篇证非对称常数 \((n+1)^{n+1}/(n!)^2\)（单纯形等号），辛几何篇用球嵌入从体积角度另证对称下界；三者在透镜映射这一解析工具上同源，但逻辑上相互独立。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇主结果已形式化，可信度较高，泛函与熵–运输推论则仍以论文推导为准。

{% endraw %}
