---
layout: default
title: "Integrable metrics and effectivity with controlled boundary"
family: "068"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Integrable metrics and effectivity with controlled boundary

> 结果族 068：Anticanonical nonvanishing in every dimension　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明受控边界有效性定理：若 \(-K_Y+C\) 的度量有整体严格曲率下界且 \(C\) 的典范截断局部平方可积，则任何伪有效有理除子经支集含于 \(C\) 的有效修正后即有理有效；据此建立固定误差转化定理，把反典型非消没推进到任意维数。

## 问题背景

伪有效（pseudoeffective）除子未必有任何正倍的有效代表。本文研究一个使其变为有效（至相差有理线性等价）的分析条件：反典型度量的正曲率，加上边界除子典范截断的可积性。其价值在双有理几何：纤维化基上作出的修正，经拉回与推向后可以在原簇上消失，从而"借基还簇"。用乘子理想（multiplier ideal）语言，条件 \(\mathcal J(h)\supset\mathcal O_Y(-C)\) 恰好等价于 \(s_C\) 的范数平方局部可积。与 LMPTX、Müller 的 nef 框架相比，光滑半正度量给出更强的分析输入，使结论能对一切维数成立。

## 主要结果

定理一（受控边界有效性，Effectivity modulo a controlled boundary）：设 \(Y\) 光滑射影、\(C\ge0\) 为整除子，\(-K_Y+C\) 有曲率支配某 Kähler 形式的奇性 Hermitian 度量 \(h\)，且 \(\mathcal J(h)\supset\mathcal O_Y(-C)\)。则对每个伪有效有理除子 \(M\)，存在支集含于 \(C\) 的有效有理除子 \(C_0\)，使 \(M+C_0\) 有理有效（rationally effective，即有理线性等价于有效有理除子）。定理二（固定误差转化）：设 \(X\) 光滑连通射影、\(L=-K_X\) 光滑半正、\(P\) 为任意伪有效 Cartier 除子；若存在无界正整数 \(m_j\) 及有效整除子 \(N_j\sim m_jL-P\)，则 \(H^0(X,mL)\ne0\)。推论：固定 \(p\ge0\)，若 \(H^0(X,(\Omega_X^1)^{\otimes p}\otimes mL)\) 沿无界 \(m\) 非零，则 \(L\) 的某正倍有截断。文中还给出修正环的多分次有限生成、辅助基的 Fano 型（Fano type）模型，以及 \(\chi(X,\mathcal O_X)\ne0\) 时的不变截断版本。

## 证明思路

定理一走"BCHM 大边界非消没"路线。先用 Demailly 加权 Bergman 逼近（Ohsawa–Takegoshi 点延拓，配合 Nadel 消没给出的整体生成性）在消解 \(\sigma:Y'\to Y\) 上造出符号除子 \(\Psi=\Psi^+-\Psi^-\)：其系数严格小于一，负部只落在 \(C\) 与例外轨迹之上。留一个小丰富（ample）除子 \(A\) 作缓冲；对给定 \(M\) 取小 \(t>0\) 使 \(A+tM\) 丰富，用一般自由与丰富代表把正部充实成有效、大且 klt（Kawamata log terminal）的边界 \(\Delta_t\)，满足 \(K_{Y'}+\Delta_t\sim_{\mathbb Q}\Psi^-+t\sigma^*M\)，右端伪有效。BCHM 定理 D 给出实线性等价的有效代表；"有理恢复"引理（系数非负性是有限组有理线性不等式，非空有理多面体必有有理点）把结论升级为有理等价；推前后除以 \(t\)，修正 \(\sigma_*\Psi^-/t\) 的支集恰落在 \(C\) 上。另有度量层面的扰动路线：Guan–Zhou 强开性加 Skoda 小指数可积性加 Hölder 不等式，允许对度量作小伪有效扰动而保持 \(s_C\) 可积与严格下界。

定理二只用单个 Iitaka 纤维化（Iitaka fibration）。取 \(N_1\) 的截断比值域，一切 \(N_j\) 的除子沿一般纤维仿射变化（精确恒等式 \(\pi^*N_j=\pi^*N_0+(m_j-m_0)(\pi^*R+f^*Q_j)\)），垂直最小值定义出基上除子 \(M\)，由有效性取极限知其伪有效。反证法证伴随直像秩一：若秩更大，两个一般纤维无关的截断经扭曲后的比值既是基函数又不是，矛盾。极化等式给出 \(\pi^*L\) 上支配 \(f^*\omega_Y\) 的正电流度量，与光滑拉回度量小比例混合后，Skoda 定理保证全空间乘子理想平凡；Păun–Takayama 奇性直像正性在秩一壳 \(\mathcal O_Y(-K_Y+C)\) 上给出整体严格曲率度量，且 \(\mathcal J\supset\mathcal O_Y(-C)\)、\(f^*C\) 例外。套定理一得 \(M+C_0\sim_{\mathbb Q}G\ge0\)，返回引理把截断送回 \(X\) 而不引入极点。张量版由行列式法与余切子丛伪有效性衔接。另一路线调用姊妹篇《Metric descent》的环面体积度量（文中引作 CompanionG）得到无权可积版本；光滑 coarea 路线则给出整除子修正与 \(L^{1+\eta}\) 增强可积性。

## 可信度与备注

本文处于本族的分析—代数枢纽：它消费《Metric descent and rank-preserving contractions》的环面体积度量构造，其固定误差转化机制与《Cohomological transfer》的转移定理互为呼应；不变版本则依赖族内姊妹篇的不变指标定理与有限覆盖结构。全部结果暂无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能存在问题，结论请以社区核验为准。

{% endraw %}
