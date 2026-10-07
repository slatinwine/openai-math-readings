---
layout: default
title: "A directional zero–one law for finite-range-dependent random environments"
family: "220"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A directional zero–one law for finite-range-dependent random environments

> 结果族 220：Directional zero–one laws beyond iid environments and iid ballisticity　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
证明了 \(\mathbb{Z}^d\)（\(d\ge3\)）上平稳、遍历、有限程依赖（finite-range-dependent）且一致椭圆的环境中，最近邻随机游走沿任一固定非零方向逃逸的退火概率只能是 0 或 1，把此前仅在独立环境成立的方向 0-1 律推广到了相依环境。

## 问题背景
随机环境中的随机游走（random walk in random environment, RWRE）每到一个格点就按该点自带的转移概率跳步；重访同一格点会遇到同一组概率，这种环境的"记忆"使模型远比普通马尔可夫链难处理。1981 年 Kalikow 与 Sznitman–Zerner 的再生表述证明了符号并 0-1 律 \(P_0(A_\ell\cup A_{-\ell})\in\{0,1\}\)（\(A_\ell=\{X_n\cdot\ell\to+\infty\}\)），但它回答不了单一方向 \(P_0(A_\ell)\) 能否取 0 与 1 之间的值。二维情形由 Zerner–Merkl（2001）解决，其论证依赖平面上反向路径必然相交的几何；高维中这一几何失效，问题悬置多年。依赖性更使问题微妙：Bramson–Zeitouni–Zerner（2006）构造了平稳、多项式混合、一致椭圆的环境，游走竟以正概率沿两个相反方向逃逸。因此"独立性要多少才够"是实质问题，而有限程依赖正是自然的门槛；此前 Comets–Zeitouni、Rassoul-Agha、Guo 等在混合条件下只得到速度类结论，未判定两个逃逸事件的概率。

## 主要结果
环境测度 \(Q\) 需满足三条：(i) 平稳遍历（stationary ergodic）——平移不变且平移不变事件平凡；(ii) 一致椭圆（uniform ellipticity）——几乎所有环境中每步转移概率 \(\omega(x,e)\ge\kappa>0\)；(iii) 有限程依赖——对 \(\ell^\infty\) 距离超过固定 \(R\) 的任意确定性集合 \(A,B\)（包括无穷集合），由转移行生成的 \(\sigma\)-域 \(\mathcal F_A\) 与 \(\mathcal F_B\) 独立。主定理：在此假设下，对每个固定 \(\ell\in\mathbb R^d\setminus\{0\}\)（方向可无理），退火概率 \(P_0(A_\ell)\in\{0,1\}\)。证明只直接使用平稳性与有限程独立性，不借助独立标签表示，也不附加速度或再生时间矩条件。

## 证明思路
全文用反证法排除"两个相反符号以正概率共存"。先在固定方向上构造独立的再生段（regeneration pieces）：以新的高度记录结尾、此后路径永不再下穿该高度的有路径段；在"永不回退"条件下它们独立同分布，这说明正概率逃逸时两个符号穷尽。有限程依赖带来两个 iid 情形没有的障碍：不相交的路径可能使用相关的行，而已观察的路径会改变附近未观察行的条件分布。绕行的办法是把每个转移拆成两个固定权重的"标记"选择与一个剩余选择：一段预先写好的固定权重脚本不需要任何行信息就能走出依赖范围，把路径送进一片行真正独立的区域，在那里接上不再回落的延续；不同脚本互不重叠，保证再生段有唯一的拼接法则，端点处的条件化靠枚举有限前缀完成。接着证明共存迫使再生段有有限平均空间半径：一次很大的横向偏移会在倾斜方向产生新记录，用一张倾斜超平面和一个短标记连接器就能拼接一段反向符号的延续；反复构造会在互不相交的窗口内放入一致正概率，与游走最终方向上确界的分布矛盾。半径界进而给出两条相反的确定性极限射线，把一般实方向化归为坐标方向。最后把正、负两列独立再生段放入"对置排布"（opposed arrangement），接触（contact）指两条排布路径的出发格点距离不超过 \(R\)；公共再生高度把排布切成独立同分布的块。上界一边用桥（bridge，即按指定总宽条件化的再生段串）作比较、以有限空间矩控制侧向位移的熵，得到接触统计 \(m(J)=O(J/\log J)\)；下界一边用端点对齐与后验概率向量鞅（其运行最大值之和在端点个数的对数尺度上有指数尾），并把被停止的路径边缘律跨过"活动行间隙"转移，得到 \(m(J)\ge cJ/\log\log J\)。两个界不相容，矛盾完成证明。

## 可信度与备注
本文暂无形式化证明，请以社区核验为准。它与族内另两篇姊妹作互为支撑：作者明确说明本文沿用 iid 严格椭圆姊妹篇的"半径—接触"架构并完成有限程环境所需的全部改造；而弹道性一篇的推论又以严格椭圆 0-1 律为输入把"正概率瞬态"升级为"概率 1"。按 OpenAI 官方声明，未经形式化的结果可能有问题，本篇结论宜待同行评审与独立核验。

{% endraw %}
