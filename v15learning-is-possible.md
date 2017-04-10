# 有沒有辦法推論未知?

![](/assets/h34ifweimport.png)

假設欲得知橘色彈珠的比例，可使用抽樣\(sample\)

![](/assets/imphfuewf3ort.png)

在sample中，橘色彈珠的比例為$$\nu$$

在母體中，橘色彈珠的比例為$$\mu$$

### 那$$Sample的\nu跟母體的\mu有什麼關係?$$

$$\nu跟\mu$$很有可能相差甚遠，也有可能差距極小

因此要借助統計上的概念：Hoeffding's Inequality\(霍夫丁不等式\)來釐清彼此的關係

### **Hoeffding's Inequality**

![](/assets/imhoeffdingport.png)

> 抽樣數越大，$$\nu跟\mu的$$差距越小

這裡的$$\epsilon$$ 指的是可容忍的誤差機率，$$\exp(n)$$則代表$$e^n$$\(e為常數\)

### 例題

![](/assets/impy43hg43123ort.png)

$$\epsilon$$\(可容忍誤差\) = $$|\nu-\mu| = 0.3$$ , $$N = 10$$

bound =Upper-bound\( $$\mathbb{P}[|\nu-\mu|>\epsilon]$$ \) = $$2exp(-2\epsilon^2N)$$ 

=$$2*e^{-2\times 0.09\times 10} \approx 0.33$$ 

而實際的機率為$$C^{10}_1(0.4)(0.6)^9 + C^{10}_0(0.6)^{10} \approx 0.4635$$

