---
layout: default
title: "Computing the Random 3-SAT Threshold"
family: "235"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Computing the Random 3-SAT Threshold

> 结果族 235：Limiting random SAT thresholds, sharp variance and computability　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了均匀随机 3-SAT 的极限可满足性阈值（satisfiability threshold）\(\alpha_3\) 存在，且是可计算实数（computable real）：一台不用神谕、不带任何不可计算常数的确定性图灵机就能把它算到任意指定精度。

## 问题背景

随机 3-SAT 在 \(n\) 个变量中均匀选三个不同变量、独立公平地定号，抽 \(m\) 条独立子句，\(m/n\) 称为子句密度（clause density）。Mitchell–Selman–Levesque 1992 年的实验发现求解难度在"一半公式可满足"的密度附近激增，由此产生阈值猜想：存在临界密度，低于它公式渐近可满足，高于它渐近不可满足。Friedgut（1999，附 Bourgain 附录）证明了每个固定 \(k\ge3\) 都有陡峭相变（sharp transition），但相变中心可以随系统尺寸漂移，推不出极限存在。数值上，3.52（Kaporis–Kirousis–Lalas 2006）与 4.4898（Díaz 等 2009）从两侧夹住阈值，统计物理的空腔方法（cavity method）预言约 4.267；Ding–Sly–Sun（2022）对所有充分大的 \(k\) 证明了含数值的猜想，\(k=3\) 一直悬置。2026 年 10 月，Carenini 以 \(O_{k,\eta}(n^{1/2+1/k})\) 的多项式窗口对每个固定 \(k\ge3\) 确立了极限阈值的存在，论文明确把优先权归于她。本文处理下一步：即便极限存在，Specker（1949）早已构造出收敛到不可计算实数的可计算单调有理序列，所以"存在"并不自动等于"可算"。

## 主要结果

主定理分两层。第一，存在 \(\alpha_3\in(0,\infty)\)，使对每个固定实数 \(a\ge0\)，可满足概率 \(p(n,\lfloor an\rfloor)\) 在 \(a<\alpha_3\) 时趋于 1、在 \(a>\alpha_3\) 时趋于 0。第二，存在一台有限确定性图灵机，输入一元精度 \(1^r\) 即停机并输出有理数 \(q_r\)，满足 \(|q_r-\alpha_3|\le2^{-r}\)；机器不使用神谕（oracle）、建议（advice）或任何不可计算实常数。论文同时划清边界：\(a=\alpha_3\) 处的行为未知，不给运行效率界，也不断言 \(\alpha_3\) 等于 4.267 的物理预言。

## 证明思路

先把任务抽象成"证书搜索引理"：设有可计算有理序列 \(\ell_k\to\alpha\) 自下方逼近，另有一致可计算的测试值 \(G(a,\beta;Q)\)，\(Q\) 取自可有效枚举的有限描述，满足两条符号条件——\(G<0\) 蕴含 \(\alpha\le a\)，且每个有理 \(a>\alpha\) 都存在负值测试。对全部三元组 \((a,\beta,Q)\) 做鸽笼式公平搜索，每阶段多执行若干步，随时用下证书抬高区间左端、用负值测试压低右端，区间长度一旦不超过 \(2^{1-r}\) 就输出中点。停机论证只用到"两族证书终会被找到"，完全不需要有限尺寸收敛的速率——这正是绕开 Specker 障碍的关键。

概率侧先在松弛泊松模型（relaxed Poisson model，三个变量下标独立取样、允许重复）中计算，最后经细化（thinning）与泊松计数比较转移回原模型。令 \(T_0\) 为首个不可满足时刻，\(f_n=\E\min\{T_0,20n\}\)。核心是免费删除矩界：免费删去变量 \(v\) 换来的存活增量满足 \(\E[(F_r^{+v}-F_r)^{6/5}]\le2^{60}\)，且对删除额度 \(r\) 一致。证明沿用 Friedgut 半立方引理与 Carenini 顺序替换的残余集条件化（residual-set conditioning）思想：固定不含 \(v\) 的基底子句流后，含 \(v\) 的子句投影成两文字测试，而 \(d\) 个三文字测试替换一个两文字测试时"全部歼灭"的概率至多损失 \(1/d^2\)；再按残余集被消灭的概率二进分箱，未来基底流以几何速度歼灭各箱残余，逐箱积分后级数收敛，关键幂为 \(2-3p/2=1/5>0\)。随后按子句最小变量指标分桶、用 Doob 鞅得集中不等式，又以加权插值比较"两块独立公式"与"合并公式"的可满足概率——两种子句的消灭概率 \(\sum\lambda_ix_i^3\) 与 \((\sum\lambda_ix_i)^3\) 由 \(x^3\) 的凸性分出高下，再用品格函数展开把变量权重抹匀——得到次可乘不等式，进而 \(f_n\) 近似超可加，误差 \(O(n^{5/6})\)，故 \(f_n/n\) 收敛于 \(\alpha\) 且带单侧证书 \(\alpha\ge f_n/n-2^{67}n^{-1/6}\)；而 \(f_n\) 可一致计算——枚举全部子句列表与赋值、截断泊松尾即可——这就给出下证书序列。删除矩界另有一功：它保证超过 \(\alpha\) 后、以趋于 1 的概率任何赋值都违反多于 \(\epsilon n\) 条子句，于是软压强（soft pressure）\(P(a,\beta)=\lim n^{-1}\E\log Z_n\)（其中 \(Z_n=\sum_\sigma e^{-\beta H_n(\sigma)}\)）在某个整数惩罚 \(\beta\) 下严格为负。上证书由一族有限有理试验（trial）描述 \(Q\) 提供：插值方向留下非负余项 \((x-y)^2(x+2y)\)，给出 \(P\le G\)；反向恒等式 \(P=\inf_QG\) 则借助 Ghirlanda–Guerra 恒等式的高斯探测、Panchenko 超度量（ultrametricity）定理与 Austin–Panchenko 层次表示，把不同位点共享的随机变量逐层剥离为独立采样，最后用有理数表离散化。组装两族证书即得定理；证明中取子序列、选条件律等非有效步骤只用于保证有限见证存在，机器本身只搜索有限描述。

## 可信度与备注

本文主结果暂无形式化证明，OpenAI 官方声明未经形式化的结果可能有问题，请以社区核验为准。作为结果族 235 的可计算性成员，它与姊妹篇互为支撑：族内另一篇独立证明每个固定 \(k\ge3\) 的极限阈值存在并给出命中时方差（hitting-time variance）\(\Theta_k(n)\) 的尖锐估计，与本文共享删除矩界与压强符号机制；本文还证明所构造的 \(\alpha\) 与姊妹篇的 \(k=3\) 常数一致。Carenini 的优先权（ECCC TR26-229，2026 年 10 月 5 日公开）在摘要与引言中均被明确致谢。

{% endraw %}
