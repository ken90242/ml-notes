# $$m_H(N)的上限$$＆回顧

# ![](/assets/螢幕快照 2017-04-25 下午8.44.48.png)

原先Bounding function已經比確切的數目多了不少

![](/assets/螢幕快照 2017-04-25 下午8.46.11.png)

現在為了清楚描述VC dimension，我們將上限再上調至$$N^{k-1}$$

因此現在函數演進至：

![](/assets/螢幕快照 2017-04-25 下午8.48.30.png)

而上述函數也描述了機器學習是如何發揮作用的：

1. $$m_H(N)$$的break point為3$$\longrightarrow$$ good H
2. N的數量夠大\($$E_{in} \approx E_{out}$$\)$$\longrightarrow$$ good D
3. A選到一個hypothesis g，獲得小的$$E_{in}$$$$\longrightarrow$$ good A
4. 好的運氣\(不能總是選到壞資料呀\)

# VC dimension

> vc dimension = Maximum **non-break** point
>
> $$d_{vc} = k-1,k=$$最小break point

以之前的四個例子來說

![](/assets/螢幕快照 2017-04-25 下午8.55.33.png)

所以什麼是一個好的H?

好的break point、有限的VC dimension













