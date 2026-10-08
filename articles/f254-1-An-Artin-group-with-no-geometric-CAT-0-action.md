---
layout: default
title: "An Artin group with no geometric CAT(0) action"
family: "254"
discipline: "Group theory"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | An Artin group with no geometric CAT(0) action

> 结果族 254：Classifying spaces and geometric obstructions for Artin groups　·　学科：Group theory　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

给一个舞团找"平整舞台"：台面处处不凸不凹，舞者保持队形对称地跳，还要把舞台铺满不留死角。数学家曾猜想，任何一种"编辫子的代数结构"（Artin 群）都能登上这样的完美舞台。这篇论文却造出一个 116 人的大舞团，并证明：无论多大的平整舞台，都容不下它的舞步。

**关键词卡片**

- Artin 群（Artin group）：生成元两两满足"编织关系"（如 aba=bab）的群，辫群是它的特例。
- CAT(0) 空间（CAT(0) space）：三角形都不比平面参照更"胖"的度量空间，即曲率非正的"平地"。
- 几何作用（geometric action）：群保持距离地对称行动，且真（不挤压）、余紧（铺满不留死角）。
- 稳定平移长度（stable translation length）：元素反复作用时，平均每步向前挪动的距离。
- 环绕数（winding number）：闭曲线绕一个点转过的净圈数。

**看个具体例子**

反例的心脏是只有 3 个生成元的小群 T：a、b、c 两两编织（左图）。假如 T 能在某块 CAT(0) 舞台起舞，"长度账本"会逼出三对辫关系必须满足的大小不等式；可与此同时，a² 与 (ab)³ 这类成对的交换元素在无穷远处张开六个尖扇形，每个张角都不足 60°，首尾相接凑不满一整圈（右图）——图形拼不拢，矛盾。116 个生成元的大群，正是把三份 40 股的辫群挂到 T 的三对生成元上，再添两个"隔离元" d 与 e 搭成的。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="140" y="26" font-size="15" text-anchor="middle" fill="#333">小群 T：三对生成元两两编织</text>
  <line x1="60" y1="215" x2="180" y2="215" stroke="#4a7" stroke-width="2"/>
  <line x1="60" y1="215" x2="120" y2="65" stroke="#4a7" stroke-width="2"/>
  <line x1="180" y1="215" x2="120" y2="65" stroke="#4a7" stroke-width="2"/>
  <text x="44" y="240" font-size="16">a</text>
  <text x="186" y="240" font-size="16">b</text>
  <text x="114" y="56" font-size="16">c</text>
  <text x="120" y="258" font-size="12" text-anchor="middle" fill="#4a7">aba=bab</text>
  <text x="10" y="122" font-size="12" fill="#4a7">cac=aca</text>
  <text x="196" y="142" font-size="12" fill="#4a7">bcb=cbc</text>
  <text x="430" y="26" font-size="15" text-anchor="middle" fill="#333">六个尖扇形凑不满整圆</text>
  <circle cx="430" cy="150" r="95" fill="none" stroke="#999" stroke-dasharray="5 4"/>
  <line x1="430" y1="150" x2="525" y2="150" stroke="#c55" stroke-width="2"/>
  <line x1="430" y1="150" x2="484" y2="72" stroke="#c55" stroke-width="2"/>
  <line x1="430" y1="150" x2="397" y2="61" stroke="#c55" stroke-width="2"/>
  <line x1="430" y1="150" x2="338" y2="125" stroke="#c55" stroke-width="2"/>
  <line x1="430" y1="150" x2="357" y2="211" stroke="#c55" stroke-width="2"/>
  <line x1="430" y1="150" x2="438" y2="245" stroke="#c55" stroke-width="2"/>
  <line x1="430" y1="150" x2="512" y2="198" stroke="#c55" stroke-width="2"/>
  <circle cx="430" cy="150" r="3.5" fill="#222"/>
  <text x="452" y="106" font-size="12" fill="#666">每角 &lt; 60°</text>
  <text x="430" y="270" font-size="12" fill="#666" text-anchor="middle">六角之和 &lt; 360°，出现缺口</text>
</svg>

</div>

**为什么值得关心**

它推翻了 Artin 群的 CAT(0) 猜想，说明这类群的"好几何"应当到分类空间（拓扑层面）去寻找，而不是非正曲率的度量舞台。

> 已 Lean 形式化

## 一句话结论

显式构造了一个 116 个生成元、非对角标签仅含 `@@M@@2,3,\infty@@` 的 Artin 群（Artin group），证明它不容许任何非空真 CAT(0) 空间上真且余紧的等距作用，从而推翻了 Artin 群的 CAT(0) 猜想。

## 问题背景

CAT(0) 空间（三角比较意义下的非正曲率度量空间）是几何群论的基本舞台。Charney 提出问题：哪些 Artin 群是 CAT(0) 的；Haettel 进一步把"每个有限秩 Artin 群都在某个 CAT(0) 空间上有几何作用（真、余紧、等距）"记录为猜想。已有大量正面结果：右角 Artin 群有非正曲立方分类空间，Brady–McCammond 处理三个生成元全大型，Haettel 证明 XXL 型（有限标签均 `@@M@@\ge5@@`），`@@M@@B_5@@`、`@@M@@B_6@@`、`@@M@@B_7@@` 辫群也逐一被攻克。但 Brady–Crisp 的例子表明：在某一维数处出现的障碍，可能在更高维的 CAT(0) 空间中消失。因此真正的反例必须给出在任何维数都不消失的障碍——未知空间没有维数或组合结构可用，这是根本困难。

## 主要结果

主定理：存在 116 个生成元上的 Artin 矩阵 `@@M@@M@@`，非对角标签全在 `@@M@@\{2,3,\infty\}@@` 中（论文给出显式定义），使得 `@@M@@A_M@@` 没有任何几何 CAT(0) 作用；结论对所有非空真 CAT(0) 空间成立，不限维数、不限度量与胞腔结构。矩阵的具体约定是：`@@M@@m_{ab}=m_{bc}=m_{ca}=3@@`，三个辫块内部相邻标签为 3、其余为 2，`@@M@@d,e@@` 与 `@@M@@a,b,c@@` 的标签为 2，其余一切标签为 `@@M@@\infty@@`。这给出 CAT(0) 猜想的否定解答。

## 证明思路

构造分三层展开。核心小群是 `@@M@@T=\langle a,b,c\mid aba=bab,\ bcb=cbc,\ cac=aca\rangle@@`（三角形全 3 型）。先建长度工具：CAT(0) 等距变换有稳定平移长度（stable translation length）`@@M@@\ell(g)@@`；交换元素对 `@@M@@g,h@@` 配以配对 `@@M@@\langle g,h\rangle=(\ell(gh)^2-\ell(g)^2-\ell(h)^2)/2@@`，它在整个中心化子上可加且来自半正定二次型。再做辫群计算：在 `@@M@@40@@` 股辫群中取中心元链 `@@M@@Z_2=s_1^2@@`、`@@M@@Z_3=(s_1s_2)^3@@` 等，用中心化子特征与奇指标平方元的正性做算术，逼出不等式 `@@M@@\ell((uv)^3)/(3\ell(u^2))>1/2@@`（平方后 `@@M@@\ge143/513@@`）。把三个 `@@M@@B_{40}@@` 分别挂到 `@@M@@T@@` 的三对生成元上（各新增 37 个生成元），指数和同态 `@@M@@G\to\mathbb Z@@` 使平方元无限阶、稳定长度为正，于是三对辫关系全部满足该不等式。接着构造角度障碍：交换对 `@@M@@(a^2,(ab)^3)@@` 等六对在渐近意义下张出六个"扇形"，每个角 `@@M@@<\pi/3@@`，首尾相接总角 `@@M@@<2\pi@@`。为把这一角度矛盾在任意维数严格化，作者取 Digne 反射坐标同态的等边三角形特例作仿射镜像坐标，在大尺度下分离扇形盘的不交区域；CAT(0) 测地线提供第二个盘；将所得球面转移到 Brady–McCammond 型三角呈现复形上，局部环绕数（winding number）计数找到一个符号重数非零的目标三角形，而折叠论证又迫使所有重数为零，得出矛盾。最后组装大群：再添两个与 `@@M@@a,b,c@@` 交换、其余标签为 `@@M@@\infty@@` 的生成元 `@@M@@d,e@@`（共 `@@M@@3+3\cdot37+2=116@@` 个），经 amalgam 自由积的正规形引理证明 `@@M@@C_G(d)\cap C_G(e)=T@@`。若 `@@M@@G@@` 有几何作用，则 `@@M@@d,e@@` 的公共位移子水平集 `@@M@@Y@@` 闭凸且 `@@M@@T@@`-不变，中心化子引理（承 Ruane–Swenson）保证 `@@M@@T@@` 在 `@@M@@Y@@` 上作用几何、稳定长度不变，故 `@@M@@T@@` 继承三条辫不等式，与扇形障碍冲突。全程不使用任何 Artin 群球型性定理，只用到初等有限平面拓扑与环绕数。

## 可信度与备注

论文标注主结果已 Lean 形式化。本反例与族内两篇正面结果相映成趣：`@@M@@K(\pi,1)@@` 猜想与抛物交猜想成立，而 CAT(0) 猜想失效，说明 Artin 群的"好几何"应到分类空间层面寻找，而非非正曲几何层面。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇主结果已形式化，可信度较高。

{% endraw %}
