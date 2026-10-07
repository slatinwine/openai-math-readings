---
layout: default
title: "Simulating One-Tape Time in Two-Fifths-Power Space"
family: "137"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Simulating One-Tape Time in Two-Fifths-Power Space

> 结果族 137：One-tape time simulation in two-fifths-power space　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

一台固定的单可写带图灵机在时间 `@@M@@T@@` 内的停机与状态结果，可用 `@@M@@\widetilde O(T^{2/5})@@` 个工作比特（模拟时间不限）确定性算出，首次把单带模拟的空间指数从经典的 `@@M@@1/2@@` 压到 `@@M@@2/5@@`，肯定回答了 Williams 的公开问题。

## 问题背景

模拟一台图灵机时，若允许模拟器跑任意久、只计较工作空间，需要多少比特？经典答案归于 Hopcroft 与 Ullman（据 Williams 的综述）：单条读写带的机器跑 `@@M@@t@@` 步，`@@M@@O(\sqrt t)@@` 空间就够。2025 年 Williams 借助 Cook–Mertz 的树求值算法（tree evaluation；Goldreich 2024 以一元插值与全局存储给出阐释）证明多带机器的时间 `@@M@@t(n)@@` 可用 `@@M@@O(\sqrt{t\log t})@@` 空间模拟，并在全文第 5 节问：单带情形的平方根指数能否被某个固定正常数压低？本文对该模型给出肯定回答，并说明多带情形为何另有障碍。

## 主要结果

主定理：固定一台确定性机器，带单条可写带（writable tape）与一个磁头，可另配固定数目的只读输入头（read-only input heads），所有磁头每步至多移动一格、起点固定；初始符号由一个固定访问器（accessor）以 polylog 空间按需读出。对满足该访问条件（access condition）的输入 `@@M@@x@@` 与二进制时间上限（time cap）`@@M@@T\ge2@@`，机器在 `@@M@@T@@` 步内的有限控制与停机结果（finite-control and halting outcome）可用 `@@M@@\widetilde O(T^{2/5})@@` 个工作比特确定性求出；模拟时间不设限，最终带内容无需落地。若机器在 `@@M@@t@@` 步后自行停机，倍增上限 `@@M@@2,4,8,\ldots@@` 即得 `@@M@@\widetilde O((t+2)^{2/5})@@` 空间。对任何固定 `@@M@@\delta<1/10@@` 这就是 `@@M@@O(T^{1/2-\delta})@@`，正合 Williams 问题所求。推论（层级分离）：对空间可构造的 `@@M@@s(n)\ge n@@` 与固定 `@@M@@0<\epsilon<5/2@@`，`@@M@@\mathrm{DSPACE}(s)\not\subseteq\mathrm{TIME}_{1w,\mathrm{ro}}(s^{5/2-\epsilon})@@`，即单带时间 `@@M@@s^{5/2-\epsilon}@@` 分辨不出全部 `@@M@@\mathrm{DSPACE}(s)@@` 语言。

## 证明思路

第一步，分块（block）与访问（visit）。把可写带按宽度 `@@M@@b@@`、偏移 `@@M@@a@@` 切块。每步至多跨过一个边界，`@@M@@b@@` 个偏移的跨界总数不超过 `@@M@@T@@`，故存在好偏移只需 `@@M@@T/b@@` 次块访问；逐个试遍偏移即可，全程不存块地址转录。每次访问从磁头进块到离块，局部演化只碰这一个块；访问之间传递的只是短控制器（controller：状态、各头位置、时刻与终止标志，共 `@@M@@c=O(\log T)@@` 比特）。关键观察：一旦控制器序列固定，每个块的演化只由该块初始内容决定，一致性检查遂按块分解。

第二步，纪元（epoch）与轮（round）。把 `@@M@@b@@` 次访问组成一个纪元，共 `@@M@@E=O(1+T/b^2)@@` 个；纪元内再按 `@@M@@k=\sqrt b@@` 次访问一轮地补齐转录。整段纪元转录加任一块装进宽 `@@M@@d=O((b+1)\log T)@@` 的字里。轮更新是分解式规则（factored rule）：猜测接下来 `@@M@@k@@` 个控制器（`@@M@@g=kc@@` 比特），对每个块用重放（replay）核验，语义上恰有一个猜测全票通过，于是新历史满足特征 2 域上的多项式恒等式 `@@M@@H'=\sum_Y\overline{G_Y(H)}\prod_i P_{Y,i}(H,A_i)@@`，其中 `@@M@@A_i@@` 是纪元边界处的块检查点（checkpoint）。

第三步，带权求值引擎，即可复用的核心引理（weighted evaluation）。沿用 Cook–Mertz 共享寄存器思想：过程 `@@M@@\Add(V,\lambda,t)@@` 从任意寄存器初值出发，把 `@@M@@\lambda\bar v(V)@@` 加到第 `@@M@@t@@` 个寄存器并复原其余寄存器，使子调用可直接借用父辈的输入与部分累计输出。实现上先用齐次查表延拓（homogeneous lookup extension）把布尔局部函数变成对每个变元分别 `@@M@@d@@` 次齐次的多项式，再用插值权重 `@@M@@\omega_L(s)@@` 提取代换 `@@M@@a+sv@@` 后的最高次系数；特征 2 域由二次扩张 `@@M@@X^2+X+a@@` 逐层均匀构造，次数超过特征数也无妨。

第四步，加权栈记账。普通依赖边权重 1，历史到检查点数组的边权重 `@@M@@g+1=kc+1@@`，对应悬挂帧里留住的轮猜测。但进入数组字必通往前一纪元，故任一递归路径每个纪元至多保留一个轮猜测，路径总权重 `@@M@@O(Ek)@@`。合计空间 `@@M@@\widetilde O(b+Ek)=\widetilde O(b+(1+T/b^2)\sqrt b)@@`，在 `@@M@@b\asymp T^{2/5}@@` 处平衡，得 `@@M@@\widetilde O(T^{2/5})@@`。末节还证明：只调块宽、纪元长、轮长这三个尺度，该构造的平衡点不会低于 `@@M@@2/5@@` 指数。

## 可信度与备注

本文主结果暂无形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。论文内部支撑较完整：同文给出多带对照命题（固定多带机仍只有 `@@M@@\widetilde O(\sqrt T)@@`，并指出读两个带的联合转移 `@@M@@\{00,11\}@@` 无法按块分解的具体障碍）与层级分离推论。但对数因子未去除，也未宣称 `@@M@@2/5@@` 是无对数端点或对一般多带机成立。

{% endraw %}
