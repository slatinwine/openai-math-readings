---
layout: default
title: "Thompson's group F is nonamenable"
family: "248"
discipline: "Group theory"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Thompson's group F is nonamenable

> 结果族 248：Thompson's group <i>F</i> is nonamenable　·　学科：Group theory　·　验证状态：主结果已 Lean 形式化

## 一句话结论

论文证明了 Thompson 群 \(F\)——区间 \([0,1]\) 上二进分段线性同胚构成的群——不是顺从群（nonamenable），确认了 Geoghegan 1979 年猜想，为这个悬置四十余年的几何群论难题画上句号。

## 问题背景

Thompson 群 \(F\) 由 \([0,1]\) 上所有保定向分段线性同胚构成，要求分段有限、断点均为二进有理数（dyadic rational）、斜率均为 2 的整数幂；它由 Thompson 于 1965 年引入（早期构造见 McKenzie–Thompson 1973），是几何群论的核心对象。顺从性（amenability）源自 von Neumann 与 Day 的经典理论：群顺从当其上有正的、归一的左不变平均（invariant mean）；由 Følner 准则可知，顺从群对任何有限平移集都能找到相对边界 \(|hA\triangle A|/|A|\) 同时任意小的有限集。Cannon–Floyd–Parry 讲义记载了 Geoghegan 1979 年的猜想：\(F\) 非顺从。问题之难在于两条经典判据全部失效：Brin–Squier（1985）证明 \(F\) 不含非交换自由子群，自由群障碍用不上；\(F\) 又不属于初等顺从类（elementary amenable）。此前不乏两个方向的证明断言——Akhmedov 2021 宣称非顺从，Shavgulidze 2009 宣称顺从（被 Moore 指出错误，Moore 亦撤回过自己一篇顺从证明）——均未成为定论。Moore 还证明了 Følner 集大小的塔式下界与 Ramsey 刻画，Haagerup–Olesen 证明 Thompson 群 \(T\) 的约化 C*-代数单性蕴含 \(F\) 非顺从，但都不能直接定夺。

## 主要结果

主定理：Thompson 群 \(F\) 不是顺从群。论文实际证明的是定量版本（finite-proof.tex，命题 avg:boundary）：存在与待测集无关的有限集 \(S\subset F\) 及正常数
\[c=\frac{\delta^2/L^2-4/D}{4(1-1/D)}>0,\]
使得对一切非空有限集 \(A\subset F\) 均有 \(\max_{h\in S}|hA\triangle A|/|A|\ge c\)，与 Følner 准则直接矛盾。推论有两条（consequences.tex，均援引配套定理）：其一，对每个 \(\varepsilon>0\)，存在表示 \(\pi:F\to\mathrm{GL}(H)\) 满足 \(\sup_g\|\pi(g)\|\le1+\varepsilon\)，却不能被任何有界可逆算子整体酉化（nonunitarizable，不可酉化）；其二，对任意有限对称生成集给出的 Cayley 图，Bernoulli 边渗流（bond percolation）满足 \(\|T_{p_c}\|_{2\to2}<\infty\)、\(p_c<p_{2\to2}\le p_u\)，且对每个 \(p\in(p_c,p_u)\) 几乎必然出现无穷多个无穷开簇（open cluster），并存在确定性窗口 \([p_1,p_2]\) 使之同时发生。

## 证明思路

整个证明是"反证法＋无穷维现象＋一次有限平均"的组合。先固定三样与待测集无关的原料。其一，Benyamini–Sternfeld 定理（1983）供给的映射：无穷维 Hilbert 空间闭单位球 \(B\) 上存在 Lipschitz 自映射 \(f\) 与 \(\delta>0\) 使 \(\|f(x)-x\|\ge\delta\) 处处成立（无近似不动点）；附录在 \(L^2([0,1];\mathbb R^2)\) 上以 \(\delta=1/2\) 显式构造——沿一条带"有界尾部"的螺线曲线取固定半径的管状邻域，再令 \(f(x)=-G(x)/\|G(x)\|\)。其二，满足 \(D>4L^2/\delta^2\) 的大整数 \(D\)。其三，\(D\) 个两两分离的内部二进区间 \(I_1<\cdots<I_D\)（父区间），并在每个父区间内放入这组区间的仿射拷贝 \(I_i\cdot I_j\)（子区间）。随后对每个基本二进划分按胞腔数递归定义颜色 \(p(T)\in B\)：当 \(T\) 尊重全部父区间时，\(p(T)=f(\text{诸限制颜色的均值})\)，否则取 \(0\)；取限制会严格减少胞腔数，故归纳良定。对群元 \(g\) 取足够细的水平 \(n\)，使像划分 \(gT^{(n)}\) 基本化并尊重所有相关区间，据此定义颜色函数 \(X_I(g)\) 与标量相关（scalar correlation）\(\varphi_{I,J}(g)=\langle X_I,X_J\rangle\)。

接着是组合核心"搬运"：\(F\) 能把任意分离区间对标仿射地送到任意另一对（在三个余隙中反复二分配平胞腔数即可），据此预先固定有限搬运元集 \(S\)。精确的协方差恒等式 \(((hg)T^{(n)})_{I'}=(gT^{(n)})_I\) 给出 \(\varphi_{I,J}(g)=\varphi_{I_1,I_2}(h_{I,J}g)\)；再配合初等的有限平均比较 \(|\mathbb E_A\varphi(hg)-\mathbb E_A\varphi(g)|\le|hA\triangle A|/|A|=\eta\)，可得：凡严格分离的区间对，其平均相关都落在同一公共值 \(\alpha\) 的 \(\eta\) 邻域中。

最后是方差估计。令 \(m\) 为父颜色均值、\(z_i\) 为第 \(i\) 个父区间诸子颜色的均值，递归定义给出精确恒等式 \(X_{I_i}=f(z_i)\)，而 \(m\) 又是诸 \(f(z_i)\) 的均值。位移下界、平方范数的凸性与 Lipschitz 条件联合给出
\[\delta^2\le\|m-f(m)\|^2\le\frac{L^2}{D}\sum_i\|z_i-m\|^2 .\]
展开 \(\mathbb E_A\|z_i-m\|^2\) 时，交叉项中严格分离对的相关被 \(\alpha\pm\eta\) 控制，公共值 \(\alpha\) 的系数恰好正负相消；对角项与嵌套对只占比例 \(1/D\)，由单位球界控制。合并得 \(\mathbb E_A\|z_i-m\|^2\le4/D+4(1-1/D)\eta\)，代回上式整理即得一致正下界 \(c\)，与 Følner 准则矛盾，故 \(F\) 非顺从。

## 可信度与备注

论文标注主结果已获 Lean 形式化证明（结果族 248 附有形式化文档），这对该量级的结论是重要保障。两条推论分别援引同项目关于不可酉化表示与渗流的姊妹定理：它们依赖本文结论而非相反，论文也明确说明二者未参与非顺从性的证明。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本文主结果已形式化，推论所涉配套定理仍请以社区核验为准。

{% endraw %}
