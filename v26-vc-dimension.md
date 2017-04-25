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

要證明$$d_{vc} \geq d+1$$只需證明在d+1個資料上，**有至少一種可能可以達成所有的解\(Shattered\)**

![](/assets/螢幕快照 2017-04-25 下午9.08.07.png)

最左邊的為$$x_0$$，皆為常數1，而上圖的資料為特別設計過的，因此其保證此資料Ｘ是有反轉矩陣存在

![](/assets/螢幕快照 2017-04-25 下午9.11.20.png)

為了shattered這種特別的資料，因此需要求得一個w\(特徵權重矩陣\)是可以求得任何可能的解y矩陣的

y矩陣有$$2^{d+1}$$種可能，由於w可以由x的反轉矩陣乘上y獲得的，因此在這個input data中是可以shatter所有解的

$$\therefore d_{vc} \geq d+1$$

### Step2： $$d_{vc} \leq d+1$$

要證明$$d_{vc} \leq d+1$$需要證明在d+2個資料裡，_**完全沒有機會**_可以達成所有的可能解

![](/assets/螢幕快照 2017-04-25 下午9.18.57.png)

當列數多於行數時，一定會造成linear dependence\(即其內的$$x_{k}$$可被其他資料所組合而成\)

因此當我們將某$$x_k$$移至最後一行成為$$x_{d+2}$$時，即可得到某種linear dependence的式子

![](/assets/螢幕快照 2017-04-25 下午9.23.28.png)

上述表達的僅是一種可能性，$$x_{d+2}$$這個點因為linear dependence的關係，所以無法同時表達出兩種解\(取sign\)

**一個式子畢竟只能表達出一種解**

因此無論換了多少input data，都無法shatter該input data，表達出所有的解

$$\therefore d_{vc} \leq d+1$$

### Step 3：得證$$d_{vc} = d+1$$

$$\because d_{vc} \geq d+1  $$ && $$d_{vc} \leq d+1$$

$$\therefore d_{vc} = d+1$$

# VC dimension代表的意義

> Penalty for model complexity

![](/assets/螢幕快照 2017-04-25 下午9.42.15.png)

當使用$$\delta$$代替$$4(2N)^{d_{vc}}exp(-\frac{1}{8}\epsilon^2N)$$後，便可得到

$$\epsilon = \sqrt{\frac{8}{n}ln(\frac{4(2N)^{d_{vc}}}{\delta})}$$



