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

# VC dimension定義

> vc dimension = Maximum **non-break** point
>
> $$d_{vc} = k-1,k=$$最小break point

以之前的四個例子來說

![](/assets/螢幕快照 2017-04-25 下午8.55.33.png)

所以什麼是一個好的H?

好的break point、有限的VC dimension

![](/assets/螢幕快照 2017-04-25 下午8.57.11.png)

答案為4，因為題目僅僅闡述有一組input data無法被shattered，但是其他input data是否能被shattered仍是未知的情況

若是所有的input data都被證明是無法被shattered的話，答案即為3

# $$d_{vc} =? d + 1 $$

![](/assets/螢幕快照 2017-04-25 下午9.02.34.png)

在一維的PLA和二維的PLA中，可以歸納出$$d_{vc} = d+1$$，但要如何證明呢？

要從兩個步驟下手：

1. $$d_{vc} \geq d+1$$
2. $$d_{vc} \leq d+1$$

最後便可得出$$d_{vc} = d + 1$$

### Step1： $$d_{vc} \geq d+1$$

要證明$$d_{vc} \geq d+1$$只需證明在d+1的維度上，**有至少一種資料可以達成所有可能的解\(Shattered\)**

![](/assets/螢幕快照 2017-04-25 下午9.08.07.png)

最左邊的為$$x_0$$，皆為常數1，而上圖的資料為特別設計過的，因此其保證此資料Ｘ是有反轉矩陣存在





