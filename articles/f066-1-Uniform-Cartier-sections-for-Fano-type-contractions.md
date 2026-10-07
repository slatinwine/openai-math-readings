---
layout: default
title: "Uniform Cartier sections for Fano type contractions"
family: "066"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Uniform Cartier sections for Fano type contractions

> 结果族 066：Bounded klt complements for Fano contractions　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了 Birkar–Shokurov 的 Cartier 除子猜想：`@@M@@\epsilon@@`-lc 的 Fano type 收缩过任一指定基点，都能取到经过该点的 Cartier 除子，其拉回的 log canonical threshold 有只依赖维数 `@@M@@d@@` 与 `@@M@@\epsilon@@` 的下界；有理边界在特征零成立，实边界在 `@@M@@\mathbb C@@` 上成立。

## 问题背景

给一个奇异簇，能否过指定闭点选一条 Cartier 超曲面，使其 log canonical threshold (LCT) 有远离零的一致下界？对 Fano type 收缩 `@@M@@f\colon X\to Z@@`，整体版本要求在基上找一条过 `@@M@@z@@` 的超曲面，使拉回沿整根纤维奇异性受控。障碍集中在一个比值：若 `@@M@@D@@` 的局部方程为 `@@M@@g@@`，添加边界 `@@M@@t f^*D@@` 保持 log canonical 需要对一切素除子 `@@M@@E@@` 满足 `@@M@@t\le a(E;X,B)/\operatorname{ord}_E(f^*g)@@`，而差异下界本身控制不了分母的阶——光滑曲线上 `@@M@@m[z]@@` 的阈值只有 `@@M@@1/m@@`。Birkar 与 Shokurov 猜想断言对 `@@M@@\epsilon@@`-lc 的 Fano type 收缩存在一致下界。此前已知加权爆破情形（Sankaran–Santos）、环面情形（Ambro）与曲线基情形（Birkar）；Chen 证明了决定性约化——有界 klt 补、Cartier 截面陈述与其恒等收缩情形彼此等价——并解决基底维数不超过 2 的情形，本文补上一般情形。

## 主要结果

定理一（一致 Cartier 截面）：对每个 `@@M@@d>0@@` 与 `@@M@@\epsilon>0@@` 存在 `@@M@@\tau(d,\epsilon)>0@@`，使得任何 `@@M@@\epsilon@@`-lc 有理对 `@@M@@(X,B)@@`（`@@M@@\dim X=d@@`）配上 Fano type 收缩 `@@M@@f\colon X\to Z@@`（拟投影、`@@M@@\dim Z>0@@`、`@@M@@-(K_X+B)@@` 相对 nef），对每个闭点 `@@M@@z\in Z@@` 都有邻域 `@@M@@U@@` 与 `@@M@@U@@` 上非零有效 Cartier 除子 `@@M@@D@@`，`@@M@@z\in\operatorname{Supp}D@@`，使 `@@M@@(f^{-1}(U),\,B|_{f^{-1}(U)}+\tau f^*D)@@` 为 log canonical。常数不依赖 Cartier 指标、边界分母与极化选择，但非有效，除子与邻域可随例子变化。推论：`@@M@@\mathbb C@@` 上同结论对有效实边界 `@@M@@B@@` 成立。定理二（双有理 klt 补）：存在 `@@M@@n(d,\epsilon)@@`，对每个 `@@M@@\epsilon@@`-lc 有理 Gorenstein 簇 `@@M@@X@@` 上的双有理 Fano type 收缩（`@@M@@-K_X@@` 相对 nef），在 `@@M@@z@@` 附近有有效有理除子 `@@M@@\Delta@@` 使 `@@M@@(X,\Delta)@@` klt 且 `@@M@@n(K_X+\Delta)@@` Cartier、线性平凡。由 Chen 等价，定理二推出定理一及有限有理系数补陈述。

## 证明思路

反证定理二失败。Birkar 的相对 lc 补定理先给出固定指标 `@@M@@b=b(d)@@`，于是可取一列没有 klt `@@M@@M_i@@`-补的反例，`@@M@@M_i\to\infty@@` 且每个固定正整数最终整除 `@@M@@M_i@@`（取阶乘式序列即可）。先经 `@@M@@K@@`-MMP 取 crepant ample model 把 `@@M@@-K_X@@` 化为相对丰富，保持全部差异与失败性。

再做饱和：在反例的完备截面系统中找到一个本原除子赋值 `@@M@@w@@`，其中心含指定点，满足对一切 `@@M@@k\mid M_i@@` 次截面有 `@@M@@w(\Delta_s)\ge kA_X(w)@@`、在 `@@M@@b@@` 次补截面处取等；取几何一般切片把中心化为闭点。

然后把数据搬到带循环群作用的 klt 芽上：`@@M@@f@@` 局部同构时取典范覆盖 (canonical cover) `@@M@@t^r=c^{-1}@@`；否则取带号反典范挠子 (signed anti-canonical torsor) `@@M@@R=\bigoplus_{k\in\mathbb Z}H^0(X,\mathcal O_X(-kK_X))t^k@@`，其负半代数的有限生成要靠 `@@M@@K@@`-MMP 与半丰富收缩。"衬垫"引理添加 `@@M@@b-1@@` 个坐标，使无零除子的典范生成元与函数 `@@M@@h=a_0s_bt^b+\sum a_ju_j^b@@` 具有同一特征 (character)，商的差异间隙得以保持；由此得到中心拟单项赋值 `@@M@@T@@` 满足 `@@M@@A_S(T)=T(h)=1@@`，且每个固定特征 `@@M@@\chi^m@@` 的一切正则半不变量 (semi-invariant) 最终都有 `@@M@@T(s)\ge m@@`。

最后是钉扎障碍 (pinning obstruction)：这样的序列不可能存在。把截面除以 `@@M@@h@@` 的幂得不变比值 `@@M@@Y=s/h^m@@`，其值恰为 `@@M@@T(s)-m@@`；用一对取相反符号值的比值从两侧强加不等式，锁定 `@@M@@T(Y)=0@@`。在公共 lc 切片 `@@M@@\mathcal Q=\{v:A(v)=v(h)=1,\ v(F_j)\ge m_j\}@@` 上以允许高度 (allowed height) 极小化；关键在于把约束极小值精确实现为小扰动 klt 对的普通正规化体积极小值，从而可用稳定退化得到有限生成的中心代数。归纳的每一步要么产出新的代数无关变量——被维数封顶——要么剩余特征方向给出商上差异任意小的素除子——被商的 `@@M@@\epsilon@@`-lc 间隙排除；两条出路都被堵死，矛盾。最后经 Chen 等价与换域引理（点理想阈值与一般 Cartier 除子的互相转换、下降到可数子域再嵌入 `@@M@@\mathbb C@@`）完成两个定理与实边界推论。

## 可信度与备注

主结果暂无形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。姊妹篇《Bounded klt complements for Fano contractions》从反典范锥与正特征迹估计出发，独立证明了同一猜想的补方向，本篇则独立给出双有理 klt 补，两篇经 Chen 等价互相支撑。证明还依赖 Birkar 的 BAB 与 Calabi–Yau 有界性、有效双有理性、Filipazzi 的广义典范丛公式及 normalized volume 理论等外部结果，正确性以这些文献为前提。

{% endraw %}
