# 回到原本的Bad Bound

![](/assets/螢幕快照 2017-04-25 下午5.42.25.png)

分成三個步驟

1. replace $$E_{out}$$ by $$E_{in}^\prime$$
2. decompose H by kind
3. use Hoeffding without replacement

# Step1: Replacement

因為$$E_{out}$$為無限多個，因此無法直接將$$m_N(N)$$帶入，因此要先將$$E_{out}$$轉為有限多個

方法就是再取一個$$E_{in}^\prime$$，其取樣的數量等於$$E_{in}$$

![](/assets/螢幕快照 2017-04-25 下午5.48.57.png)

但是怎麼確保其與原本$$E_{out}$$發生壞事機率的關係呢？

![](/assets/螢幕快照 2017-04-25 下午5.49.01.png)

由於$$E_{out}$$可以說是變相的平均，而我們取$$E_{in}^\prime$$有一半的機率會選到壞資料\(比原本$$E_{in}與E_{out}$$的距離還遠\)

![](/assets/螢幕快照 2017-04-25 下午5.49.03.png)

![](/assets/螢幕快照 2017-04-25 下午5.51.51.png)

因為有一半的機率會選到壞資料，因此$$\mathbb{P}$$前面加上$$\frac{1}{2}$$，$$\epsilon改為\frac{\epsilon}{2}$$是出於數學推導考量

# Step2: Decompose H by kind

由於我們只取樣了$$E_{in}與E_{in}^\prime$$，設取的樣本數量皆為N，我們所取的樣本總數量即為2N，又因前述Bounding function可知  
在已知break point的情況下，$$m_H(N)$$為polynomial bounded，因此可將其直接帶入：

![](/assets/螢幕快照 2017-04-25 下午5.59.28.png)

\(見[V17:Connection to real](/v17connection-to-real.md)\)

# Step3: Use Hoeffding without Replacement

由於fixed h只是一個固定的hypothesis，要比較一個sample與所有平均便須用到Hoeffding了

![](/assets/螢幕快照 2017-04-25 下午6.08.32.png)



除此之外，為了將$$E_{out}$$重新加回算式，從$$|E_{in}-E_{in}^\prime| > \frac{\epsilon}{2} \leftrightarrow | E_{in}-\frac{E_{in}+E_{in}^\prime}{2}|>\frac{\epsilon}{4}$$，因為$$E_{out} \approx \frac{E_{in}+E_{in}^\prime}{2}$$

![](/assets/螢幕快照 2017-04-25 下午6.03.22.png)

套用上述兩點得論：

![](/assets/螢幕快照 2017-04-25 下午6.08.29.png)

# Final

![](/assets/螢幕快照 2017-04-25 下午6.11.15.png)



