---
layout: default
title: "Quenched SLE Universality for Weakly Disordered FK–Ising Interfaces"
family: "223"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Quenched SLE Universality for Weakly Disordered FK–Ising Interfaces

> 结果族 223：Random-cluster interfaces: critical, disordered, thermal, and natural-time scaling　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

磁铁游戏升级：这次每条边的"连接强度"被随机微调——有的边略强、有的略弱，像材料里撒进杂质。直觉担心这些杂质会搅乱分界线的形状。这篇论文证明：只要别调得太狠，分界线根本不在乎杂质，最终仍是原来那条随机曲线 SLE₁₆/₃——普适性对随机缺陷是稳定的。

**关键词卡片**

- FK–Ising 模型（FK–Ising model）：随机簇框架取 q=2，等价于研究磁铁的连通几何。
- 键无序（bond disorder）：每条边独立地取强度 1+ε 或 1−ε 的随机微调，ε 是杂质浓度。
- 淬火（quenched）：先把一套随机杂质固定住、再采样曲线——比"对杂质取平均"更严的要求。
- 临界逆温（critical inverse temperature）：无序模型自己的临界点，方程 `@@M@@(e^{2\beta_c(1+\varepsilon)}-1)(e^{2\beta_c(1-\varepsilon)}-1)=2@@` 的唯一解。
- 普适性（universality）：微观细节（此处是杂质）不影响宏观极限的现象。

**看个具体例子**

取 ε=0.1：一半边强度 0.9、一半 1.1，且这个"不完美程度"固定，不随格子变细而消失。定理说只要 ε 足够小，无论哪一套具体的杂质实现，条件曲线律都收敛到同一个 `@@M@@\mathrm{SLE}_{16/3}(D;a,b)@@`。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="20" y="24" font-size="15" fill="#333">无杂质与固定杂质的界面 → 同一条极限曲线</text>
  <rect x="60" y="50" width="180" height="180" fill="#f7f7f7" stroke="#333" stroke-width="2"/>
  <text x="100" y="40" font-size="14" fill="#333">均匀强度</text>
  <line x1="80" y1="90" x2="80" y2="190" stroke="#9bb" stroke-width="1"/>
  <line x1="110" y1="70" x2="110" y2="210" stroke="#9bb" stroke-width="1"/>
  <line x1="140" y1="80" x2="140" y2="200" stroke="#9bb" stroke-width="1"/>
  <line x1="170" y1="75" x2="170" y2="205" stroke="#9bb" stroke-width="1"/>
  <line x1="200" y1="85" x2="200" y2="195" stroke="#9bb" stroke-width="1"/>
  <path d="M60,230 C90,205 105,170 130,160 C160,148 150,110 185,100 C205,94 215,80 240,50" fill="none" stroke="#c33" stroke-width="3"/>
  <rect x="320" y="50" width="180" height="180" fill="#f7f7f7" stroke="#333" stroke-width="2"/>
  <text x="345" y="40" font-size="14" fill="#333">随机强弱边（ε 固定）</text>
  <line x1="340" y1="90" x2="340" y2="190" stroke="#9bb" stroke-width="2.5"/>
  <line x1="370" y1="70" x2="370" y2="210" stroke="#9bb" stroke-width="1"/>
  <line x1="400" y1="80" x2="400" y2="200" stroke="#9bb" stroke-width="2.5"/>
  <line x1="430" y1="75" x2="430" y2="205" stroke="#9bb" stroke-width="1"/>
  <line x1="460" y1="85" x2="460" y2="195" stroke="#9bb" stroke-width="2.5"/>
  <path d="M320,230 C350,208 362,172 390,162 C418,152 412,112 445,102 C462,96 475,80 500,50" fill="none" stroke="#c33" stroke-width="3"/>
  <text x="20" y="262" font-size="14" fill="#333">两图极限同为 SLE₁₆/₃：杂质不改变宏观形状（细线=弱边，粗线=强边）</text>
</svg>

</div>

**为什么值得关心**

二维 Ising 恰处于 Harris 判据的边缘情形，物理界争论随机耦合是否产生对数修正数十年；本文给出第一个固定强度无序下的整条界面严格收敛结果。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
证明带固定强度、对称二值键无序的临界 FK–Ising 界面仍收敛到 chordal `@@M@@\SLE_{16/3}@@`：无序强度不随网格变小，收敛对环境取 quenched 意义（依概率成立），确认 SLE 普适性对随机耦合稳定。

## 问题背景
纯临界 FK–Ising 的 Dobrushin 界面收敛到 `@@M@@\SLE_{16/3}@@`，由 Chelkak–Duminil-Copin–Hongler–Kemppainen–Smirnov 于 2014 年证明。自然的问题是：这种临界几何对随机扰动稳定吗？Harris 判据指出二维 Ising 恰处边缘（marginal）情形，比"严格无关"的扰动更微妙；物理上有 Dotsenko–Dotsenko、Shalaev、Ludwig 关于弱随机键对数修正的微扰研究。严格结果方面，Avérous–Mahfouf 近期得到的是无序随观测尺度减弱的近临界交叉估计；固定强度无序下的整条界面定律此前没有结果。困难有二：探索界面产生随机裂缝边界，条件交叉概率必须在剩余域中比较；已有的 quenched 界只对固定物理尺度成立，环境收敛没有速率，无法对所有微观域或所有裂缝历史做并集界。

## 主要结果
定理（Theorem thm:main）：存在 `@@M@@\eps_0>0@@`，使得对每个固定 `@@M@@0<\eps<\eps_0@@`、每个有界标记 Jordan 域 `@@M@@(D;a,b)@@` 及任意确定性方格逼近，键 `@@M@@e@@` 的耦合取 `@@M@@J_e=1+\eps\xi_e@@`（`@@M@@\xi_e@@` 独立、等概率取 `@@M@@\pm1@@`），温度取该无序模型的临界逆温 `@@M@@\beta_c(\eps)@@`——由加态磁化阈值定义，论文证明它是 `@@M@@(e^{2\beta_c(1+\eps)}-1)(e^{2\beta_c(1-\eps)}-1)=2@@` 的唯一解，键几率恰为 `@@M@@v_e=\sqrt2\,e^{\theta\xi_e}@@`。在此律下以 wired/free Dobrushin 边界条件采样探索界面 `@@M@@\gamma_n@@`，则其条件曲线律 `@@M@@\mu_{n,\xi}@@` 在 bounded-Lipschitz 度量下依环境概率 `@@M@@\P_{\mathrm{env}}@@` 收敛到 `@@M@@\SLE_{16/3}(D;a,b)@@`。要点有三：环境固定后再采界面（quenched 而非平均）；无序强度 `@@M@@\eps@@` 固定、不随网格 `@@M@@\delta_n\downarrow0@@` 减小；`@@M@@\eps_0@@` 与域及逼近无关，且结论覆盖含终点段在内的整条有向曲线。

## 证明思路
论文依赖配套重整化文稿的两个输入：临界点识别，与一个体内（bulk）扰动趋于零的局部尺度变换；本文要补的是三块。第一块把配分函数比较推广到固定多边形的边界附近：体内对称性带来的相消在边界处失效，改用纯 Ising 传递矩阵估计——沿直边相关投影距离以尺度比的平方衰减，平方衰减使边界胞的误差可求和；在有限个角点与边界条件变换处，任何正衰减指数即可。第二块处理探索后的裂缝域：先固定环境，从任意网格子列抽出确定性进一步子列，使一个可数"库存"中的所有多边形都有纯极限、可数稠密族中的环形屏障几乎必然成立，从而得到臂界与探索历史的紧性。再把裂缝域在有限个边界入口附近穿孔并提升到万有覆盖（universal cover）上：覆盖上的多边形仍有普通方格坐标，每条提升边携带其投影边的无序，而独立性只在单张单射图内使用；精心选择的横截线即使在裂缝边界附近也控制共形坐标，小规模删边把可能交叉的中段限制在覆盖的紧部，用库存中的固定多边形检验。若条件测试失败，紧性给出收敛的失败历史列，覆盖构造从中产出库存里的某个固定多边形，与其已知极限矛盾——于是几何可以在历史之后选择，而最终测试在网格极限之前固定，全程不需要任何统一速率。第三块识别曲线：沿用姊妹篇的"有界鞅测试"策略，在自由边界插入短 wired 区间，open-cap 四变换律下条件配对概率是精确鞅；先在固定区间长度时取网格极限、换成有界 Loewner 表达式、再与原 Dobrushin 律比较、最后缩小区间，得 `@@M@@M_{n,t}(x)=(xg'_{n,t}(x)/(g_{n,t}(x)-W_n(t)))^{1/2}@@`（`@@M@@q=2@@` 故幂为 `@@M@@1/2@@`）是一致近似鞅；两个测试点识别 Loewner 驱动为 `@@M@@\sqrt{16/3}@@` 布朗运动。尖端从正共形高度的一致逼近（停止时刻版"小门"论证）加上目标处的不回返界，把驱动收敛升级为曲线度量下的收敛。

## 可信度与备注
本篇暂无形式化证明，请以社区核验为准。证明依赖配套文稿的临界点识别与尺度变换（体内部分），以及姊妹篇的绘图、闭合比较与鞅识别框架；均匀概率输入全部换成此文证明的 quenched 估计。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
