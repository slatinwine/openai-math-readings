---
layout: default
title: "The reverse logarithmic Kodaira inequality and additivity"
family: "033"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The reverse logarithmic Kodaira inequality and additivity

> 结果族 033：Iitaka subadditivity, variation, and logarithmic additivity　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文在约化 SNC、边界层光滑设定下证明了反向对数 Kodaira 不等式 `@@M@@\kappa(X,K_X+E)\le\kappa(Y,K_Y+D)+\kappa(F,K_F+E_F)@@`，与姊妹篇的次可加性相加得到可加性等式，正面解决 Popa 的对数可加性猜想（该设定）。

## 问题背景

把光滑族完备化成射影对的态射后，其全空间能有多少对数多重典范形式？次可加性给出由基与一般纤维决定的下界；反向不等式则约束纤维变异性可能带来的额外增长，两者相等即"可加性"，是光滑族的期望行为。Popa 的对数表述（猜想 3.9）明确要求全空间与每个边界层在开基上光滑。此前的上界结果都带重条件：Popa–Schnell 在 Campana–Peternell 猜想下证光滑射影族情形；Fujino–Fujisawa 的对数上界假设基的对数 Iitaka 纤维化的一般纤维满足广义丰度；Park 假设那些纤维有好极小模型；Campana 的可加性定理要求原纤维典范层半丰。困难集中在基的对数 Kodaira 维数为 `@@M@@0@@` 或 `@@M@@-\infty@@` 的情形：负基时下界是平凡的，而上界却断言全空间的一切多重典范空间为零，是完全不同性质的结论。

## 主要结果

设 `@@M@@f:X\to Y@@` 为光滑连通射影簇之间的满射连通纤维态射，`@@M@@E,D@@` 为约化单连通交叠（SNC）除子且 `@@M@@\operatorname{Supp}(f^*D)\subseteq\operatorname{Supp}(E)@@`（只限支撑，不加平滑性；二者均可为零）。记 `@@M@@V=Y\setminus\operatorname{Supp}D@@`，并假设 `@@M@@X@@` 与 `@@M@@E@@` 的各分量交的每个不可约组分限制在 `@@M@@f^{-1}(V)@@` 上都对 `@@M@@V@@` 光滑（"层光滑"，允许水平边界分量）。

**定理（反向对数 Kodaira 不等式）**：对非常好点 `@@M@@y\in V@@` 处的纤维 `@@M@@F=X_y@@`，
`@@M@@D\kappa(X,K_X+E)\le\kappa(Y,K_Y+D)+\kappa(F,K_F+E_F);@@`
且右端任一项为 `@@M@@-\infty@@` 时，`@@M@@H^0(X,m(K_X+E))=0@@` 对一切 `@@M@@m>0@@` 成立。不设丰度、半丰度、好极小模型或一般型假设。

与姊妹篇的对数次可加性（适用于任意连通纤维的约化 SNC 对，不需层光滑）合并，立即得**对数可加性**等式
`@@M@@D\kappa(X,K_X+E)=\kappa(Y,K_Y+D)+\kappa(F,K_F+E_F),@@`
正面解决 Popa 猜想 3.9 的射影约化 SNC、层光滑表述。

## 证明思路

上界不等式的证明独立于次可加性，全部困难浓缩在"截影构造命题"里：任给非零 `@@M@@s\in H^0(X,m(K_X+E))@@`，则 `@@M@@\kappa(Y,K_Y+D)\ge0@@`；且当 `@@M@@\kappa(Y,K_Y+D)=0@@` 而 `@@M@@s@@` 在某条纤维 `@@M@@X_y@@`（`@@M@@y@@` 属于原始开基 `@@M@@V@@`）上恒为零时，存在非零基形式 `@@M@@\tau\in H^0(Y,a(K_Y+D))@@` 在 `@@M@@y@@` 处取零。先看归约。纤维为 `@@M@@-\infty@@` 时，非零总截影在非常好纤维上的限制非零，立即矛盾；基为 `@@M@@-\infty@@` 时由命题第一断言，总空间没有任何多重形式；基维数为零时，每度基截影空间至多一维，取 `@@M@@y@@` 在所有非零基多重形式的零轨迹之外，命题的第二断言保证限制映射逐度单射，得 `@@M@@\kappa(X,L_X)\le\kappa(F,L_F)@@`；基维数 `@@M@@k>0@@` 时按 Popa–Schnell 的基 Iitaka 纤维化路线约化：一般基纤维 `@@M@@G@@` 的对数维数为零，对诱导族 `@@M@@f_t:(H,E'|_H)\to(G,D'|_G)@@`（层光滑性经基变换保持）用零基情形，再作像维数估计合成 `@@M@@\dim T+\kappa(F,L_F)@@`。再看命题本身的证明。先把 `@@M@@s@@` 的 `@@M@@m@@` 次根张成循环覆盖（cyclic cover），把其上同调类投影到非零纯权数商，得到"最高 Hodge 向量"——它一般并不张满该向量丛，故整个丛的行列式正性控制不了这个特定向量的坐标，也保不住它在选定纤维上的零点。论文的关键改进是：在原对 `@@M@@(Y,D)@@` 的对数微分标架中跟踪该向量的系数（regular coefficients，格为 `@@M@@\Omega^1_{Y'}(\log D')@@`）；局部计算表明根覆盖在 `@@M@@V@@` 内新增的判别式不扩大基上允许的极点，且原光滑纤维上的零被保留；齐次张量运算后，这些数据与周期一起下降到一个射影参数空间 `@@M@@S@@`，它还记录了周期映射本身可能漏掉的紧群方向。随后分两种情形。若 `@@M@@S@@` 是点，上同理丛为常值丛，向量的各数量坐标经系数计算就是真正的基多重形式，且保留指定零点——这同时给出基的非消失性与保零性。若 `@@M@@\dim S>0@@`，先限制到 `@@M@@Y\to S@@` 的 generic 纤维使系数系统常值，非零数量坐标允许作相对 Iitaka 纤维化，在中间簇上产生与 `@@M@@K_Y+D@@` 有相同可除截影空间的除子；周期正性——包括 Bakker–Brunebarbe–Tsimerman 的整周期像代数性、Campana–Păun 的轨道余切正性、Fujino–Gongyo 的 lc-平凡纤维化模态部分 b-nef 性——使该除子加上 `@@M@@S@@` 的拉回后为大（big）；最后比较选定向量的迭代 Higgs 像与周期方向并作数值维数减法论证，去掉所加除子，得该除子本身为大，迫使 `@@M@@\kappa(Y,K_Y+D)>0@@`，与基维数 `@@M@@0@@` 或 `@@M@@-\infty@@` 矛盾，故该情形不会发生。

## 可信度与备注

本篇主结果暂无形式化证明。反向不等式的证明是自足的；可加性等式则把本篇的上界与姊妹篇《Orbifold and logarithmic Iitaka subadditivity》的下界拼接而成，二者使用同一类非常好纤维。三篇文章在结果族 033 中构成闭环：次可加性给下界、变异性给加细、反向不等式封顶。依照 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。

{% endraw %}
