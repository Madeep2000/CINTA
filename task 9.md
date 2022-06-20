# task 9

2.

$x = 41$

$11\ mod\ 19$ 的逆元  $7$

$19\ mod\ 11$  的逆元  $-4 (或7)$

3.

$x = 1731$

$b_1^{-1}=693$

$b_2^{-1}=495$

$b_3^{-1}=385$

$b_4^{-1}=315$

4.

$x ≡ a (mod\ m)$

$x ≡ a (mod\ n)$

得

$(x-a)|m$ $且$ $(x-a)|n$

$∴(x-a)|mn$

$∴x$模$mn$等于$a$

C++ code:

```cpp
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
		
			if(a>b){                  //ÈÃ a<=b 
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

// p > q
int CRT(int a,int b,int p,int q,int &r0,int &s0){
	
	int r1,s1;
	r0=1,r1=0,s0=0,s1=1;
	
	int d = begcd(p,q,r0,r1,s0,s1);
	if(d == 1){
		int p_re = r0;
		int q_re = s0;
		
		int y = a*q*q_re + b*p*p_re;
		y %= (p * q);
		if(y < 0){
			y += p*q;
		}		
		return y;
	}

	else{
		return 0;
	}

}

int ECRT(int m[],int a[],int b[],int len){
	int x = 0;
	int r0,r1,s0,s1;
	int sum = 1;
	
	for(int i=0;i < len;i++){
		sum*=m[i];
	}

	for(int i = 0;i < len;i++){
		b[i] = sum/m[i];
		r0=1,r1=0,s0=0,s1=1;
		
		if(b[i] < m[i]){
			begcd(m[i],b[i],r0,r1,s0,s1);
			x += a[i]*b[i]*s0; 
		}
		else{
			begcd(b[i],m[i],r0,r1,s0,s1);
			x += a[i]*b[i]*r0; 
		}
		
	}
	x %= sum;
	if(x<0){
		x += sum;
	}
	
	return x;

}

int main(){
	int r0=1,s0=0;
	int len;
	cin>>len;
	int m[len],a[len];
	for(int i=0;i<len;i++){
		cin>>a[i]>>m[i];
	}
	int b[len];
	
	int temp = ECRT(m,a,b,len);
	//	int temp = CRT(3,8,19,11,r0,s0);
	
	cout<<temp;
	return 0;
}
```