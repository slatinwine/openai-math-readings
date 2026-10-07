---
layout: default
title: "Minimal models in numerical dimension one"
family: "036"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Minimal models in numerical dimension one

> 结果族 036：Numerical semiampleness and generalized minimal models　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对维数 \(n\geq 3\)、典范除子 \(K_X\) 伪有效且数值维数 \(\kappa_\sigma(X,K_X)=1\) 的光滑复射影簇，本文证明极小模型猜想在该情形成立：\(X\) 有 \(\mathbb Q\)-因子终型（terminal）极小模型；结合同项目的对数丰度定理，它还是好极小模型。

## 问题背景

极小模型猜想（minimal model conjecture）是双有理几何的核心纲领：若光滑射影簇的典范除子 \(K_X\) 伪有效（pseudo-effective，即数值类落在有效除子锥的闭包中），它就应双有理等价于一个典范除子 nef（每条整曲线上度数非负）的极小模型。三维情形由 Mori 等人解决，BCHM（2010）处理了大边界 klt 对与一般型，但"伪有效而不大"的中间地带长期开放。Nakayama 的数值维数 \(\kappa_\sigma\) 以取定充裕（ample）扭转后 \(h^0(mK_X+A)\) 的增长幂次来度量这一地带：\(\kappa_\sigma=0\) 的存在性由 Druel、Gongyo 得到，\(\kappa_\sigma=1\) 此前只有附带假设的部分结果——Lazić–Peternell 要求簇已极小且 \(\chi(\mathcal O_X)\neq0\)，Liu–Xu 要求维数至多五且 Kodaira 维数非负。本文去掉全部额外假设，对一切 \(n\geq 3\) 的光滑连通复射影簇给出肯定答案。

## 主要结果

**定理 1.1** 设 \(X\) 是维数 \(n\geq 3\) 的光滑连通复射影簇，\(K_X\) 伪有效且 \(\kappa_\sigma(X,K_X)=1\)。则存在射影、\(\mathbb Q\)-因子、终型的簇 \(Y\)，以及有限步 \(K\)-负除子收缩与翻转（flip）复合而成的 \(\phi:X\dashrightarrow Y\)，使 \(K_Y\) nef、\(\phi\) 的逆不收缩任何素除子，且在公共光滑分辨率上 \(p^*K_X=q^*K_Y+E\)，其中 \(E\) 为有效 \(q\)-例外 \(\mathbb Q\)-除子。这里 \(\kappa_\sigma=1\) 的确切含义是：对每个取定的充裕 Cartier 扭转 \(A\)，截面数 \(h^0(X,mK_X+A)\) 都不出现正的二次增长 \(\limsup\)。

**推论 1.2** 同一端点 \(Y\) 上 \(K_Y\) 半充裕（semiample），故 \(Y\) 是 \(X\) 的好极小模型（good minimal model）；这一步引用了同项目 OpenAI 的对数丰度（log abundance）定理。

## 证明思路

证明分三步，核心困难在于：每个正扰动参数处的 MMP 都有限终止，但这无穷多段的拼接未必终止，如何过渡到参数为零。

**第一步：正扰动给出固定模型。** 取有效充裕有理除子 \(B\) 使 \((X,B)\) klt 且 \(K_X+B\) 充裕，则因 \(K_X\) 伪有效，\(K_X+tB\) 对一切 \(t>0\) 都是大的（big）。令 \(t_j=2^{-j}\)，逐段运行以 \((t_j-t_{j+1})B\) 为缩放除子的 \((K+t_{j+1}B)\)-MMP：由 BCHM 每段有限步终止，端点伴随除子 nef 且大、从而半充裕，且不会出现 Mori 纤维化。为绕过拼接不终止，作者证明"余维数二的稳定化"。翻转目标一侧：终型簇在余维数二处光滑，余维数二翻转分量的一般点爆破给出差异恰为 2 的赋值，而其旧差异小于 2，故它必是 \(X\) 上原有的素除子——这样的除子只有有限个，且每个至多消费一次。翻转源一侧：代数 \((n-2)\)-闭链类张成的实向量空间的维数在翻转轨道含余维数二分量时严格下降，非负整数只能下降有限次。于是取定有限前缀后的模型 \(Y\)：对每个 \(j\)，\(M_j=K_Y+t_jB_Y\) 的充分可除倍数在余维数至少三的闭集 \(Z_j\) 之外无基点。

**第二步：第一张曲面排除正平方。** 取关于很充裕 \(H\) 的非常一般完全交曲面 \(S\)，同时避开奇点轨迹与全部 \(Z_j\)，则 \(M_j|_S\) 半充裕故 nef，取极限得 \(K_Y|_S\) nef，即 \(L^2\cdot H^{n-2}\ge 0\)。若此数为正：在分辨率 \(\widehat Y\) 上固定扭转 \(P\)，用 Nadel 乘子理想（multiplier ideal）消没与 Koszul 复形把 \(S\) 上截面提升回 \(\widehat Y\)，曲面 Riemann–Roch 把正平方转化为二次增长下界；再经公共分辨率上的有效差 \(u^*K_X-r^*\pi^*L\ge 0\) 逐级单射传回 \(X\)，得到 \(h^0(X,mK_X+A_X)\) 的正二次 \(\limsup\)，与 \(\kappa_\sigma=1\) 矛盾。故 \(L^2\cdot H^{n-2}=0\)。

**第三步：第二张曲面排除负曲线。** 设 \(C_0\) 满足 \(L\cdot C_0<0\)（可含于奇点轨迹）。取过其一点的完全交曲面 \(T\)：各分量上 \(M_j^2\) 非负，带权和恰为 \(M_j^2\cdot H^{n-2}\to 0\)。关键的"环境射流引理"断言：在光滑簇上沿一条固定曲线，任意线丛的截面在曲线每点的消没阶有下界 \(-\deg/g\)，\(g\) 只依赖该曲线。由 \(\deg\,\iota^*\pi^*M_j\) 一致为负，\(k_jM_j\) 的全部截面在固定点 \(z\) 处至少消没 \(ck_j\) 阶。把截面限制到 \(T\) 的分辨率并在 \(z\) 上方一点爆破，得固定例外曲线 \(e\)，线性系的固定部分 \(F_j\) 沿 \(e\) 的系数 \(\ge ck_j\)；Hodge 指数定理（Hodge index theorem）给出 \(F_j^2\le -\epsilon k_j^2\)，而移动剩余部分平方非负，故 \(M_j^2\cdot[T]\ge\epsilon\)，与趋于零矛盾。因此不存在负曲线，\(K_Y\) nef；定理的其余断言由第一步的有限前缀直接给出。

## 可信度与备注

主结果暂无形式化证明，验证状态以社区核验为准。本文属于结果族 036：推论 1.2 直接调用同项目 OpenAI 的对数丰度定理（文献键 OpenAILogAbundance2026）把极小模型升级为好极小模型，族内关于 nef 伴随除子数值半充裕性、广义 log canonical 对极小模型与 Mori 纤维化存在的姊妹篇与之互相支撑。按 OpenAI 官方声明，未经形式化的结果可能存在问题，请审慎对待。

{% endraw %}
