---
layout: default
title: "Nagata's Conjecture for Plane Curves"
family: "039"
discipline: "Algebraic and complex geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Nagata's Conjecture for Plane Curves

> 结果族 039：Nagata's conjecture and maximal Seshadri constants　·　学科：Algebraic and complex geometry　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

在一张大纸上钉 10 枚或更多图钉，再派一条 `@@M@@d@@` 次代数曲线去逐个"拜会"：第 `@@M@@i@@` 枚图钉要拜访 `@@M@@m_i@@` 遍。Nagata 在 1959 年猜：只要图钉摆得不特殊，拜会的总次数一定严格少于 `@@M@@d\sqrt r@@`——曲线想多绕几圈？账单有硬上限。本文对一切 `@@M@@r\ge 10@@` 完整证明了这个猜想，并顺带算清了爆炸曲面上相应的 Seshadri 常数。

**关键词卡片**

- 平面曲线（plane curve）：一个 `@@M@@d@@` 次齐次方程在射影平面里的零点集，允许可约。
- 重数（multiplicity）：曲线在某点"打转"的圈数。
- 非常一般点（very general points）：避开所有可数个特殊位置陷阱的摆放。
- Nagata 猜想（Nagata's conjecture）：总重数账单 `@@M@@\sum_i m_i<d\sqrt r@@`。
- Seshadri 常数（Seshadri constant）：曲线过点消耗正性的效率；本文算得 `@@M@@1/\sqrt r@@`。

**看个具体例子**

取 `@@M@@r=10@@`：上限为 `@@M@@d\sqrt{10}\approx 3.162\,d@@`。若 `@@M@@d=10@@`：每点重数 `@@M@@3@@` 时总账 `@@M@@30<31.6@@`，尚有可能；每点重数 `@@M@@4@@` 则 `@@M@@40>31.6@@`，必然无解。为什么从 10 开始？`@@M@@r=9@@` 时过 9 个一般点总有不为零的三次曲线，`@@M@@9=3\times\sqrt 9@@` 恰好卡在等号上，严格不等式无从谈起。Nagata 本人当年只证出点数为平方数（至少 16）的情形，此后六十多年的最好记录也停在略低于 `@@M@@\sqrt r@@` 的位置，本文终于触线。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="30" text-anchor="middle" font-size="15" fill="#334455">10 枚图钉与一条曲线：总重数 30 &lt; 31.6</text>
  <path d="M40 205 C 62 172, 76 147, 95 128 S 122 100, 152 86 S 185 62, 208 68 S 240 78, 262 92 S 285 112, 302 132 S 330 164, 356 186 S 388 218, 414 222 S 446 236, 466 232 S 492 210, 510 150" fill="none" stroke="#4a90c4" stroke-width="2.5"/>
  <circle cx="40" cy="205" r="5" fill="#c0504d"/>
  <circle cx="95" cy="128" r="5" fill="#c0504d"/>
  <circle cx="152" cy="86" r="5" fill="#c0504d"/>
  <circle cx="208" cy="68" r="5" fill="#c0504d"/>
  <circle cx="262" cy="92" r="5" fill="#c0504d"/>
  <circle cx="302" cy="132" r="5" fill="#c0504d"/>
  <circle cx="356" cy="186" r="5" fill="#c0504d"/>
  <circle cx="414" cy="222" r="5" fill="#c0504d"/>
  <circle cx="466" cy="232" r="5" fill="#c0504d"/>
  <circle cx="510" cy="150" r="5" fill="#c0504d"/>
  <text x="90" y="250" font-size="13" fill="#c0504d">图钉：非常一般点</text>
  <text x="440" y="70" font-size="13" fill="#4a90c4">d 次曲线</text>
  <text x="280" y="272" text-anchor="middle" font-size="13" fill="#666666">每点重数 3 可以做到；重数 4 必然无曲线</text>
</svg>

</div>

**为什么值得关心**

它是多项式插值问题的地基，并精确钉死了爆炸曲面的多点 Seshadri 常数；而且整个主定理已通过计算机辅助的形式化证明验证，可信度极高。

> 已 Lean 形式化

## 一句话结论
证明了 `@@M@@r\ge 10@@` 个非常一般复点上，任何带任意重数 `@@M@@m_i@@` 的非零有效平面曲线必满足 `@@M@@\sum_i m_i\lt d\sqrt r@@`，以严格、非齐次的形式完全确立 Nagata 猜想，并给出爆炸曲面上多点 Seshadri 常数的精确值 `@@M@@1/\sqrt r@@`。

## 问题背景
过多点作平面曲线是经典插值问题：给定点的位置与所需消失阶，曲线次数 `@@M@@d@@` 最小能有多小？Nagata 在研究希尔伯特第十四问题（Hilbert's fourteenth problem）时于 1959 年提出该猜想，并证明了点数为平方数（至少 16）的情形。维数计数给出临界尺度：`@@M@@d@@` 次型有 `@@M@@\binom{d+2}{2}@@` 个系数，`@@M@@r@@` 个点上阶 `@@M@@\ge m@@` 至多施加 `@@M@@r\binom{m+1}{2}@@` 个线性条件，首项恰在 `@@M@@d=m\sqrt r@@` 处平衡。条件计数只能保证该尺度之上曲线存在；要证明之下不存在，必须对所有 `@@M@@m@@` 一致地控制条件之间的线性相关，这正是难点。此外 `@@M@@r=9@@` 时非零三次曲线总存在，严格不等式不可能从 9 开始。此前最好结果如 Roé 的 `@@M@@d\gt m(\sqrt{r-1}-\pi/8)@@`（`@@M@@r\ge 10@@`）与十点情形的 `@@M@@d/m\ge 117/37@@`，均未触及 `@@M@@\sqrt r@@` 本身。

## 主要结果
主定理：对每个整数 `@@M@@r\ge 10@@`，存在配置空间 `@@M@@U_r@@` 中可数个真 Zariski 闭子集之并 `@@M@@E_r@@`（余集非空），使得对 `@@M@@E_r@@` 之外的任意点组 `@@M@@(p_1,\ldots,p_r)@@`：若非零有效平面曲线（effective plane curve，即某个 `@@M@@d\ge 1@@` 次齐次形式的零除子，允许可约与非约化）满足 `@@M@@\mathrm{mult}_{p_i}C\ge m_i@@`，则必有 `@@M@@d\sqrt r\gt\sum_{i=1}^r m_i@@`。重数向量完全任意（非齐次形式），且同一点组对所有次数与重数向量一致成立。推论：结论经 `@@M@@\mathbb Q@@` 上定义的关联轨迹延伸到任意不可数、特征为零的代数闭域；在 `@@M@@r@@` 点爆炸（blow-up）曲面上，除子类 `@@M@@\sqrt r\,H-\sum_i E_i@@` 严格 nef 且自交为零，故多点 Seshadri 常数（multipoint Seshadri constant）`@@M@@\varepsilon(\mathcal O(1);p_1,\ldots,p_r)=1/\sqrt r@@`。

## 证明思路
先做归约：若某非常一般点组出现违约曲线，则由关联轨迹的闭性与有理定义性，相应线性系统在每个点组都有非零解（普适系统 `@@M@@\mathsf U_r(d,m)@@`）；再用 Nagata 的循环乘积技巧——对重数向量取 `@@M@@r@@` 次循环置换、各取一条曲线相乘——得到等重数系统，次数 `@@M@@d=rd_0@@`、公共重数 `@@M@@m=\sum_i m_i@@`，且 `@@M@@d/m\le\sqrt r@@`，还可取任意公倍数放大。于是只需排除一切 `@@M@@d/m\le\sqrt r@@` 的普适系统。

再把曲线化为法丛上的多项式：让点沿切向逼近一条 `@@M@@k@@` 次光滑曲线 `@@M@@B@@`，重标度法向坐标后取极限，得到法丛全空间 `@@M@@\mathrm{Tot}(M)@@` 上的多项式 `@@M@@F(w)=\sum_j f_j w^j@@`，系数 `@@M@@f_j\in H^0(B,L^{d-kj})@@`，在任意指定的法向位移处仍消失到阶 `@@M@@\ge m@@`。平方情形 `@@M@@r=k^2@@` 由此直接排除：选取使 `@@M@@A=M(-P)@@` 非挠的点组（正 genus 曲线上挠线丛仅可数个，故可选）以及落在赋值像之外的位移，最高次项的度数计数与 `@@M@@w^{m-1}@@` 系数比较均导出矛盾。

非平方情形改用三次曲线：九个点取零法向位移，迫使前 `@@M@@m+1@@` 个系数落入同一度数 `@@M@@h=3(d-3m)@@` 的截面空间 `@@M@@H^0(B,T\otimes A^{m-j})@@`；先用类似计数证明 `@@M@@d\gt 3m@@`。剩余 `@@M@@q=r-9@@` 个点沿水平线碰撞，`@@M@@b@@` 次纤维求导后基座阶至少 `@@M@@q(m-b)@@`，故某个有限维 jet 映射 `@@M@@J_\tau@@` 必有非平凡核。随后让三次曲线退化为 `@@M@@X_\tau=\mathbb C^*/\tau^{\mathbb Z}@@`，乘性 theta 函数（multiplicative theta function）的剩余类 Laurent 基给出显式坐标，其归一化表达式在对数坐标 `@@M@@(x,y)@@` 下趋于 `@@M@@e^{Kx+jy}@@`（`@@M@@K@@` 为 Laurent 指数、`@@M@@j@@` 为纤维次数），混合导数给出极限矩阵 `@@M@@(K^\ell j^b)@@`，其中 `@@M@@0\le b\lt m@@`、`@@M@@0\le\ell\lt q(m-b)@@`，列由指数对 `@@M@@(j,K)@@` 标号。

最后用插值排除核：单纯的总数计数不够，关键在按固定 `@@M@@K@@` 的水平行分组——只要每行点数 `@@M@@\le m@@`，且点数 `@@M@@\ge t@@` 的行数 `@@M@@\le q(m-t+1)@@`，单项式张成的空间 `@@M@@\mathrm{span}\{K^\ell J^b\}@@` 便能插值指数集上的任意函数，矩阵满列秩。指数对恰含于一个多边形 `@@M@@\mathcal D_\lambda@@`，其水平切片宽度轮廓恰好提供这两条界；由于 `@@M@@d/m@@` 有理而 `@@M@@\sqrt r@@` 无理，严格间隙 `@@M@@d/m\lt\sqrt r@@` 允许取收缩参数 `@@M@@\lambda\lt 1@@`，并取 `@@M@@(d,m)@@` 的公倍数吸收取整端点误差。满秩对充分小的正 `@@M@@\tau@@` 保持，与每个固定曲线上 `@@M@@J_\tau@@` 有核矛盾，定理得证。

## 可信度与备注
本文主结果已由 Lean 形式化证明。它是结果族 039 的基石：曲面姊妹篇明确把 `@@M@@r\ge 10@@` 的严格阈值与严格非齐次不等式引用为本文的独立精细化，高维篇则沿用同一套机制；本文得到的 `@@M@@\varepsilon=1/\sqrt r@@` 正是族概述中极大 Seshadri 常数断言的平面原型。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文已形式化，可信度较高。

{% endraw %}
