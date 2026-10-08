---
layout: default
title: "Strong diffeomorphic approximation in three dimensions for 1≤p≤2"
family: "368"
discipline: "Partial differential equations"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Strong diffeomorphic approximation in three dimensions for 1≤p≤2

> 结果族 368：The three-dimensional Ball–Evans approximation problem　·　学科：Partial differential equations　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

揉一块不许自相穿透的橡皮泥：形变可以很粗糙——每一点的"拉伸程度"只在平均意义下可谈。问：能否用一系列同样不自穿、却光滑无比的形变去逼近它，并且连拉伸程度也一起逼近？这篇论文在三维、指数 `@@M@@1\le p\le2@@` 时给出肯定回答；与处理 `@@M@@p>2@@` 的姊妹篇合起来，三维 Ball–Evans 逼近问题宣告彻底解决。

**关键词卡片**

- Sobolev 同胚（Sobolev homeomorphism）：连续双射、导数按 `@@M@@L^p@@` 平均可控的形变。
- 微分同胚（diffeomorphism）：光滑且逆也光滑的"无粘连"形变。
- 强逼近（strong approximation）：位置与导数同时逼近，`@@M@@\int|Df_j-Df|^p\to0@@`。
- Ball–Evans 问题（Ball–Evans approximation problem）：粗糙同胚能否被映满同一目标的光滑微分同胚强逼近。
- 指数 `@@M@@p@@`（integrability exponent）：导数按几次幂平均，`@@M@@p=1@@` 最宽松。

**看个具体例子**

定理的数值版：取最宽松的 `@@M@@p=1@@`，对任意两个有界区域之间的三维 Sobolev 同胚 `@@M@@f@@`，都存在映满同一目标的光滑微分同胚 `@@M@@f_j@@`，使 `@@M@@\int_\Omega(|f_j-f|+|Df_j-Df|)\,dx\to0@@`。歪扭的粗糙网格，可以被光滑且仍不重叠的网格连"拉伸程度"一起逼近。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="30" text-anchor="middle" font-size="15" fill="#333">粗糙同胚 f 与光滑逼近 f_j：都不自穿、都映满目标</text>
  <rect x="45" y="70" width="170" height="150" fill="none" stroke="#333" stroke-width="2"/>
  <path d="M85 70 Q90 140 82 220" fill="none" stroke="#2471a3" stroke-width="1.5"/>
  <path d="M130 70 Q118 145 133 220" fill="none" stroke="#2471a3" stroke-width="1.5"/>
  <path d="M175 70 Q185 138 172 220" fill="none" stroke="#2471a3" stroke-width="1.5"/>
  <path d="M45 110 Q128 100 215 112" fill="none" stroke="#2471a3" stroke-width="1.5"/>
  <path d="M45 150 Q130 162 215 148" fill="none" stroke="#2471a3" stroke-width="1.5"/>
  <path d="M45 190 Q126 180 215 192" fill="none" stroke="#2471a3" stroke-width="1.5"/>
  <text x="130" y="245" text-anchor="middle" font-size="13" fill="#333">f：网格歪扭（导数只是 L^p）</text>
  <path d="M255 145 L305 145" fill="none" stroke="#666" stroke-width="2"/>
  <path d="M297 139 L307 145 L297 151" fill="none" stroke="#666" stroke-width="2"/>
  <text x="280" y="128" text-anchor="middle" font-size="12" fill="#666">强逼近</text>
  <rect x="340" y="70" width="170" height="150" fill="none" stroke="#333" stroke-width="2"/>
  <path d="M380 70 Q372 145 384 220" fill="none" stroke="#2e7d32" stroke-width="1.5"/>
  <path d="M425 70 Q433 145 421 220" fill="none" stroke="#2e7d32" stroke-width="1.5"/>
  <path d="M470 70 Q462 145 474 220" fill="none" stroke="#2e7d32" stroke-width="1.5"/>
  <path d="M340 110 Q425 103 510 110" fill="none" stroke="#2e7d32" stroke-width="1.5"/>
  <path d="M340 150 Q425 157 510 150" fill="none" stroke="#2e7d32" stroke-width="1.5"/>
  <path d="M340 190 Q425 183 510 190" fill="none" stroke="#2e7d32" stroke-width="1.5"/>
  <text x="425" y="245" text-anchor="middle" font-size="13" fill="#333">f_j：光滑微分同胚（导数也逼近）</text>
  <text x="280" y="268" text-anchor="middle" font-size="13" fill="#666">网格线互不相交 = 保持单射；网格走向逐格贴近 = 导数按 L^p 收敛</text>
</svg>

</div>

**为什么值得关心**

弹性力学要求形变保持单射（物质不穿透），本结果让"保持单射"与"导数逼近"在三维首次兼容——四维以上存在行列式变号反例，三维是最后的空档。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文解决了三维 Ball–Evans 逼近问题在 `@@M@@1\le p\le2@@` 的情形：任意有界区域之间的 `@@M@@W^{1,p}@@` 同胚都是映满同一目标域的 `@@M@@C^\infty@@` 微分同胚在 `@@M@@W^{1,p}@@` 中的强极限，让"保持单射"与"导数逼近"这两个在三维长期无法兼得的要求首次同时成立。

## 问题背景

非线性弹性中，材料的变形必须单射（物质互不穿透），局部形变由弱导数刻画，于是自然的映射类是 Sobolev 同胚 (Sobolev homeomorphism)。卷积磨光随手可得，却会破坏单射；Ball 在 2001 年的论述中把"能否两者兼得"归于 Evans，即固定目标的 Ball–Evans 逼近问题。二维已完整解决：Iwaniec–Kovalev–Onninen (2011) 覆盖 `@@M@@1<p<\infty@@`，Hencl–Pratelli (2018) 攻下端点 `@@M@@p=1@@`。高维存在实质障碍：Campbell–Hencl–Tengvall (2018) 在 `@@M@@n\ge4@@`、`@@M@@1\le p<\lfloor n/2\rfloor@@` 造出 Jacobi 行列式在正测度集上变号的同胚，导数的强收敛无法重现这种符号模式。三维恰是空档：Hencl–Malý (2010) 的定向定理保证保向同胚 `@@M@@\det Df\ge0@@` 几乎处处成立，挡住了上述反例，但它不提供逼近，秩亏 (rank-deficient) 导数仍须专门构造——这正是本文要跨过的鸿沟。

## 主要结果

主定理：设 `@@M@@\Omega,\Lambda\subset\R^3@@` 为有界连通开集，`@@M@@1\le p\le2@@`，`@@M@@f:\Omega\to\Lambda@@` 为 `@@M@@W^{1,p}@@` 同胚，则存在 `@@M@@C^\infty@@` 微分同胚 (diffeomorphism) `@@M@@f_j:\Omega\to\Lambda@@`，每个都属于 `@@M@@W^{1,p}@@`，使

`@@M@@D\int_\Omega\bigl(|f_j-f|^p+|Df_j-Df|^p\bigr)\,dx\longrightarrow0 .@@`

不要求任何边界正则性、`@@M@@f@@` 的边界延拓、逆映射的 Sobolev 正则性或 Jacobi 非零；每个逼近映射的像恰为原目标 `@@M@@\Lambda@@`。

## 证明思路

证明分两大步：先构造局部双 Lipschitz (locally bi-Lipschitz) 同胚 `@@M@@H:\Omega\to\Lambda@@` 以任意小误差强逼近 `@@M@@f@@`，再用一个对所有有限 `@@M@@p@@` 都成立的光滑化定理把 `@@M@@H@@` 换成光滑微分同胚。核心障碍在于：三维 PL 拓扑（Moise–Bing 三角剖分理论、Hamilton 的相对逼近、Edwards–Kirby 形变定理）只提供定性替换，不给任何导数估计；若先缩小例外集再选替换，替换的 Lipschitz 常数可以任意大，能量估计便成循环论证。论文的对策是贯穿全文的次序原则——先把一切有限常数（紧射流 (jet) 界、模型库导数上界）固定，再让各误差在它们面前变小。

光滑化一步又分两层。先用"有限 PL 模型库 + 适应性二进网格"把 `@@M@@H@@` 强逼近为分片仿射 (piecewise affine) 同胚：各粗邻域的替换模型及其导数上界在网格加密之前选定，坏方体的体积之后才缩小，循环性由此破解。再对 PL 同胚分级磨光：棱上在管状邻域内做显式角度修正保持行列式为正；面上用变半径卷积，正性由"附近梯度凸包落在 `@@M@@\mathrm{GL}^+(3)@@` 内"保证；顶点处借 Smale 的球面同痕定理把齐次芽顺滑为旋转。最后以真同伦 (proper homotopy) 加拓扑度论证：只要光滑逼近逐点足够贴近原同胚，它就自动双射映满原目标。

低指数逼近是主战场。先选出有限个紧集，其上 `@@M@@f@@` 的值与一阶导数受控、导数秩固定（经 Whitney 延拓得到相容射流），丢弃部分的 `@@M@@\int|Df|^p@@` 任意小。满秩紧集用"径向块"恢复精确射流：先在中心植入与 `@@M@@f@@` 局部重合的 `@@M@@C^1@@` 微分同胚芽，再以源径向压缩、目标径向扩张把这个芽放大到块的大部分。秩一、秩二时压缩核方向，把体积估计化为线段或平面截面上的长度、面积问题：`@@M@@p=1@@` 用初等的平方长度亏损估计加 Hölder 不等式（绕开 `@@M@@L^1@@` 无严格凸性）；秩二、`@@M@@p=2@@` 用"边界参数化圆盘估计"，经 Ahlfors–Bers 等温坐标共形换参，把面积转化为接近极小的 Dirichlet 能量。能量来源是一套"迹预算 (trace budget)"机制：对目标三角剖分中由重心坐标并列最大者定义的对偶分层，数曲线、曲面的穿越次数，每次穿越记下对应目标棱长或面面积；平移平均与 coarea 公式把期望预算控制在原迹积分内；再用 softmax 型"单纯形挤压"目标自同胚把像长、像面集中到穿越点旁，把计数变成真实测量。`@@M@@p=2@@` 时还调用 Csörnyei–Hencl–Malý 的逆 `@@M@@BV@@` 定理与二维 Lusin 性质来选取反向射线、测量一般像曲面。其余不受控胞腔由次临界径向塌缩用边界能量控制，误差全部可和，最终拼出整体 `@@M@@W^{1,p}@@` 强逼近。

## 可信度与备注

主结果暂无 Lean 形式化证明。本族两篇互为姊妹：本文覆盖 `@@M@@1\le p\le2@@`，另一篇覆盖 `@@M@@p>2@@`，合并即完整解决三维 Ball–Evans 问题；两文共享同一光滑化定理（本文第 2 节，姊妹篇在附录 A 完整重证），但互不引用对方区间的定理。按 OpenAI 官方声明，未经形式化的结果可能存在问题，结论请以社区核验为准。

{% endraw %}
