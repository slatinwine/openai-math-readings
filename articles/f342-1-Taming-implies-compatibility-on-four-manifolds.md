---
layout: default
title: "Taming implies compatibility on four-manifolds"
family: "342"
discipline: "Differential geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Taming implies compatibility on four-manifolds

> 结果族 342：Donaldson's tamed-to-compatible conjecture　·　学科：Differential geometry　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

给四维空间装上一套斜放的坐标栅格 J。一把"面积尺"（辛形式）若让栅格每根斜线扫出的面积都为正，叫驯服 J；若还把栅格当成完美的方格看待，叫相容。把驯服尺投影成相容尺的初等办法会破坏"闭性"，于是这两个概念是否等价悬置了二十年——本文给出肯定答案，而且栅格 J 原封不动，只允许换尺子。

**关键词卡片**

- 殆复结构（almost complex structure）：每点指定一个"转 90 度"算子 J，未必来自真正的复坐标。
- 辛形式（symplectic form）：闭且非退化的 2-形式，一把守恒的面积尺。
- 驯服（taming）：只要求 `@@M@@\omega(v,Jv)>0@@` 对一切非零向量 `@@M@@v@@` 成立。
- 相容（compatible）：进一步要求 `@@M@@\omega(Ju,Jv)=\omega(u,v)@@`，使 J 成为保面积的旋转。
- 正电流（positive current）：反证法中构造的带权曲面族障碍物，最终导出自相矛盾。

**看个具体例子**

公式卡：`@@M@@\omega@@` 驯服 `@@M@@J@@` `@@M@@\Longrightarrow@@` 存在辛形式 `@@M@@\eta@@` 相容于同一个 `@@M@@J@@`（`@@M@@\eta(Ju,Jv)=\eta(u,v)@@`，`@@M@@J@@` 原封不动）。特别地，被驯服的 `@@M@@J@@` 自动容许辛形式。

推论：当交截形式正指标 `@@M@@b_2^+=1@@` 时还可取同上同调类 `@@M@@[\eta]=[\omega]@@`；一般情形两锥满足 `@@M@@\mathcal{K}_J^t=\mathcal{K}_J^c+H_J^-@@`。这一步看似只差一条对称性，却卡住学界二十年，症结正是投影守不住闭性。

**为什么值得关心**

正面解决 Donaldson 2006 年提出的辛几何核心存在性问题；此前只覆盖可积复曲面与部分有理流形等特殊情形。它还与姊妹篇互相支撑，共同完成超辛形变定理链条，并且是本批结果中唯一已被机器验证的。

> 已 Lean 形式化

## 一句话结论

证明 Donaldson"驯服蕴含相容"猜想：闭四维流形上被某辛形式驯服的光滑殆复结构，必相容于一个辛形式，且 `@@M@@J@@` 保持不动、形式的上同调类可以改变。这一悬置二十年的辛几何核心存在性问题得到完整正面解答。

## 问题背景

设 `@@M@@X@@` 为闭光滑四维流形，`@@M@@J@@` 为其上的光滑殆复结构（almost complex structure）。闭且非退化的实 2-形式 `@@M@@\omega@@` 称为辛形式（symplectic form）；若 `@@M@@\omega(v,Jv)>0@@` 对一切非零切向量 `@@M@@v@@` 成立，称 `@@M@@\omega@@` 驯服（tame）`@@M@@J@@`；若进一步 `@@M@@\omega(Ju,Jv)=\omega(u,v)@@`，则称相容（compatible）。相容形式给出与 `@@M@@J@@` 一致的酉几何，驯服只保证较弱的正性。Donaldson 在 2006 年提问：四维闭流形上驯服是否必然推出相容？初等投影 `@@M@@\omega\mapsto\frac12(\omega+\omega(J\cdot,J\cdot))@@` 虽保持复直线上的正性，却一般破坏闭性，障碍正在于此。可积情形（紧复曲面）已由 Buchdahl、Lamari、Li–Zhang 等解决；Gromov、Taubes 的伪全纯曲线方法先后覆盖 `@@M@@\mathbb{CP}^2@@`、`@@M@@b_2^+=1@@` 的残差情形与部分有理流形，一般光滑殆复结构的问题悬置至今。

## 主要结果

**主定理**：设 `@@M@@J@@` 是闭连通光滑四维流形 `@@M@@X@@` 上的光滑殆复结构，且被某个辛形式驯服，则存在与 `@@M@@J@@` 相容的光滑辛形式。定理中原有的 `@@M@@J@@` 原封不动，结论对相容形式的上同调类（cohomology class）不加任何限制——它并不断言任意驯服类中都含有相容代表。

结合 Li–Zhang 的四维权锥比较还得到上同调层面的推论：设 `@@M@@\mathcal K_J^t,\mathcal K_J^c\subset H^2(X;\mathbb R)@@` 分别为驯服、相容辛形式代表的上同调锥，`@@M@@H_J^-@@` 为反不变（anti-invariant，即 `@@M@@\alpha(Ju,Jv)=-\alpha(u,v)@@`）闭形式代表的子空间，则有闵可夫斯基和分解 `@@M@@\mathcal K_J^t=\mathcal K_J^c+H_J^-@@`；当交截形式正指标 `@@M@@b_2^+(X)=1@@` 时两锥相等，此时每个驯服形式 `@@M@@\omega@@` 都有同上同调类的相容代表 `@@M@@\eta@@`，即 `@@M@@[\eta]=[\omega]@@`。

## 证明思路

全文采用反证法：假设 `@@M@@J@@` 不相容于任何辛形式。第一步构造障碍电流（current）。在不变（invariant）2-形式的空间里，正定不变形式构成的开凸锥与闭不变形式的子空间不相交，Hahn–Banach 分离给出非零正电流 `@@M@@P@@`——它可表示为单位复直线双向量丛 `@@M@@\mathscr C@@` 上概率测度 `@@M@@\lambda@@` 的加权平均，且消灭所有闭不变形式。再借助椭圆提升（elliptic lift）：构造满足 `@@M@@dB=0@@`、`@@M@@RB=\mathrm{Id}@@` 的伪微分算子 `@@M@@B@@`（`@@M@@R@@` 为到反不变形式的投影），令 `@@M@@T=P+Q@@`，则反不变的 `@@M@@Q@@` 吸收误差，使 `@@M@@T@@` 消灭一切闭 2-形式；四维的关键代数事实是反不变形式必自对偶（self-dual）。

第二步建立定量估计。校正的径向试验函数给出迹测度（trace measure）`@@M@@\mu@@` 的二次增长 `@@M@@\mu(B_r(x))\le Cr^2@@`；Hodge 预解式 `@@M@@S_r=(1+r^2\Delta)^{-3}@@` 的热核具有正的标量主部，由此得到的配对不等式从下方控制"相邻点处复直线方向的偏差角" `@@M@@\iint_{d_g(x,y)<r}|\ell-\tau_{yx}m|^2\dd\lambda\dd\lambda@@`。将其与恒等式 `@@M@@0=\langle S_rP,*S_rP\rangle+2\langle S_rP,S_rQ\rangle+\|S_rQ\|_2^2@@`（源于 `@@M@@T@@` 消灭闭形式且 `@@M@@Q@@` 自对偶）联立，并用交换子增益一个导数的相对投影估计压制交叉项，可得 `@@M@@\|S_rQ\|_2@@` 一致有界，从而 `@@M@@Q\in L^2@@` 且角能量 `@@M@@\le Cr^4@@`。

第三步做密度与切测度（tangent measure）分析。类 Lelong–Jensen 的单调性比较证明密度 `@@M@@\theta(x)=\lim_{r\downarrow0}r^{-2}\mu(B_r(x))@@` 处处存在；在正密度点，伸缩极限测度必为单个复平面上面积测度的倍数，故横向位移矩为 `@@M@@o(r^2)@@`——但没有速率。核心的分裂定理（splitting theorem）把正则化密度截断 `@@M@@f_r\to c_h\theta@@` 代入闭性方程：闭性把 `@@M@@f_r@@` 沿复直线 `@@M@@L_\ell@@` 的切向导数换成"法向导数乘角亏损"之积，其积分经 Cauchy–Schwarz 后按临界标度 `@@M@@r^{-3}\cdot O(r^2)\cdot o(r)=o(1)@@` 消失，恰好抵消截断的 `@@M@@r^{-3}@@` 归一化，从而证明密度限制 `@@M@@P_E=\mathbf 1_{\{\theta>0\}}P@@` 是闭电流。

最后一步收尾。残差 `@@M@@T'=T-P_E@@` 的正部分集中在零密度中心，那里配对中的负误差趋于零；对 `@@M@@T'@@` 展开零配对恒等式并令混合项消失，迫使 `@@M@@0\ge\|Q\|_2^2@@`，即 `@@M@@Q=0@@`。于是正电流 `@@M@@P=T@@` 消灭一切闭形式，特别地 `@@M@@P(\omega)=0@@`；但驯服形式 `@@M@@\omega@@` 在紧丛 `@@M@@\mathscr C@@` 上有正下界且 `@@M@@\lambda(\mathscr C)=1@@`，强制 `@@M@@P(\omega)>0@@`，矛盾。故相容辛形式必存在。

## 可信度与备注

主定理已有 Lean 形式化证明，是本结果族中验证最完备的一环；姊妹篇将同一套正电流估计与指定类、形变论证结合，把闭四维流形上规范化的超辛（hypersymplectic）三重组形变为固定上同调类的超凯勒（hyperkähler）三重组，两文互相支撑。本文系 OpenAI 数学工作产出，按其官方声明，未经形式化的结果可能有问题，具体引理细节仍建议以社区核验为准。

{% endraw %}
