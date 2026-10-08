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

## 入门导读 🐣

想象收到一团揉皱的宣纸：双有理几何专家的日常，就是把它抚平成一个"最简形状"，全程只许抹平褶皱、不许撕破纸。这篇论文证明：对一类"褶皱程度中等"的高维空间——维数至少 3、固有曲率整体不亏、截面数恰好按一次方速度增长——这样的最简形状必定存在。它补上了极小模型猜想拼图中拖延多年的一块。

**关键词卡片**

- 极小模型（minimal model）：与原空间双有理等价、处处曲率非负的"最简替身"。
- 典范除子 `@@M@@K_X@@`（canonical divisor）：记录空间固有曲率的账本，正负主导几何命运。
- 伪有效（pseudo-effective）：账本整体不亏本，即落在有效除子的闭包里。
- 数值维数 `@@M@@\kappa_\sigma@@`（numerical dimension）：截面数随倍数增长的速度；本文专攻"一次方增长"。
- 翻转（flip）：一种"换褶皱不换本质"的外科手术，扔掉坏形状、换上好形状。

**看个具体例子**

取亏格 `@@M@@\ge 2@@` 的曲线 `@@M@@C@@` 与阿贝尔簇（高维环面）`@@M@@A@@`，令 `@@M@@X=C\times A@@`，且 `@@M@@\dim A\ge 2@@`。它维数 `@@M@@\ge 3@@`；`@@M@@K_X@@` 恰是 ample 的 `@@M@@K_C@@` 的拉回，整体不亏；截面数 `@@M@@h^0(mK_X)@@` 随 `@@M@@m@@` 线性增长，正是 `@@M@@\kappa_\sigma=1@@` 的教科书样本。这个例子自己就是极小模型；定理的分量在于：任何满足这两条假设的 `@@M@@X@@`，都注定能经有限步手术抵达同样干净的结局。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <rect x="80" y="28" width="400" height="120" rx="10" fill="#f5f8fb" stroke="#667788" stroke-width="2"/>
  <text x="280" y="50" text-anchor="middle" font-size="15" fill="#334455">X = C × A（维数 ≥ 3，K_X 伪有效）</text>
  <line x1="160" y1="62" x2="160" y2="138" stroke="#4a90c4" stroke-width="2"/>
  <line x1="240" y1="62" x2="240" y2="138" stroke="#4a90c4" stroke-width="2"/>
  <line x1="320" y1="62" x2="320" y2="138" stroke="#4a90c4" stroke-width="2"/>
  <line x1="400" y1="62" x2="400" y2="138" stroke="#4a90c4" stroke-width="2"/>
  <text x="445" y="104" font-size="13" fill="#4a90c4">纤维 A</text>
  <line x1="280" y1="148" x2="280" y2="184" stroke="#8899aa" stroke-width="2"/>
  <polygon points="280,192 275,180 285,180" fill="#8899aa"/>
  <text x="300" y="173" font-size="13" fill="#8899aa">投影</text>
  <path d="M80 225 Q 165 190 250 225 T 420 225" fill="none" stroke="#c0504d" stroke-width="3"/>
  <text x="280" y="252" text-anchor="middle" font-size="14" fill="#c0504d">基曲线 C（亏格 ≥ 2）</text>
  <text x="280" y="272" text-anchor="middle" font-size="12" fill="#666666">截面数随倍数线性增长，κσ = 1</text>
</svg>

</div>

**为什么值得关心**

极小模型纲领是高维几何的总路线图，而"伪有效却不大"的中间地带是最难啃的骨头之一；本文不设任何附加条件，把其中"一次方增长"的一整块解决。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

对维数 `@@M@@n\geq 3@@`、典范除子 `@@M@@K_X@@` 伪有效且数值维数 `@@M@@\kappa_\sigma(X,K_X)=1@@` 的光滑复射影簇，本文证明极小模型猜想在该情形成立：`@@M@@X@@` 有 `@@M@@\mathbb Q@@`-因子终型（terminal）极小模型；结合同项目的对数丰度定理，它还是好极小模型。

## 问题背景

极小模型猜想（minimal model conjecture）是双有理几何的核心纲领：若光滑射影簇的典范除子 `@@M@@K_X@@` 伪有效（pseudo-effective，即数值类落在有效除子锥的闭包中），它就应双有理等价于一个典范除子 nef（每条整曲线上度数非负）的极小模型。三维情形由 Mori 等人解决，BCHM（2010）处理了大边界 klt 对与一般型，但"伪有效而不大"的中间地带长期开放。Nakayama 的数值维数 `@@M@@\kappa_\sigma@@` 以取定充裕（ample）扭转后 `@@M@@h^0(mK_X+A)@@` 的增长幂次来度量这一地带：`@@M@@\kappa_\sigma=0@@` 的存在性由 Druel、Gongyo 得到，`@@M@@\kappa_\sigma=1@@` 此前只有附带假设的部分结果——Lazić–Peternell 要求簇已极小且 `@@M@@\chi(\mathcal O_X)\neq0@@`，Liu–Xu 要求维数至多五且 Kodaira 维数非负。本文去掉全部额外假设，对一切 `@@M@@n\geq 3@@` 的光滑连通复射影簇给出肯定答案。

## 主要结果

**定理 1.1** 设 `@@M@@X@@` 是维数 `@@M@@n\geq 3@@` 的光滑连通复射影簇，`@@M@@K_X@@` 伪有效且 `@@M@@\kappa_\sigma(X,K_X)=1@@`。则存在射影、`@@M@@\mathbb Q@@`-因子、终型的簇 `@@M@@Y@@`，以及有限步 `@@M@@K@@`-负除子收缩与翻转（flip）复合而成的 `@@M@@\phi:X\dashrightarrow Y@@`，使 `@@M@@K_Y@@` nef、`@@M@@\phi@@` 的逆不收缩任何素除子，且在公共光滑分辨率上 `@@M@@p^*K_X=q^*K_Y+E@@`，其中 `@@M@@E@@` 为有效 `@@M@@q@@`-例外 `@@M@@\mathbb Q@@`-除子。这里 `@@M@@\kappa_\sigma=1@@` 的确切含义是：对每个取定的充裕 Cartier 扭转 `@@M@@A@@`，截面数 `@@M@@h^0(X,mK_X+A)@@` 都不出现正的二次增长 `@@M@@\limsup@@`。

**推论 1.2** 同一端点 `@@M@@Y@@` 上 `@@M@@K_Y@@` 半充裕（semiample），故 `@@M@@Y@@` 是 `@@M@@X@@` 的好极小模型（good minimal model）；这一步引用了同项目 OpenAI 的对数丰度（log abundance）定理。

## 证明思路

证明分三步，核心困难在于：每个正扰动参数处的 MMP 都有限终止，但这无穷多段的拼接未必终止，如何过渡到参数为零。

**第一步：正扰动给出固定模型。** 取有效充裕有理除子 `@@M@@B@@` 使 `@@M@@(X,B)@@` klt 且 `@@M@@K_X+B@@` 充裕，则因 `@@M@@K_X@@` 伪有效，`@@M@@K_X+tB@@` 对一切 `@@M@@t>0@@` 都是大的（big）。令 `@@M@@t_j=2^{-j}@@`，逐段运行以 `@@M@@(t_j-t_{j+1})B@@` 为缩放除子的 `@@M@@(K+t_{j+1}B)@@`-MMP：由 BCHM 每段有限步终止，端点伴随除子 nef 且大、从而半充裕，且不会出现 Mori 纤维化。为绕过拼接不终止，作者证明"余维数二的稳定化"。翻转目标一侧：终型簇在余维数二处光滑，余维数二翻转分量的一般点爆破给出差异恰为 2 的赋值，而其旧差异小于 2，故它必是 `@@M@@X@@` 上原有的素除子——这样的除子只有有限个，且每个至多消费一次。翻转源一侧：代数 `@@M@@(n-2)@@`-闭链类张成的实向量空间的维数在翻转轨道含余维数二分量时严格下降，非负整数只能下降有限次。于是取定有限前缀后的模型 `@@M@@Y@@`：对每个 `@@M@@j@@`，`@@M@@M_j=K_Y+t_jB_Y@@` 的充分可除倍数在余维数至少三的闭集 `@@M@@Z_j@@` 之外无基点。

**第二步：第一张曲面排除正平方。** 取关于很充裕 `@@M@@H@@` 的非常一般完全交曲面 `@@M@@S@@`，同时避开奇点轨迹与全部 `@@M@@Z_j@@`，则 `@@M@@M_j|_S@@` 半充裕故 nef，取极限得 `@@M@@K_Y|_S@@` nef，即 `@@M@@L^2\cdot H^{n-2}\ge 0@@`。若此数为正：在分辨率 `@@M@@\widehat Y@@` 上固定扭转 `@@M@@P@@`，用 Nadel 乘子理想（multiplier ideal）消没与 Koszul 复形把 `@@M@@S@@` 上截面提升回 `@@M@@\widehat Y@@`，曲面 Riemann–Roch 把正平方转化为二次增长下界；再经公共分辨率上的有效差 `@@M@@u^*K_X-r^*\pi^*L\ge 0@@` 逐级单射传回 `@@M@@X@@`，得到 `@@M@@h^0(X,mK_X+A_X)@@` 的正二次 `@@M@@\limsup@@`，与 `@@M@@\kappa_\sigma=1@@` 矛盾。故 `@@M@@L^2\cdot H^{n-2}=0@@`。

**第三步：第二张曲面排除负曲线。** 设 `@@M@@C_0@@` 满足 `@@M@@L\cdot C_0<0@@`（可含于奇点轨迹）。取过其一点的完全交曲面 `@@M@@T@@`：各分量上 `@@M@@M_j^2@@` 非负，带权和恰为 `@@M@@M_j^2\cdot H^{n-2}\to 0@@`。关键的"环境射流引理"断言：在光滑簇上沿一条固定曲线，任意线丛的截面在曲线每点的消没阶有下界 `@@M@@-\deg/g@@`，`@@M@@g@@` 只依赖该曲线。由 `@@M@@\deg\,\iota^*\pi^*M_j@@` 一致为负，`@@M@@k_jM_j@@` 的全部截面在固定点 `@@M@@z@@` 处至少消没 `@@M@@ck_j@@` 阶。把截面限制到 `@@M@@T@@` 的分辨率并在 `@@M@@z@@` 上方一点爆破，得固定例外曲线 `@@M@@e@@`，线性系的固定部分 `@@M@@F_j@@` 沿 `@@M@@e@@` 的系数 `@@M@@\ge ck_j@@`；Hodge 指数定理（Hodge index theorem）给出 `@@M@@F_j^2\le -\epsilon k_j^2@@`，而移动剩余部分平方非负，故 `@@M@@M_j^2\cdot[T]\ge\epsilon@@`，与趋于零矛盾。因此不存在负曲线，`@@M@@K_Y@@` nef；定理的其余断言由第一步的有限前缀直接给出。

## 可信度与备注

主结果暂无形式化证明，验证状态以社区核验为准。本文属于结果族 036：推论 1.2 直接调用同项目 OpenAI 的对数丰度定理（文献键 OpenAILogAbundance2026）把极小模型升级为好极小模型，族内关于 nef 伴随除子数值半充裕性、广义 log canonical 对极小模型与 Mori 纤维化存在的姊妹篇与之互相支撑。按 OpenAI 官方声明，未经形式化的结果可能存在问题，请审慎对待。

{% endraw %}
