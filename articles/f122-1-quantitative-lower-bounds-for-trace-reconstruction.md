---
layout: default
title: "Quantitative lower bounds for trace reconstruction"
family: "122"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Quantitative lower bounds for trace reconstruction

> 结果族 122：Quantitative trace-reconstruction bounds with a uniform decoder　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
论文证明：对每个固定删除概率 \(q\in(0,1)\)，即使计算不限、成功概率只需固定正值，精确重构任意 \(n\) 长二进制词需要 \(n^{\Omega(\log\log n)}\) 条轨迹，否定"多项式样本足够"的猜想；一般地当 \(q^3\log n\to\infty\) 时下界为 \(n^{c\log(q^3\log n)}\)。

## 问题背景
轨迹重构（trace reconstruction）的下界长期大幅落后于上界。Batu–Kannan–Khanna–McGregor（2004）提出问题时勾勒了固定删除概率下线性样本的障碍；McGregor–Price–Vorotnikova 分析零背景中单个 1 的位移；Holden–Lyons 证明 \(\Omega(n^{5/4}/\sqrt{\log n})\)，Chase 改进到 \(\Omega(n^{3/2}/\log^7 n)\)——都停留在多项式量级。上界侧 BVW（2026）已给出拟多项式样本界，"固定删除概率下多项式条轨迹是否足够"成为核心悬案。本文给出否定回答：任何固定 \(q\) 都超多项式。定理二更证明：固定 \(q\) 时两个不同 \(n\) 长词的轨迹律的最小总变差（total variation）衰减快于任何多项式。

## 主要结果
以 \(T_{q,s}(n)\) 记以概率至少 \(s\) 重构每个 \(x\in\{0,1\}^n\) 所需的最小轨迹数（估计器可随机、计算不限）。定理一（定量样本下界）：固定 \(s\in(0,1]\) 与 \(0<c<1/(4\log2)\)，沿一切 \(n\to\infty\)、\(q\in(0,1)\) 且 \(q^3\log n\to\infty\) 的实例列，最终有 \(T_{q,s}(n)\ge n^{c\log(q^3\log n)}\)（对数均为自然对数）。固定 \(q\) 时 \(\log(q^3\log n)\asymp\log\log n\)，即 \(n^{\Omega(\log\log n)}\)。定理二（单轨迹超多项式不可区分）：对每个固定 \(q\in(0,1)\) 与每个 \(A>0\)，有 \(n^A\min_{x\ne y}\mathrm{TV}(\mathcal D_q(x),\mathcal D_q(y))\to0\)，且同一信道下 \(T_{q,s}(n)/n^A\to\infty\)。

## 证明思路
先做信道归约：工作删除率取 \(\delta=\min(q,1/2)\)，令 \(H_{\rm del}=\delta^3\log n\)；在 \(\delta\) 处证明的不可区分性上界，经对存活比特再删除即传递到请求信道 \(q\)。证明是跨约 \(D\approx(1-\zeta)\log H_{\rm del}/(B\log2)\) 个尺度的归纳：目标长度按 \(N_{i-1}=N_i^{a_0(b_i)}\) 自 \(n\) 向下收缩，得分指数 \(d_i\) 每块增长 \((b_i-1)/4-0.05\)（前 \(5\cdot2^B\) 个深度 2 预备块把种子指数从 2.20 抬到所需强度）。归纳不变量（level invariant）同时维护：一对等长词 \(x_i,y_i\) 与辅助律 \(\mu_i,\nu_i\)，使某个马尔可夫核把辅助律投影到真轨迹律且 TV 误差每级不超过 \((i+1)\Delta\)；似然得分 \(d\nu/d\mu-1\) 的 \(L^{r_i}\) 范数平方不超过 \(N_i^{-d_i}\)；以及 \(x_i\) 连缀 \(k\) 次与 \(k+1\) 次的轨迹律有共同质量至少 \(\omega\)。

构造机制是"在多个尺度上隐藏位置差异"。基石是精确共同质量：同一词连缀 \(k\) 与 \(k+1\) 次后的轨迹律共享质量 \(\omega\)；把这样一对游程放在中央段两侧、以公平比特选朝向，联合轨迹律便含质量 \(\omega^2\) 的乘积分量，其上朝向仍公平，许多独立对留下中央段位置的二项不确定性；边际化朝向后恰好还原两侧轨迹律之积，故把固定词各段的独立真迹连缀就能精确复原其轨迹律——这就是"辅助观察近似真迹"的来源。两词的中央段取互补的 Prouhet–Thue–Morse 型带符号模式，其生成多项式在 \(1\) 处高阶为零，与宽二项偏移卷积后极小（与 HMPW 的二进符号递归同源）。系数沿嵌套段树展开后，互补词的根类型为 \(\pm1\)，相减消去一切偶根项；奇根项若不含"单活跃孩子"，就被迫包含 \(2^b\) 片叶的完全二叉子树，带来 \(2^b\) 个旧得分因子、保住衰减 \(N^{-d}\)，而兄弟组的共享位移加独立位移再摊开后代位置，额外贡献 \(N^{-(b-1)/4}\) 的衰减。收尾用 Hellinger 张量化：\(\mathrm{TV}(\mathrm{Tr}(x)^{\otimes m},\mathrm{Tr}(y)^{\otimes m})\le\sqrt{mN^{-d}}+2mE\)，要它小于常数必须 \(m\ge n^{c\log(q^3\log n)}\)；经转移与按长度填充即得两个定理。归纳还须核查：种子对随 \(q\) 减小一致有效、块数增长时常数不越过尺度裕度、一切条件化与失败布局的损失计入不变量误差。强迫二叉子树与位移摊开的技术细节论文展开极长，此处从略。

## 可信度与备注
主结果无 Lean 形式化证明，OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。与族内上界两篇的关系：BVW 型拟多项式上界的对数是 \(\log n\) 的固定幂，本下界在固定信道下的对数量级为 \((\log n)(\log\log n)\)，两侧仍有缺口。多项式可能性被否定后，姊妹篇的拟多项式样本上界与"统一拟多项式时间"篇的解码器便是当前最佳答案；低删除率 \(q\le n^{-1/3-\varepsilon}\) 下的多项式时间重构落在本文体制 \(q^3\log n\to\infty\) 之外，并不矛盾。

{% endraw %}
