# Task 12

2.如果任取环 $R$ 中的元素$x$都满足$x^2 = x$，请证明环$R$是交换环。

证：

$∵$ 任取环 $R$ 中的元素$x$都满足$x^2 = x$

任取 $a,b ∈ R$

有$(-a)(-a) = -a = a$

$∴(a+b)(a+b) = a + ba + ab + b = a+b$

$∴$ $ba + ab = 0$

$∴ ba = -（ab）= ab$

所以 $R$ 是交换环

3.记 $\Z[\sqrt 2]$ $= \{ a + b\sqrt 2 : a,b ∈ Z\}$，请证明$\Z[\sqrt 2]$ 是环，且是整环。

证：

乘法对加法的分配律显然存在

$①加法交换群：$

加法交换律显然存在

任取 $a,b,c,d,e,f ∈ Z$

$(a+b\sqrt 2) + ((c+d\sqrt 2)+(e+f\sqrt 2))$ 

$= (a + c + e) + (b+d+f)\sqrt 2$  

$=( (a+b\sqrt 2) + (c+d\sqrt 2) )+(e+f\sqrt 2)$

$∴ \Z[\sqrt i]$ 有加法结合律

显然 $0 + 0\sqrt 2 = 0$ 是加法单位元

任取 $a,b,c,d ∈ Z$

有 $a + b\sqrt 2 + c + d\sqrt 2 = (a + c) + (b + d)\sqrt 2$ 

$∵ (a + c) ,(b + d)∈ Z$

$∴(a + c) + (b + d)\sqrt 2 ∈ \Z[\sqrt 2]$

$∴ \Z[\sqrt 2]$对加法有封闭性

取$a,b$在 $Z$ 中的加法逆元，有

$a + b\sqrt 2 + (-a) + (-b)\sqrt 2 = 0$

$∴\Z[\sqrt 2]$中任意元素有加法逆元

$∴\Z[\sqrt 2]$ 是加法交换群

$②乘法半群：$

乘法交换律显然存在

$2 = 2+0\sqrt2 ∈ \Z[\sqrt 2]$

任取 $a,b,c,d,e,f ∈ Z$

$(a+b\sqrt 2) * ((c+d\sqrt 2)*(e+f\sqrt 2))$ 

$= (ace+2adf+2bde+2bcf) + (ade+acf+bce+2bdf)\sqrt 2$  

$=( (a+b\sqrt 2) * (c+d\sqrt 2) )*(e+f\sqrt 2)$

$∴ \Z[\sqrt i]$ 有乘法结合律

$(a + b\sqrt 2) * (c + d\sqrt 2)$ 

$= ac + cb\sqrt 2 + ad\sqrt 2 + 2bd$ 

$= (ac + 2bd) + (cb + ad)\sqrt 2$

$∈ \Z[\sqrt 2]$

$∴\Z[\sqrt 2]$对乘法封闭

$∴ \Z[\sqrt 2]$ 是乘法半群

$∴\Z[\sqrt 2]$ 是交换环

显然 $1 + 0\sqrt2 = 1$ 是乘法单位元

所以 $\Z[\sqrt 2]$ 是带单位元的环

假设该环不是无零因子环

不妨设$(a+b\sqrt2)$为环中的零因子且$(a+b\sqrt2) ≠ 0$

则有：

$(a+b\sqrt2)*(c+d\sqrt2)$

$=  0$

$= (c+d\sqrt2) - (c+d\sqrt2)$

$∴(a+b\sqrt2)*(c+d\sqrt2) + (c+d\sqrt2) =  (c+d\sqrt2)$

由乘法对加法的分配律和加法交换律得

$((a+1)+b\sqrt 2)*(c+d\sqrt2) = (c+d\sqrt2)$

由$c+d\sqrt 2$的一般性和乘法单位元的定义有：

$((a+1)+b\sqrt 2) = 1$

$∴a+b\sqrt 2 = 0$ 与$(a+b\sqrt2) ≠ 0$ 相矛盾

$∴$环是无零因子环

所以$\Z[\sqrt 2]$ 是整环

4.记$\Z[\sqrt i]$ $= \{a+bi : a,b ∈ Z\}$，请证明 $\Z[\sqrt i]$是整环。

乘法对加法分配律显然存在

$①加法交换群：$

加法交换律显然存在

任取 $a,b,c,d,e,f ∈ Z$

$(a+b\sqrt i) + ((c+d\sqrt i)+(e+f\sqrt i))$ 

$= (a + c + e) + (b+d+f)\sqrt i$  

$=( (a+b\sqrt i) + (c+d\sqrt i) )+(e+f\sqrt i)$

$∴ \Z[\sqrt i]$ 有加法结合律

显然 $0 + 0\sqrt i = 0$ 是加法单位元

$a + b\sqrt i + c + d\sqrt i = (a + c) + (b + d)\sqrt i$ 

$∵ (a + c) ,(b + d)∈ Z$

$∴(a + c) + (b + d)\sqrt i ∈ \Z[\sqrt i]$

$∴ \Z[\sqrt i]$ 对加法有封闭性

取 $a,b$ 在 $Z$ 中的加法逆元，有

$a + b\sqrt i + (-a) + (-b)\sqrt i = 0$

$∴\Z[\sqrt i]$中任意元素有加法逆元

$②乘法半群$

乘法交换律显然存在

$(-1) = -1 + 0\sqrt i ∈ \Z[\sqrt i]$

任取 $a,b,c,d,e,f ∈ Z$

$(a+b\sqrt i) * ((c+d\sqrt i)*(e+f\sqrt i))$ 

$= (ace-adf-bde-bcf) + (ade+acf+bce-bdf)\sqrt i$  

$=( (a+b\sqrt i) * (c+d\sqrt i) )*(e+f\sqrt i)$

$∴ \Z[\sqrt i]$ 有乘法结合律

$(a + b\sqrt i) * (c + d\sqrt i)$ 

$= ac + bc\sqrt i + ad\sqrt i - bd$ 

$= (ac - bd) + (cb + ad)\sqrt i$

$∈ \Z[\sqrt i]$

$∴\Z[\sqrt i]$对乘法封闭

$∴\Z[\sqrt i]$是乘法半群

$∴\Z[\sqrt i]$ 是交换环

显然 $1 + 0\sqrt i = 1$ 是乘法单位元

所以 $\Z[\sqrt i]$ 是带单位元的环

假设$(a+b\sqrt i)$为环中的零因子且$(a+b\sqrt i) ≠ 0$

则有：

$(a+b\sqrt i)*(c+d\sqrt i)$

$=  0$

$= (c+d\sqrt i) - (c+d\sqrt i)$

$∴(a+b\sqrt i)*(c+d\sqrt i) + (c+d\sqrt i) =  (c+d\sqrt i)$

由分配律和加法交换律得

$((a+1)+b\sqrt i)*(c+d\sqrt i) = (c+d\sqrt i)$

由$c+d\sqrt i$ 的一般性乘法单位元的定义有：

$((a+1)+b\sqrt i) = 1$

$∴a+b\sqrt i = 0$ 与假设相矛盾

$∴$环是无零因子环

所以$\Z[\sqrt i]$ 是整环

5.如果 $I$ 和 $J$ 都是交换环$R$ 的理想，则$I+J$ $= \{i+j: i∈I,j∈J\}$也是$R$的理想。

证：

$①I + J 是 R 的子环$

$∵ I$ 和 $J$ 是$R$的子环

$∴ I + J \subset R$ 

$∴I + J$ 中加法交换律和结合律存在

且乘法对加法具有分配律

$∵0 \in I 且 0 \in J$

$\therefore 0 = 0 + 0 \in I + J$

$\forall i \in I, j \in J$

$0 + i + j = i + j + 0 = i + j$ 

$\therefore I + J$ 中有加法单位元 $0$

对于 $i$ 在 $I$ 中的加法逆元 $-i$ 和 $j$ 在 $J$ 中的加法逆元 $-j$,有 

$i + j + (-i) + (-j)$

$= i - i + j - j$

$= 0$

$∴I + J$ 中所有元素均有加法逆元

$∴\forall i_1,i_2 \in I, j_1, j_2 \in J$

 $i_1 + j_1 + i_2 + j_2$

$= (i_1 + i_2) + (j_1 + j_2)$

由$I$和$J$的封闭性知 $(i_1 + i_2) \in I , (j_1 + j_2) \in J$

$∴  i_1 + j_1 + i_2 + j_2 \in I + J$

$∴ I + J$ 具有加法封闭性

$∴ I + J$ 是加法交换群

$(i_1 + j_1) * (i_2 + j_2)$

$= (i_1+ j_1) * i_2 + (i_1+ j_1)*j_2$

由I 和 J 的吸收律可知

$(i_1+ j_1) * i_2 \in I 且  (i_1+ j_1)*j_2 \in J$

$∴(i_1 + j_1) * (i_2 + j_2)  \in I + J$

即 $I + J$ 具有乘法封闭性

$∴ I + J$ 是环且是$R$的子环

②吸收律

$\forall i \in I, j \in J$

$\forall r \in R$,由分配律有

$r(i+j) = ri + rj$

其中 $ri \in I, rj \in J$

$∴r(i+j) \in I+J$

即$r(I + J) \subset I + J$

6.命题12.4的证明：

设映射 $ϕ : R → R^′$ 是环同态，则：

1. 如果 $R$ 是交换环，则 $ϕ(R)$ 也是交换环。

$\forall a,b \in R$,有$ab = ba$

$\therefore \phi(a)\phi(b) = \phi(ab) = \phi(ba) = \phi(b)\phi(a)$

$∴ϕ(R)$是交换环

2. 分别记 $0$ 和 $0'$ 是 $R$ 和 $R^′$ 的加法单位元，$ϕ(0) = 0^′$。

$0'+\phi(0) = \phi(0) = \phi(0+0) = \phi(0) + \phi(0)$

两边分别加上$\phi(0)$ 的加法逆元

有$0' = \phi(0)$

3. 分别记 $1$ 和 $1'$ 是 $R$ 和 $R^′$ 的乘法单位元，如果 $ϕ$ 是满射，则 $ϕ(1) = 1'$。

$\forall a \in R$

$a = a*1 = 1*a$

$\phi(1)\phi(a) = \phi(1*a) = \phi(a) = \phi(a*1) =\phi(a)\phi(1)$

由$\phi(a)$的一般性和乘法单位元的定义可知

$\phi(1) = 1'$