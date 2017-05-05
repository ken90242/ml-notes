# Linear Regression真的是機器學習嗎?

![](/assets/78293hf9823hf921hj3r9823.png)

# 怎麼讓$$E_{out}變好?$$

$$\overline{E_{in}} = \varepsilon_{D \sim P^N}(E_{in} (w\ \ \ w.r.t\ \ \ D)$$

$$= \frac{1}{N}\|y-\hat{y}\|^2 = \frac{1}{N}\|y-XX^{\dagger}y\|^2 = \frac{1}{N}\|(I-XX^{\dagger})y\|^2$$

**let **$$XX^{\dagger}$$** become **$$H$$**\(hat matrix\)**

$$= \frac{1}{N}\|(I-H)y\|^2$$

![](/assets/d9j328fj9283f92h.png)

在一個多維度的空間中，$$\hat{y}$$就是我們計算$$w^Tx$$的結果，就是在x的平台上伸縮w的比例

而y則是原本的資料標籤，$$y-\hat{y}$$則是現實跟預測的差距

H則是將$$y$$ 投影至x的平台上，成為$$\hat{y}$$               $$\because \hat{y} = XX^{\dagger}y = Hy$$

至於I-H則是將$$y$$ 投影成$$y-\hat{y}$$                    $$\because y-\hat{y} = (I-H)y$$

![](/assets/dioj2938jr923j9f32f32.png)

當我們再看仔細一點時，會發現這個$$y$$ 實際上是由f\(x\)與noise所組成的資料，由於f\(x\)是完美的，因此並不會犯錯

所有犯錯的可能都存在於noise上，而這個犯錯就是$$y-\hat{y}$$

前面提到I-H是將$$y$$ 投影成$$y-\hat{y}$$ ，但現在我們知道f\(x\)並不會犯錯，**因此實際上**$$y-\hat{y}$$** 是完全由noise藉由I-H投影而成的**

![](/assets/rj2983rhj932jdajdoi.png)

> 原來有N個自由度的向量，現在要投影在d+1維的空間\(因為x最多有d個feature+1個常數\)，因此其自由度剩下N-\(d+1\)

$$\therefore E_{in}(w) = \frac{1}{N}\|y-\hat{y}\|^2 = \frac{1}{n}\|(I-H)noise\|^2= \frac{1}{n}(N-D+1)\|noise\|^2$$

# 所以$$\overline{E_{in}}$$跟$$\overline{E_{out}}$$的關係?

# ![](/assets/fj9832f93f8j9f.png)

$$\overline{E_{in}}$$之所以少了$$\frac{d+1}{N}$$是因為訓練時會為了最小化錯誤往雜訊那邊fit，讓E\_in好看一點

$$\overline{E_{out}}$$之所以多了$$\frac{d+1}{N}$$，若是剛好往雜訊反方向篇則為會增加

![](/assets/jf3984fj9ewjf9ew8hf.png)

當N的數量越來越大時，$$\overline{E_{in}}$$跟$$\overline{E_{out}}$$會收攏成為近似$$\sigma^2$$\(noise level\)

而generalization error為$$\frac{2(d+1)}{N}$$

![](/assets/lflkkfkfkfkfkfk8932yr932yr.png)

