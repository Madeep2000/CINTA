# Task 1

用 C 语言编程实现一种迭代版本的简单乘法。

```cpp
#include<iostream>
using namespace std;
unsigned int mul(unsigned int a,unsigned int b){
	unsigned int sum=0;
	
	for(int i=0;b!=0;i++){
		if(b&1){
			sum=sum+(a<<i);

		}
		b=b>>1;
	}
	return sum;	
}

int main(){
	cout<<mul(10,71);
}

```

证明命题1.1：

设 $a, b, c ∈ Z$，如果 $a | b$，$b | c$，则 $a | c$。如果 $c | a$，$c | b$，则对任意 $m, n ∈ Z$，有
$c | (ma + nb)$。

证:

如果 $a | b$，$b | c$，

由除法算法得:

$b = qa + r$,

$c = Qb + R$

得 $c = Q (qa + r) + R$

$= Qqa + Qr + R$

显然上式可化为形如 $c = ka + r$ 的形式

$∴ a | c$

如果 $c | a$，$c | b$，

由除法算法得：

$a = qc + r$

$b = Qc + R$

$∴ ma + nb = ( qm + Qn ) c + rm + Rn$

显然上式可化为形如 $ma + nb = kc + r$ 的形式

$∴ c | (ma + nb)$

定理1.1除法算法的证明：

存在性.

构造集合

$S = \{a − bk : k ∈ Z\ 且\ a − bk ≥ 0\}.$

显然，集合 S 非空。由良序原则，存在一个最小元 $r ∈ S$，且 $r = a − qb$。

因此， $a = qb + r, r ≥ 0$。

假设$r ≥ b$,则

存在一个正整数 $c$ 使得 $r = b + c$，

则 $c = r-b = a – qb – b = a – (q+1) b$

$∴ c ∈ S$

$∵ r ∈ S$ 且 $r$ 是 $S$ 中最小元

与 $c < r$ 相矛盾

$∴$ 假设不成立

即 $r < b$

唯一性

假设存在不唯一的整数对 $q$ 和 $r$ 以及 $Q$ 和 $R$ 使得

$a = qb + r = Qb + R$ 且 $0 ≤ r < R <b$

其中 $r ,R ∈ S$ 且 $r$ 为 $S$ 中最小元

$∵ r ＜ R ，qb + r = Qb + R , b > 0$

$∴ q ＞Q$

$∴$ 存在正整数 $c$ 使 $r + c = R$ ，正整数 $d$ 使 $Q + d = q$

$∴ a = Qb + R = ( q – d )b + r + c = qb + r + c – db$

$∴ c = db$

$∴ R = r + db ≥ b$ 与 $R < b$ 相矛盾

$∴$假设不成立

$∴$存在唯一整数对$q$和$r$