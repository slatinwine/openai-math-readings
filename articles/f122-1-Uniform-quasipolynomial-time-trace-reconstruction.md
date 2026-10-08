---
layout: default
title: "Uniform quasipolynomial-time trace reconstruction"
family: "122"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Uniform quasipolynomial-time trace reconstruction

> 结果族 122：Quantitative trace-reconstruction bounds with a uniform decoder　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

想象一台爱漏拍的复印机:你把一条黑白珠链放进去,每次复印都随机丢掉几颗珠子,还不告诉你缺在哪。这篇论文造出一台"统一修复机":只要告诉它珠链长度和漏拍概率,它就能从足够多份残缺复印件里,把任意原始珠链又快又准地拼回来。

**关键词卡片**

- 轨迹(trace):原串每个比特以概率 `@@M@@p@@` 被保留、按原顺序拼出的"残缺复印件"。
- 删除信道(deletion channel):随机丢位的劣质信道,只交出剩下的比特。
- 拟多项式(quasipolynomial):`@@M@@2^{(\log n)^3}@@` 这类量级,比 `@@M@@2^n@@` 温和得多。
- 统一解码器(uniform decoder):同一台图灵机对所有长度与保留概率都适用,不必逐案重造。
- 半定矩松弛(semidefinite moment relaxation):把候选串的统计量放宽成半正定矩阵约束,用来系统排除错误候选。

**看个具体例子**

设原串 `@@M@@x=10110@@`、保留概率 `@@M@@p=1/2@@`。某次复印丢了第 1、4 位,轨迹是 `@@M@@010@@`;另一次丢了第 2、5 位,轨迹是 `@@M@@111@@`。单条轨迹残缺不全,许多条合起来就足以锁定 `@@M@@x@@`。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="280" y="26" text-anchor="middle" font-size="16" fill="#333">原串 x = 1 0 1 1 0(每位以概率 p = 1/2 保留)</text><circle cx="160" cy="72" r="20" fill="#fff" stroke="#333" stroke-width="2"/><circle cx="220" cy="72" r="20" fill="#fff" stroke="#333" stroke-width="2"/><circle cx="280" cy="72" r="20" fill="#fff" stroke="#333" stroke-width="2"/><circle cx="340" cy="72" r="20" fill="#fff" stroke="#333" stroke-width="2"/><circle cx="400" cy="72" r="20" fill="#fff" stroke="#333" stroke-width="2"/><text x="160" y="78" text-anchor="middle" font-size="15">1</text><text x="220" y="78" text-anchor="middle" font-size="15">0</text><text x="280" y="78" text-anchor="middle" font-size="15">1</text><text x="340" y="78" text-anchor="middle" font-size="15">1</text><text x="400" y="78" text-anchor="middle" font-size="15">0</text><line x1="200" y1="98" x2="166" y2="152" stroke="#c0392b" stroke-width="2.5"/><path d="M160,162 L170,155 L162,149 Z" fill="#c0392b"/><line x1="360" y1="98" x2="394" y2="152" stroke="#c0392b" stroke-width="2.5"/><path d="M400,162 L390,155 L398,149 Z" fill="#c0392b"/><circle cx="130" cy="198" r="18" fill="#f4ecf7" stroke="#c0392b" stroke-width="2"/><circle cx="180" cy="198" r="18" fill="#f4ecf7" stroke="#c0392b" stroke-width="2"/><circle cx="230" cy="198" r="18" fill="#f4ecf7" stroke="#c0392b" stroke-width="2"/><text x="130" y="204" text-anchor="middle" font-size="14">0</text><text x="180" y="204" text-anchor="middle" font-size="14">1</text><text x="230" y="204" text-anchor="middle" font-size="14">0</text><circle cx="330" cy="198" r="18" fill="#f4ecf7" stroke="#c0392b" stroke-width="2"/><circle cx="380" cy="198" r="18" fill="#f4ecf7" stroke="#c0392b" stroke-width="2"/><circle cx="430" cy="198" r="18" fill="#f4ecf7" stroke="#c0392b" stroke-width="2"/><text x="330" y="204" text-anchor="middle" font-size="14">1</text><text x="380" y="204" text-anchor="middle" font-size="14">1</text><text x="430" y="204" text-anchor="middle" font-size="14">1</text><text x="180" y="248" text-anchor="middle" font-size="14" fill="#c0392b">轨迹① 丢第 1、4 位 → 010</text><text x="380" y="248" text-anchor="middle" font-size="14" fill="#c0392b">轨迹② 丢第 2、5 位 → 111</text><text x="280" y="272" text-anchor="middle" font-size="13" fill="#666">许多条轨迹合起来,即可唯一锁定原串</text></svg>

</div>

定理的数字版:固定 `@@M@@p@@`,只需 `@@M@@\exp(C(\log n)^3(1+\log\log n)^6)@@` 条轨迹,这台机器就以至少 `@@M@@2/3@@` 的概率输出 `@@M@@x@@`,耗时同为拟多项式;若删除概率不超过 `@@M@@n^{-\varepsilon}@@`,轨迹数与时间都降为多项式。

**为什么值得关心**

此前人们只证明"这么多条轨迹在信息上够用",却造不出跑得快的算法;本文把样本界升级为一台真正可执行、对所有参数统一的解码器,跨过了删除信道研究的一道大门。

> 暂无形式化证明(AI 结果待核验)

## 一句话结论
论文为删除信道下的轨迹重构（trace reconstruction）造出单一"统一"解码图灵机：只要长度 `@@M@@n@@` 与有理保留概率 `@@M@@p@@` 已知，对每个固定 `@@M@@p@@` 用拟多项式条轨迹与拟多项式位复杂度即可重构任意二进制串，把此前只有样本界的结果升级为高效算法。

## 问题背景
删除轨迹（deletion trace）指对未知串每位以保留概率 `@@M@@p@@` 独立保留、依序拼接所得的序列：观察者看到比特，却不知其原位置。轨迹重构问：多少条独立轨迹才能还原最坏情形下任意 `@@M@@n@@` 长二进制串？问题由 Batu–Kannan–Khanna–McGregor（2004）正式提出。样本上界历经 `@@M@@\exp(\tilde O(\sqrt n))@@`、`@@M@@\exp(O(n^{1/3}))@@` 与 Chase 的 `@@M@@\exp(O(n^{1/5}\log^5 n))@@`，2026 年 BVW 终于给出拟多项式样本界 `@@M@@\exp(p^{-7/3}(\log_2 n)^{c_0})@@`。然而区分性统计量只给样本数、不给解码器：BVW 明确把拟多项式时间重构留作公开问题；极大似然虽只多耗 `@@M@@O(n)@@` 倍样本，枚举全部候选串代价巨大。卡点是把区分性统计量变成可高效执行的搜索。

## 主要结果
定理（统一轨迹重构）：存在绝对常数 `@@M@@C,c\ge1@@` 与一台随机多带图灵机 `@@M@@\mathcal A@@`，对每个 `@@M@@n\ge2@@`、有理 `@@M@@p\in(0,1]@@`、每个 `@@M@@x\in\{0,1\}^n@@`，在给定二进制的 `@@M@@n,p@@` 与独立轨迹预言机后，`@@M@@\mathcal A@@` 至多申请 `@@M@@M_C(n,p)=\lceil\exp(CB(n,p))\rceil@@` 条轨迹，以至少 `@@M@@2/3@@` 概率输出 `@@M@@x@@`，且对一切随机比特与轨迹流都在 `@@M@@(n+L+M_C(n,p))^c@@` 位操作内停机。这里 `@@M@@B(n,p)=p^{-1}(\log n)\mathsf X^2(1+\log\mathsf X)^6@@`，`@@M@@\mathsf X=1+\log n/(1+\log(1/q))@@`，`@@M@@q=1-p@@`，`@@M@@L@@` 为 `@@M@@p@@` 的分子分母总位长。固定 `@@M@@p@@` 时对数样本预算为 `@@M@@O_p((\log n)^3(1+\log\log n)^6)@@`，样本与时间皆拟多项式（quasipolynomial）；固定 `@@M@@\varepsilon>0@@` 且 `@@M@@q\le n^{-\varepsilon}@@` 时 `@@M@@B=O_\varepsilon(\log n)@@`，两者皆为多项式。同一台机器统一覆盖随 `@@M@@n@@` 变化、甚至逼近 `@@M@@0@@` 或 `@@M@@1@@` 的保留概率。

## 证明思路
桥梁是把"区分任意两串"升级为"对凸松弛族的分离"。解码器估计秩集 `@@M@@I@@` 上的轨迹可观测量 `@@M@@T_I@@`（指定迹秩上比特乘积的期望，可由经验平均得到）。对候选前缀 `@@M@@u@@` 引入正矩泛函（positive moment functional）：剩余位置的符号矩列满足矩矩阵半正定——这是 Lasserre/Parrilo 半定矩与平方和框架的布尔特例，可行阵列不必来自真实分布。核心分离定理：若 `@@M@@u@@` 的首个错误位为 `@@M@@d@@`，则任何固定 `@@M@@u@@` 的正矩泛函必有某个低阶 `@@M@@T_I@@` 偏差超过 `@@M@@\exp(-C_{\rm sep}B(n,p))@@`。于是准确的经验统计即可排除一切错误前缀，无需搜索完整字符串空间。

分离本身是多尺度传播。先在位 `@@M@@d@@` 拿到 `@@M@@\Delta[X_d]=\pm1@@` 的局部信号，再用带指数衰减相位权重的元组特征 `@@M@@f_j@@` 与按末位索引的信号 `@@M@@\mathcal S_f(s,\omega)@@` 逐尺度推进：降低衰减与频率，同时保住可检测偏差。两个关键点使传播与凸松弛兼容。其一，半正定性把多项式矩变成内积：沿 `@@M@@J@@` 条向量链的 telescoping 误差界 `@@M@@O(J^2\xi)@@`，配以 Cauchy 密度配对，强制出总频率小且可检测的乘积。其二，Gauss 围道形变把乘积折回衰减与频率都更小的元组统计量，生成树给新间隔分配互异的边以控制系数质量。最后经信道代入 `@@M@@z=q+pw@@` 的生成函数恒等式（把迹间隙参数的单位圆盘映入输入圆盘 `@@M@@|z-q|\le p@@`）把输入统计换成迹统计——算法无需搜索任何解析见证。

解码侧逐位推进：从空前缀出发测试两个一位延拓。正确前缀把真矩与独立均匀符号按小权重 `@@M@@\zeta/8@@` 混合，得到严格松弛（矩矩阵 `@@M@@\succeq(\zeta/8)\mathrm{Id}@@`），于是 Agmon–Motzkin–Schoenberg 型投影松弛迭代配二进网格舍入，必在固定步数内找到可行矩系；错误前缀被分离定理否决。Chebyshev 不等式加联合界保证经验估计集中概率至少 `@@M@@31/32@@`，归纳得输出恰为 `@@M@@x@@`；全程至多 `@@M@@2n@@` 次可行性测试、纯有理运算，给出位复杂度界。

## 可信度与备注
主结果暂无形式化证明，OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。族内三篇互为支撑：姊妹篇先证得同型拟多项式样本界，本文把相应分离强化到半定矩松弛并落实为统一算法；下界篇证明固定删除概率需要 `@@M@@n^{\Omega(\log\log n)}@@` 条轨迹，说明拟多项式量级已接近必要。

{% endraw %}
