KaTeX 是一个快速，易于使用的JavaScript库，用于在Web上进行TeX数学渲染。
KaTeX兼容所有主流浏览器，包括Chrome，Safari，Firefox，Opera，Edge和IE 9-11。
KaTeX支持很多（但不是全部）LaTeX语法和许多LaTeX软件包。

[katex官方文档](https://katex.org/docs/supported.html)


# 字母符号

Inline math: $$\displaystyle\int_{-\infty}^\infty g(x) dx$$

Block math:

$$
\int_{-\infty}^\infty g(x) dx
$$

$\Alpha$ \Alpha|$\alpha$ \alpha|$\Tau$ \Tau|$\tau$ \tau
---|---|---|---
$\Beta$ \Beta|$\beta$ \beta|$\Upsilon$ \Upsilon|$\upsilon$ \upsilon
$\Gamma$ \Gamma|$\gamma$ \gamma|$\Phi$ \Phi|$\phi$ \phi
$\Delta$ \Delta|$\delta$ \delta|$\Chi$ \Chi|$\chi$ \chi
$\Epsilon$ \Epsilon|$\epsilon$ \epsilon|$\Psi$ \Psi|$\psi$ \psi
$\Zeta$ \Zeta|$\zeta$ \zeta|$\Omega$ \Omega|$\omega$ \omega
$\Eta$ \Eta|$\eta$ \eta|$\varPi$ \varPi|$\varpi$ \varpi
$\Theta$ \Theta|$\theta$ \theta|$\varSigma$ \varSigma|$\varsigma$ \varsigma
$\Iota$ \Iota|$\iota$ \iota|$\varTheta$ \varTheta|$\vartheta$ \vartheta
$\Kappa$ \Kappa|$\kappa$ \kappa|$\varPhi$ \varPhi|$\varphi$ \varphi
$\Lambda$ \Lambda|$\lambda$ \lambda|$\varGamma$ \varGamma|$\varepsilon$ \varepsilon
$\Mu$ \Mu|$\mu$ \mu|$\varDelta$ \varDelta|$\varkappa$ \varkappa
$\Nu$ \Nu|$\nu$ \nu|$\varLambda$ \varLambda|$\thetasym$ \thetasym
$\Xi$ \Xi|$\xi$ \xi|$\varXi$ \varXi|$\varrho$ \varrho
$\Omicron$ \Omicron|$\omicron$ \omicron|$\varUpsilon$ \varUpsilon|$\digamma$ \digamma
$\Pi$ \Pi|$\pi$ \pi|$\varPsi$ \varPsi|
$\Rho$ \Rho|$\rho$ \rho|$\varOmega$ \varOmega|
$\Sigma$ \Sigma|$\sigma$ \sigma|$\mho$ \mho|
$\imath$ \imath|$\nabla$ \nabla|$\Im$ \Im|$\Reals$ \Reals|$\text{\OE}$ \text{\OE}
$\jmath$ \jmath|$\partial$ \partial|$\image$ \image|$\wp$ \wp|$\text{\o}$ \text{\o}
$\aleph$ \aleph|$\Game$ \Game|$\Bbbk$ \Bbbk|$\weierp$ \weierp|$\text{\O}$ \text{\O}
$\alef$ \alef|$\Finv$ \Finv|$\N$ \N|$\Z$ \Z|$\text{\ss}$ \text{\ss}
$\alefsym$ \alefsym|$\cnums$ \cnums|$\natnums$ \natnums|$\text{\aa}$ \text{\aa}|$\text{\i}$ \text{\i}
$\beth$ \beth|$\Complex$ \Complex|$\R$ \R|$\text{\AA}$ \text{\AA}|$\text{\j}$ \text{\j}
$\gimel$ \gimel|$\ell$ \ell|$\Re$ \Re|$\text{\ae}$ \text{\ae}|
$\daleth$ \daleth|$\hbar$ \hbar|$\real$ \real|$\text{\AE}$ \text{\AE}|
$\eth$ \eth|$\hslash$ \hslash|$\reals$ \reals|$\text{\oe}$ \text{\oe}|

符号|定义|Latex
:---|:---|:---
$\bar{a};\overline{a+bi}$|共轭|\bar{a}; \overline{a+bi}
$\underline{AB}$||\underline{AB}
$\vec{a},\overrightarrow{AB};\overrightharpoon{ac}$|向量|\vec{a},\overrightarrow{AB};\overrightharpoon{ac}
$\underrightarrow{AB}$||\underrightarrow{AB}
$\overleftarrow{AB};\overleftharpoon{ac};\underleftarrow{AB}$||\overleftarrow{AB};;\overleftharpoon{ac};\underleftarrow{AB}
$\overleftrightarrow{T}$|张量|\overleftrightarrow{T}
$\overset{\rightrightarrows}{T}$|张量并矢|\overset{\rightrightarrows}{T}
$\underleftrightarrow{AB}$||\underleftrightarrow{AB}
$\Overrightarrow{AB}$||\Overrightarrow{AB}
$\hat{\theta}$|坐标基|\hat{\theta};\^{\theta}
$\widehat{ac}$|夹角|\widehat{ac}
$\breve{a}$||\breve{a}
$\check{a};\widecheck{ac}$||\check{a};\widecheck{ac}
$\tilde{a};\widetilde{ac};\utilde{AB}$|波浪|\tilde{a};\widetilde{ac};\utilde{AB}
$\acute{a}$||\acute{a}
$\grave{a}$||\grave{a}
$\overgroup{AB};\undergroup{AB}$||\overgroup{AB};\undergroup{AB}

# 运算符

二元运算|定义|Latex
:---|:---|:---
$=$|is equal to|=
$\approx$|is approximately equal to|\approx
$+$|plus|+
$-$|minus|-
$\pm; \mp$|plus-minus; minus-plus|\pm; \mp
$\times$|multiplied by;cross product|\times
$\cdot$|dot product|\cdot; \centerdot
$*$||*;\ast
$\div; /$|divided by|\div; /
$<$|is less than|<;\lt
$>$|is greater than|>;\gt
$\ll;\lll$|远小于|\ll\lll
$\gg;\ggg$|远大于|\gg;\ggg
$\geqslant;\ge$|大于等于|\geqslant\ge
$\leqslant;\le$|小于等于|\leqslant;\le
$\propto$|正比于|\propto
$\triangleq$|定义|\triangleq
$\stackrel{!}{=}$|堆叠|\stackrel{!}{=}
$\overset{!}{=}$|上方|\overset{!}{=}
$\underset{!}{=}$|下方|\underset{!}{=}
$a \atop b$||a \atop b
$a\raisebox{0.25em}{b}c$||a\raisebox{0.25em}{b}c
$\not=;\not\in$|前方加\not否定|\not=;\not\in

运算|定义|Latex
:---|:---|:---
$\dfrac{b}{a}$|分数|\frac{b}{a}; \dfrac{b}{a}
$\cfrac{a}{1 + \cfrac{1}{b}}$|复合分式|\cfrac{a}{1 + \cfrac{1}{b}}
$\sqrt{x}; \sqrt[n]{x}$|开方|\sqrt{x}; \sqrt[n]{x}
$a^n$|指数|a^n
$a_n$|下标|a_n
$f \circ g$|复合函数|f \circ g
$\displaystyle\sum_{k=0}^n \complement^k_n u^{n-k} v^k$|求和|`\displaystyle\sum_{k=0}^n \complement^k_n u^{n-k} v^k`
$\prod$|求积|\prod
$\amalg$|合并|\amalg

# 分隔符

符号|定义|Latex|示例
:---|:---|:---|:---
$\mid a \mid$|绝对值|\vert; \mid; `|`;\vert; \rvert
$\|a\|$|范数，模|\Vert; `\|`; \lVert\ ;rVert|
$\lceil a\rceil$|ceiling|\lceil a\rceil|
$\lfloor a\rfloor$|floor|\lfloor a\rfloor|⌊2.1⌋ = 2
$\lfloor a\rceil$|最接近的整数|\lfloor a\rceil|⌊2.6⌉ = 3
$\lmoustache\rmoustache$|胡须|\lmoustache\rmoustache|
$\ulcorner\urcorner$||\ulcorner\urcorner|
$\llcorner\lrcorner$||\llcorner\lrcorner|
$\uparrow;\downarrow;\updownarrow$||\uparrow;\downarrow;\updownarrow|
$\Uparrow;\Downarrow;\Updownarrow$||\uparrow;\downarrow;\updownarrow|

**分隔符尺寸**

$\left(\LARGE{AB}\right)$ `\left(\LARGE{AB}\right)`
$( \big( \Big( \bigg( \Bigg($ `( \big( \Big( \bigg( \Bigg(`

# 注释

符号|定义|Latex
:---|:---|:---
$\text{\sect}$|分节|\text{\sect}
$\star$|星号|\star
$\cancel{5}$|划线|\cancel{5}
$\bcancel{5}$|划线|\bcancel{5}
$\xcancel{abc}$|划线|\xcancel{5}
$\sout{5}$|划线|sout{5}
$\boxed{\pi=\frac c d}$|方框|\boxed{\pi=\frac c d}
$\overbrace{a+b+c}^{\text{note}}$|上备注|\overbrace{a+b+c}^{\text{note}}
$\underbrace{a+b+c}_{\text{note}}$|下备注|\underbrace{a+b+c}_{\text{note}}



# 函数

$\arcsin$  `\arcsin`|$\cotg$  `\cotg`|$\ln$  `\ln`|$\det$  `\det`
:---|:---|:---|:---
$\arccos$  `\arccos`|$\coth$  `\coth`|$\log$  `\log`|$\gcd$  `\gcd`
$\arctan$  `\arctan`|$\csc$  `\csc`|$\sec$  `\sec`|$\inf$  `\inf`
$\arctg$  `\arctg`|$\ctg$  `\ctg`|$\sin$  `\sin`|$\lim$  `\lim`
$\arcctg$  `\arcctg`|$\cth$  `\cth`|$\sinh$  `\sinh`|$\liminf$  `\liminf`
$\arg$  `\arg`|$\deg$  `\deg`|$\sh$  `\sh`|$\limsup$  `\limsup`
$\ch$  `\ch`|$\dim$  `\dim`|$\tan$  `\tan`|$\max$  `\max`
$\cos$  `\cos`|$\exp$  `\exp`|$\tanh$  `\tanh`|$\min$  `\min`
$\cosec$  `\cosec`|$\hom$  `\hom`|$\tg$  `\tg`|$\Pr$  `\Pr`
$\cosh$  `\cosh`|$\ker$  `\ker`|$\th$  `\th`|$\sup$  `\sup`
$\cot$  `\cot`|$\lg$  `\lg`|$\operatorname{f}$  `\operatorname{f}`|$\arg\max$  `\arg\max`
$\arg\min$  `\arg\min`|||

# 逻辑理论

符号|定义|Latex|示例
:---|:---|:---|:---
$\because$|因为|\because|
$\therefore$|所以|\therefore|
$\lnot; \sim$|逻辑非(negation)|\neg; \lnot; \sim|$\lnot(\lnot A)\iff A$
$\land$|逻辑与|\land|n < 4 ∧ n > 2 ⇔ n = 3 when n is a natural number.
$\lor$|逻辑或|\lor|n ≥ 4 ∨ n ≤ 2 ⇔ n ≠ 3 when n is a natural number.
$\oplus; \veebar$|异或|\oplus; \veebar|$a\oplus b=(\lnot a\land b)\lor(a\land \lnot b)$
$\iff; \leftrightarrow$|双条件，等价关系，当且仅当(if and only if)|\iff; \leftrightarrow|
$\Rarr; \rarr$|条件运算,if ... then|\Rarr; \rarr ;\to|$x=6\Rightarrow x^2=36$
$\Larr; \larr$|左箭头|\Larr; \larr; \gets|
$:=; :\Leftrightarrow$|定义|:=|
$\implies; \impliedby$||\implies; \impliedby|
$\forall$|任意|\forall|∀ n ∈ ℕ, n2 ≥ n
$\exists$|存在|\exists|∃ n ∈ ℕ: n is even
$\exists!$|唯一存在|\exists!|∃! n ∈ ℕ: n + 5 = 2n.
$\vDash$|满足符|\vDash|$A\vDash B$
$\vdash$|推断出|\vdash|A → B ⊢ ¬B → ¬A
$\square$|拟态词必然|\square|
$\Diamond$|拟态词可能|\Diamond|
$R \circ S$|复合关系|R \circ S|

# 集合和概率

符号|定义|Latex
:---|:---|:---
$\{x\vert P(x)\}$|集合|\{x\mid P(x)\}
$\mathring{U}$|邻域|\mathring{U}
$\uplus$|多重集|\uplus
$\subset$|真子集|\subset
$\subseteq$|子集|\subseteq
$\supset$|真父集|\supset
$\supseteq$|父集|\supseteq
$\in$||\in
$\ni$||\ni 
$\cap$|交集|\cap
$\cup$|并集|\cup
$\setminus$|差集|\setminus
$\mathrm{card}(A)$|元素个数|\mathrm{card}(A)
$\emptyset; \varnothing$|空集|\emptyset; \varnothing
$\N$|自然数|\N
$\Z$|整数|\Z
$\R$|实数|\R;\Reals
$\Im$|虚数|\Im; \Image
$\Complex$|复数|\Complex
$n!$|阶乘|n!
$\binom{n}{k}$, ${n\brack k}$|二项式系数|\binom{n}{k}; \dbinom{n}{k}; <br>{n \choose k}; n\brack k
$A^n_m$|排列(Arrangement)|A^n_m
$\complement^n_m$|组合|\complement^n_m
$X\sim N(\mu,\sigma^2)$|服从分布|\sim
⟨φ\|ψ⟩|左矢量,右矢量|\langle\rangle
${n\brace k}$||{n\brace k}
${n\brack k}$||{n\brack k}

# 几何

符号|定义|Latex
:---|:---|:---
$\backsim$|相似三角形|\backsim
$\backsimeq$||\backsimeq
$\overset{\backsim}{=}$|全等三角形|\overset{\backsim}{=}
$\parallel$|平行|\parallel
$\nparallel$|不平行|\nparallel
$\bot$|垂直|\bot
$\overline{AB}$|直线|\overline{AB}
$\overlinesegment{AB}$|线段|\\overlinesegment{AB}
$\underlinesegment{AB}$||\underlinesegment{AB}
$\overset{\frown}{AB}$|弧|\overset{\frown}{AB}
$\odot$|圆|\odot
$\bigcirc$||\bigcirc
$\boxdot$||\boxdot
$\square$|矩形|\square
$\mathrm{Rt}\triangle$|直角三角形|\mathrm{Rt}\triangle
$\Diamond$|菱形|\Diamond
$\angle$|角|\angle
$\measuredangle$||\measuredangle
$90\degree$|角度|90\degree

# 微积分

符号|定义|Latex|示例
:---|:---|:---|:---
$\gets$||\gets|
$\to$|趋向于|\to|$f:X\to Y$
$\infty$|无穷大|\infty|
$\lim$|极限|\lim\limits_{x\to \infty} f(x)=1|$\lim\limits_{x\to \infty} f(x)=1$
$\dot{x}$|导数|\dot{x}|
$\ddot{x}$|二阶导|\ddot{x}|
$x'$|导数|x'; x^\prime|
$x''$|二阶导|x''|
$x^{(n)}$|n阶导|x^{(n)}|
$\partial$|偏导数|\partial|
$\mathrm{d}x$|微分|\mathrm{d}x|
$\int$|积分|\int|$\int x^2\mathrm{d}x =\dfrac{x^3}{3}+C \\ \int_a^b x^2\mathrm{d}x =\dfrac{b^3-a^3}{3}$
$\iint$|积分|\iint|
$\iiint$|积分|\iiint|
$\oint$|曲线积分|\oint|$\oint_C \frac{1}{z}\mathrm{d}z=2\pi i$
$\oiint$|积分|\oiint|
$\oiiint$|积分|\oiiint|
$\nabla$|梯度|\nabla|$\nabla\cdot\vec{v}=\dfrac{\partial v_x}{\partial x}+\dfrac{\partial v_y}{\partial y}+\dfrac{\partial v_z}{\partial z}$
$\Delta$|拉普拉斯变换|\Delta| $\Delta f=\nabla ^{2}f=\nabla \cdot \nabla f$
$\Box$|非欧几里得<br>拉普拉斯算子|\Box|$\Box=\dfrac{1}{c^2}\dfrac{\partial^2}{\partial t^2}-\dfrac{\partial^2}{\partial x^2}-\dfrac{\partial^2}{\partial y^2}-\dfrac{\partial^2}{\partial z^2}$

# 线性代数

表示|定义|Latex
:---|:---|:---
$f(x)=\begin{cases} a &\text{if } b \\   c &\text{if } d \end{cases}$|定义方程|`f(x)=\begin{cases}`   <br>`a &\text{if } b \\` <br>   `c &\text{if } d` <br>`\end{cases}`
$\begin{alignedat}{2}   10&x+ &3&y = 2 \\  3&x+&13&y = 4 \end{alignedat}$|方程组|`\begin{alignedat}{2`}   <br>`10&x+ &3&y = 2 \\`   <br>`3&x+&13&y = 4` <br>`\end{alignedat}`
$\begin{aligned}  f(x) &=(m+n)^2 \\ & =m^2+2m+n^2 \end{aligned}$|多行等式|`\begin{aligned} ` <br>`f(x) &=(m+n)^2 \\` <br>`& =m^2+2m+n^2` <br>`\end{aligned}`
$\begin{matrix}   a & b \\   c & d\end{matrix}$|数组|`\begin{matrix}`   <br>`a & b \\`   <br>`c & d `<br>`\end{matrix}`
$\begin{array}{cc}   a & b \\   c & d\end{array}$|数组|`\begin{array}{cc} `   <br>`a & b \\`   <br>`c & d `<br>`\end{array}`
$\begin{pmatrix}   a & b \\   c & d\end{pmatrix}$|矩阵|`\begin{pmatrix}`   <br>`a & b \\`   <br>`c & d` <br>`\end{pmatrix}`
$\begin{bmatrix}   a & b \\   c & d\end{bmatrix}$|矩阵|`\begin{bmatrix`}   <br>`a & b \\`   <br>`c & d` <br>`\end{bmatrix}`
$\begin{vmatrix}   a & b \\   c & d\end{vmatrix}$|行列式|`\begin{vmatrix}`   <br>`a & b \\`   <br>`c & d`  <br>`\end{vmatrix}`
$\begin{Vmatrix}   a & b \\   c & d\end{Vmatrix}$|范式，模|`\begin{Vmatrix}`   <br>`a & b \\ ` <br>`c & d`  <br>`\end{Vmatrix}`
$\begin{Bmatrix}a & b \\ c & d\end{Bmatrix}$||`\begin{Bmatrix}`<br>`a & b \\` <br>`c & d `<br>`\end{Bmatrix}`
$\def\arraystretch{1.5} \begin{array}{c:c:c}   a & b & c \\ \hline   d & e & f \\   \hdashline   g & h & i\end{array}$||`\def\arraystretch{1.5}` <br>`\begin{array}{c:c:c}`   <br>`a & b & c \\` <br>`\hline`   <br>`d & e & f \\`   <br>`\hdashline`   <br>`g & h & i`<br>`\end{array}`
$\xrightarrow[under]{over}$|初等变换|`\xrightarrow[under]{over}`
$A\cong B$|矩阵等价|A\cong B
$A\sim B$|矩阵相似|A\sim B
$A\simeq B$|矩阵合同|A\simeq B
$\bar{A}$||\bar{A}
$A^*$|伴随矩阵|A^*
$\det A;\vert A \vert$|矩阵的行列式|\det A
$\mathrm{diag}(a_1,a_2,a_3)$|对角阵|\mathrm{diag}(a_1,a_2,a_3)
$A\otimes B$|克罗内克积|\otimes
$\cdots$|横点|\cdots
$\vdots$|竖点|\vdots
$\ddots$|对角点|\ddots

$\begin{pmatrix}
a_{11}&a_{12}&\cdots&a_{1n} \\
a_{21}&a_{22}&\cdots&a_{2n} \\
\vdots&\vdots&\ddots&\vdots \\
a_{m1}&a_{m2}&\cdots&a_{mn} \\
\end{pmatrix} \quad
\left(
\def\arraystretch{1.2} 
\begin{array}{cc:c} 
1&0 & 0 & 0 \\ 
0&1 & 0 &0 \\ 
\hdashline 
0&0 & 1 & 5
\end{array}
\right)$


```md
\begin{pmatrix}
a_{11}&a_{12}&\cdots&a_{1n} \\
a_{21}&a_{22}&\cdots&a_{2n} \\
\vdots&\vdots&\ddots&\vdots \\
a_{m1}&a_{m2}&\cdots&a_{mn} \\
\end{pmatrix}

\left(
\def\arraystretch{1.2} 
\begin{array}{cc:c} 
1&0 & 0 & 0 \\ 
0&1 & 0 &0 \\ 
\hdashline 
0&0 & 1 & 5
\end{array}
\right)
```

# 群论

符号|定义|Latex|示例
:---|:---|:---|:---
$b\pmod m$||b\pmod m|
$x \pod a$||x \pod a|
$a \bmod b$||a \bmod b|
$\equiv$|同余关系|\equiv|$a\equiv b\pmod m$
$\gtrdot$||\gtrdot|
$\lessdot$||\lessdot|
$\intercal$|区间|\intercal|
$\rhd$|双方关系对立|\rhd|$R\rhd S=R-R\ltimes S$
$\lhd$|正规子群|\lhd|$Z(G) \lhd G$
$\unrhd$||\unrhd|
$\unlhd$||\unlhd|
$\leftthreetimes$||\leftthreetimes|
$\rightthreetimes$||\rightthreetimes|
$\rtimes$||\rtimes|
$\ltimes$||\ltimes|
$\prec$|卡普可约|\prec|If L1 ≺ L2 and L2 ∈ P, <br>then L1 ∈ P
$\succ$||\succ|
$\mid$|分解|\mid|Since 15 = 3 × 5, <br>it is true that 3 \| 15 and 5 \| 15
$\nmid$||\nmid|



