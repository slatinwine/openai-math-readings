---
layout: default
title: "An infinite finitely presented residually finite 2-group"
family: "247"
discipline: "Group theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | An infinite finitely presented residually finite 2-group

> 结果族 247：An infinite finitely presented residually finite 2-group and a finitely presented nil algebra　·　学科：Group theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明姊妹篇构造的无限、有限呈现的周期群 \(\Gamma=\mathop{\mathrm{St}}\nolimits_{12}(R)\) 是剩余有限的：其有限指标子群 \(G\) 中每个元素的阶都是 \(2\) 的幂，得到首个兼具"普通有限呈现＋剩余有限＋纯 \(2\)-挠"的无限群，把有限呈现 Burnside 问题的否定回答又推进一层。

## 问题背景

1902 年 Burnside 问：有限生成的周期群（periodic group，每元有限阶）是否必有限？Golod（1964）与 Grigorchuk（1980）先后造出无限的反例，且都是剩余有限（residually finite，即可用有限商区分任意非单位元）的；但 Grigorchuk 群并非有限呈现（finitely presented），而"无限周期群能否有普通有限呈现"被 Ol'shanskii–Sapir（2003）明确列为公开问题（他们构造的有限呈现挠群都带无限循环商，本身不周期）。又由 Zel'manov 对限制 Burnside 问题（restricted Burnside problem）的解答，有限生成、剩余有限且指数有界的群必有限，故所求群的元素阶必然无界。姊妹篇已造出无限有限呈现的周期群，本文在其上补齐剩余有限性与纯 \(2\)-幂挠这关键一步。

## 主要结果

主定理：存在无限、剩余有限、具普通有限呈现的群，其中每个元素的阶都是 \(2\) 的幂（文中称 2-group，群本身可以无限）。其元素阶必然无界，且所有有限商都是有限 \(2\)-群（由 Cauchy 定理，奇素数不能整除其阶）。

具体实现：设 \(R=\mathbb F_2\oplus I\) 为姊妹篇构造的无限有限呈现分次代数，正度理想 \(I\) 是矩阵幂零（matrix-nil）的：任意有限尺寸、系数取自 \(I\) 的矩阵皆幂零。取 Steinberg 群（Steinberg group）\(\Gamma=\mathop{\mathrm{St}}\nolimits_{12}(R)\)，则 \(\Gamma\) 无限、有限呈现、剩余有限；令 \(G=\ker(\Gamma\to\mathop{\mathrm{St}}\nolimits_{12}(\mathbb F_2))\)（由分次的零度投影诱导），则 \(G\) 是有限指标子群，无限、有限呈现（Reidemeister–Schreier 定理）、剩余有限，且每元为 \(2\) 幂阶——\(G\) 即主定理中的群。

## 证明思路

有限商来自度截断：\(R_{\ge d}=\bigoplus_{b\ge d}R_b\) 是理想，商环 \(R/R_{\ge d}\) 有限；\(\mathop{\mathrm{St}}\nolimits_{12}(R/R_{\ge d})\) 有限——其到矩阵群的核中心、中心有限指标，Schur 定理给出有限导群，而该群完美。截断立刻区分矩阵像不同的元素，真正的难点是区分 Steinberg 核 \(J(R)\)。

先在稳定群 \(\mathop{\mathrm{St}}\nolimits(R)\) 中工作。第一步用分次同态 \(\gamma:R\to R[t]\)，\(a_b\mapsto a_bt^b\)，把核元素 \(z\) 的代表词多项式化，再把 \(t\) 代入 \(L\times L\) 循环移位矩阵（cyclic shift）\(C_L\)，得 \(W_z(C_L)\in J(R)\)（思想源自 Weibel 的分次 \(K\)-理论转移）。本文的直接 Steinberg 计算表明：若 \(z\) 在 \(\mathbb F_2\) 上平凡，则对一切充分大的 \(L\) 有 \(W_z(C_L)=1\)；取 \(L\) 为 \(2\) 的幂便知这类 \(z\) 是 \(2\) 幂挠。

第二步是本文的新装置：相位（phase）。姊妹篇的规则层级给每个足够长的非零词 \(w\) 规定起始相位 \(\sigma(w)\in\mathbb Z/L\) 与终止相位 \(\tau(w)=\sigma(w)+|w|\)，\(L\) 可取任意大的奇数；相位只依赖词的基类，相位失配的乘积必为零。若 \(z\) 被所有截断漏掉，可先把它写成根之积、且每根系数都是长词（用备用坐标把长系数拆成换位子而长度不减）；再用秩一映射 \(\rho(w)=u_{\sigma(w)}v_{\tau(w)}w\) 把每根两端搬到以相位编号的新坐标（relocation 引理，误差收集进矩阵映射单射的条带子群）。此时 \(C_L\) 求值恰好分解为 \(L\) 个平移副本，中心性使每个副本都等于 \(z\)，故 \(W_z(C_L)=z^L\)。先选奇数 \(L\) 使第一步为零，再选足够长的代表使第二步成立：\(z^L=1\) 与 \(z^{2^a}=1\) 互素，故 \(z=1\)。于是度截断分离 \(\mathop{\mathrm{St}}\nolimits(R)\) 的全部元素；再经稳定性定理（\(\mathop{\mathrm{St}}\nolimits_{12}(R)\hookrightarrow\mathop{\mathrm{St}}\nolimits(R)\) 单射，文中用有序标架给出直接同调证明）回到秩 12。最后对 \(g\in G\)：其矩阵像为 \(\Id+A\)、\(A\in M_{12}(I)\) 幂零，特征 \(2\) 下 \((\Id+A)^{2^a}=\Id\)，故 \(g^{2^a}\) 落入核，再用相对挠命题与单射性把它杀死，得 \(g\) 为 \(2\) 幂阶。

## 可信度与备注

本文主结果暂无形式化证明（任务元数据 formalized=false），请以社区核验为准。本文与姊妹篇"An infinite finitely presented periodic group"紧密咬合：群、代数、有限呈现与词层级全部引自姊妹篇（其定理 3.7 与层级命题被显式引作输入），本文新增相位分析、检测定理与剩余有限性，两文合成对"有限呈现＋剩余有限周期群"问题的完整否定回答。按 OpenAI 官方声明，未经形式化的结果可能存在问题；最值得优先核验的是相位引理与 relocation 步骤的细节。

{% endraw %}
