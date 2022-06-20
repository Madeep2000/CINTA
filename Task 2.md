# Task 2

写一个迭代版本的gcd算法程序和二进制gcd算法程序

```cpp
//gcd
#include<iostream>
using namespace std;

unsigned int gcd(unsigned int a,unsigned int b){
	
	while(b){
		unsigned int temp=a;
		a=b;
		b=temp%b;
	}
	return a;
}

int main(){
	cout<<gcd(60,15);
}

//bgcd
#include<iostream>
using namespace std;
unsigned int bgcd(unsigned int a,unsigned int b){  
	int k=0;
	while(((a|b)&1)==0){   
		a=a>>1;
		b=b>>1;
		k++;
	}
	while((a&1)==0){
		a=a>>1;
	}
	while(b!=0){
		while((b&1)==0){
			b=b>>1;
		}
		if(a>b){                   
			unsigned int temp=a;
			a=b;
			b=temp;
		}
		b=b-a; 
	}
	return (a<<k);
}

int main(){
	cout<<bgcd(72,12);
}
```

写一个递归版本的egcd程序和二进制egcd算法程序

```cpp
//egcd
#include<iostream>
using namespace std;

int egcd(int a,int b,int r0, int r1,int s0,int s1,int arr[]){
	if(b==0){
		arr[0]=r0;
		arr[1]=s0;
		return a;
	}
	else{	
		egcd(b,a%b,r1,r0-a/b*r1,s1,s0-a/b*s1,arr);
	}
}

int main(){
	int r0=1,r1=0,s0=0,s1=1;
	int output[2];
	int d=egcd(131,73,r0,r1,s0,s1,output);
	cout<<d<<endl;
	cout<<output[0]<<" "<<output[1];
}

//begcd
#include<iostream>
using namespace std;

void exchange(int* a,int* b){
    int tmp = *a;
    *a = *b;
    *b = tmp; 
}

int begcd(int a,int b,int &r0,int r1,int &s0,int s1){  // a>b 
  	int tempa=a;
  	int tempb=b;
	int k=0;
  	while(a&1==0 && b&1==0){
  		a=a>>1;
		b=b>>1;
		k++;
	}
	
	while(b!=0){
		
		while(a&1==0){
			a=a>>1;
			if(r0&1==0 && s0&1==0){
				s0=s0>>1;
				r0=r0>>1;
				
			}
			else{
				s0=(s0+tempb)>>1;
				r0=(r0+tempa)>>1;
			}
		}
		
		while(b&1==0){
			b=b>>1;
			if(r1&1==0 && s1&1==0){
				s1=s1>>1;
				r1=r1>>1;
				
			}
			else{
				s1=(s1+tempb)>>1;
				r1=(r1+tempa)>>1;
			}
		}
		
		if(a>b){                  //让 a<=b 
			exchange(&r0,&r1);
			exchange(&s0,&s1);
			exchange(&a,&b);
		}
		
		b=b-a;
		s1=s1-s0;
		r1=r1-r0;	
	}
	return (a>>k);
}

int main(){
	int r0=1,r1=0,s0=0,s1=1;
	int d=begcd(131,73,r0,r1,s0,s1);
	cout<<d<<endl;
	cout<<r0<<" "<<s0<<endl;
	
}
```

请完成定理2.2的证明

设 a 和 b 为非零整数，存在整数 r 和 s 使得：gcd(a, b) = ar + bs，而且，a 与 b 的最大公因子是惟一的。称 r 和 s 为 Bézout 系数。

证：

am+bn＝0时显然成立，

构造集合 S = {am+bn | m,n ∈ Z 且 am+bn > 0}

显然S非空

那么由良序原则知

S有最小值 d = ar + bs

令 a = dq + r' ,

其中 0 ≤ r' ＜d , q ∈ Z

假设r' > 0,则

r' = a - dq

   = a - (ar+ds)q

   = a - arq - bsq

   =  a(1-rq) + b(-sq)

   ∈ S

与S中最小值是d相矛盾

∴假设不成立

即 r' = 0

∴ d|a

同理 d|b

∴d 是 a与b的公因子

若 $\exists$  $d'≠d$ 使得 $d'|a$ 且 $d'|b$ ,则有：

$a = d'h, b = d'k$ 

$∴d = ar + bs = d'hr + d'ks = d'(hr+ks)$

$∴d'|d$

$∴d = gcd(a,b)$