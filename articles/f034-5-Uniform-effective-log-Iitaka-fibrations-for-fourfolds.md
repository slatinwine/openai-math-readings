---
layout: default
title: "Uniform effective log Iitaka fibrations for fourfolds"
family: "034"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Uniform effective log Iitaka fibrations for fourfolds

> 结果族 034：Log abundance for compact Kähler spaces under logarithmic Iitaka subadditivity　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

给全城四维的"带扣除项的形状"拍登记照：市政局想规定一个固定档位 `@@M@@m@@`，任何形状在那个档位拍出的照片都信息完整、足够办证（截面之比生成整个函数域）。论文证明这个档位在四维、系数来自固定有限集时真的存在；顺带还证明：四维"卡–丘"形状的固有曲率有统一周期上限——再诡异的形状，"归零频率"也逃不出同一只手掌。

**关键词卡片**

- 取整伴随系（rounded adjoint system）：把分数系数的除子 `@@M@@m(K_X+\Delta)@@` 向下取整后真正可用的截面集合
- 伪有效（pseudo-effective）：与移动曲线平均相交不负，"总量不为负"
- Iitaka 域（Iitaka field）：全部正次数截面之比生成的函数域，登记照上的完整信息
- 典范指数（canonical index）：让 `@@M@@K_X@@` 严格变成零所需的最小倍数
- klt（Kawamata log terminal）：奇点温和度的一个等级，比 log canonical 更严

**看个具体例子**

定理一的数字版：四维 klt 且 `@@M@@K_X\sim_{\mathbb Q}0@@`，则 `@@M@@N_4K_X\sim 0@@`（整数倍严格归零）。具体例子：五维射影空间里的六次超曲面

`@@M@@\{x_0^6+x_1^6+x_2^6+x_3^6+x_4^6+x_5^6=0\}\subset\mathbb P^5@@`

就是一个四维卡–丘形状：`@@M@@K_X=\mathcal O_X(6-6)=0@@`，指数为 1。定理断言任何同类形状的指数都整除某个公共的 `@@M@@N_4@@`，不管理论上能造出多"绕"的例子。定理二则给出统一档位 `@@M@@m(\Phi)@@`：在该档位所有取整伴随系非空，且截面比生成完整 Iitaka 域。

**为什么值得关心**

它同时拿下四维有效 log Iitaka 猜想（有限系数情形）与悬置的四维典范指数问题，是低维分类机器走向"可执行"的关键一步。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
证明了四维有效 log Iitaka 猜想的有限有理系数情形：对系数取自固定有限集 `@@M@@\Phi@@` 的射影 log canonical 四维组 `@@M@@(X,\Delta)@@`，存在仅依赖 `@@M@@\Phi@@` 的统一次数 `@@M@@m@@`，使完备取整线性系 `@@M@@|\lfloor m(K_X+\Delta)\rfloor|@@` 非空且其截面比生成整个 Iitaka 域；并顺带得到 klt Calabi–Yau 四维组的统一典范指数界 `@@M@@N_4@@`。

## 问题背景
Iitaka 纤维化把一个除子的正截面按次数组织成有理映射，而"有效"版本追问：能否用一个只依赖维数与系数集的统一次数实现它？Chen–Han–Liu 对系数满足 DCC 的 lc 组（log canonical pair）形式化了这一猜想，并证明到三维为止；此前的有效结果（Hacon–McKernan–Xu 的大情形、Viehweg–Zhang、Todorov–Xu、Birkar–Zhang）都只覆盖特殊 Kodaira 维数或特殊奇性。与之纠缠的是典范指数问题（canonical index problem）：`@@M@@K_X\sim_\Q 0@@` 的 klt Calabi–Yau 组的典范指数可有只依赖维数的上界？三维已由 Jiang、Xu、Jiang–Liu 等解决，Birkar 处理了有理连通情形，但四维、零边界的情形一直悬而未决。本文同时拿下这两件事的四维版本。

## 主要结果
**定理一（统一典范指数）**：存在正整数 `@@M@@N_4@@`，使得对每个满足 `@@M@@K_X\sim_\Q 0@@` 的正规射影 klt 复四维组 `@@M@@X@@`，都有 `@@M@@N_4K_X\sim 0@@`。这是整 Weil 除子的主除子平凡化，而非仅数值平凡。

**定理二（统一有效 log Iitaka 纤维化）**：设 `@@M@@\Phi\subset[0,1]\cap\Q@@` 有限，则存在 `@@M@@m=m(\Phi)@@`：只要 `@@M@@X@@` 是正规整射影复四维组，`@@M@@\Delta\geq 0@@` 是系数落在 `@@M@@\Phi@@` 中的有理 Weil 除子，`@@M@@(X,\Delta)@@` 为 lc，且 `@@M@@D=K_X+\Delta@@` 为有理 Cartier 除子并伪有效（pseudo-effective），那么 `@@M@@|\lfloor mD\rfloor|@@` 非空，且同一次数 `@@M@@m@@` 下截面之比在 `@@M@@\C(X)@@` 中生成完整 Iitaka 域 `@@M@@K(D)@@`。注意这里的线性系用秩一自反层定义，不要求 `@@M@@mD@@` Cartier；`@@M@@\kappa=4@@` 时系统是双有理的，`@@M@@\kappa=0@@` 时像为一个点。该 `@@M@@m@@` 对典范除子代表的选取也一致有效。

## 证明思路
证明分四大步。先由伪有效性导出非消失：借助姊妹篇《Log abundance in characteristic zero》的好模型定理与有效例外比较引理，在某个（未必一致的）正次数里找到一个截面，从而 `@@M@@\kappa\geq 0@@`。再作模型比较：取 crepant dlt 修正并跑伴随除子负的 MMP（flip 终止性用 Chen–Tsakanikas），通过"极点检验"`@@M@@v\in H^0(\OO(\lfloor mL\rfloor))\Leftrightarrow\Div(v)+mL\geq0@@` 证明每一步都保持所有整数次数的取整截面空间相等；再引用配套伴献《Lifting sections from the reduced support of an adjoint》中射影版的非消失后丰度定理把伴随除子变为半丰富（semiample），并识别 Iitaka 域为收缩基的函数域 `@@M@@\C(Z)@@`。第三步证指数定理：用奇异 Beauville–Bogomolov 分解把乘积与阿贝尔情形、有理连通商情形逐一排除，只剩单个 terminal 因子 `@@M@@V@@`；"移动除子"引理说明若存在正 Iitaka 维数的非大有效除子，其阶除尽一个固定整数，于是在指数无界情形下每个正 Iitaka 维数的有效除子都是大的——这给出标量估计所需的纤维化条件。对次数为 `@@M@@r@@` 的循环指数覆盖 `@@M@@\pi:Y\to V@@`，由 `@@M@@(\pi^*L)^4=rL^4@@` 得 Seshadri 常数下界 `@@M@@\varepsilon(\pi^*L)\ge c\,r^{1/4}@@`，楼上的曲线度/重数比随 `@@M@@r@@` 增长；而在对角商 `@@M@@Z_t=Y^t/\mu_{r,\mathrm{diag}}@@` 上，通过约化到正特征并比较普通 jet 与 Frobenius jet（Mustaţă–Schwede 局部比较、Sun 典范滤过），得到只以 `@@M@@t^2@@` 增长、与 `@@M@@r@@` 无关的曲线。用 Campana 链式策略与 Ein–Küchle–Lazarsfeld 参数微分把曲线串成"链叶"，其度数有界；若某叶在坐标方向有正维纤维便会落入 `@@M@@Y^{t-1}@@`，与增长的标量下界矛盾，故大 `@@M@@r@@` 时各坐标映射为一般有限，且某遗忘映射度为 1。度 1 的遗忘映射诱导只依赖端点的线性搬运，从而得到有理向量场及其双有理流，产生不可数多个双有理自映射，与 `@@M@@\Bir(V)@@` 可数矛盾。最后组装有效定理：正维基用姊妹篇的大基有效双有理性命题统一生成 `@@M@@\C(Z)@@`；零维基分非 klt（Jiang–Liu）、klt 非零边界（Xu）、klt 零边界（定理一）三种指数情形，取公倍数后经全次数截面比较传回原组。值得注意：指数定理本身不依赖 log Iitaka 可加性，只有定理二的伪有效起点继承了该输入。

## 可信度与备注
本文主结果暂无 Lean 形式化证明。它是结果族 034 的成员：半丰富模型比较所用的"非消失后丰度"输入是射影伴献中的定理 1.2，与本批姊妹篇《Abundance after nonvanishing for compact Kähler fourfolds》（紧 Kähler 版本）互为呼应；相对分母与有效线性系输入来自配套的相对伴随论文，构成环环相扣的证明网络。作者也明确区分了依赖与不依赖 log Iitaka 可加性的部分。按 OpenAI 官方声明，未经形式化的结果可能存在问题，读者应以社区核验为准。

{% endraw %}
