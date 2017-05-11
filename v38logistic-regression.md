# Logistic Regression

> 想要知道的不是【有沒有】，而是【可能性】

* ### Hypothesis

先使用權種w跟特徵x來計算出一個機率數值s

$$s = \sum_{i=0}^dw_ix_i$$

再將s轉換為$$[-1,1]$$區間的機率$$\theta(s)$$，此$$\theta$$ 函數唯一個sigmoid函數\(S型\)

$$\theta(s) = \frac{e^s}{1+e^s} = \frac{1}{e^{-s}+1} $$

![](/assets/fh2983hf9823djed.png)

> $$\theta$$ 函數是為了 當s高時，機率要趨近1，而當s低時，機率要趨近0
>
> e.g. $$\theta(-\infty) = 0$$       $$\theta(0) = \frac{1}{2}$$           $$\theta(\infty) = 1$$

**因此，logistic hypothesis為**$$h(x) = \theta(w^Tx)$$

* ### Error Function

> 一個完美的hypothesis是能完全產生所有沒有雜訊的資料
>
> 換句話說
>
> f\(x\)是最能夠產生我們所擁有的資料D

$$D = {(x_1,true),(x_2,false),...,(x_N,false)}$$

![](/assets/jf982fj9wejf98ewjf.png)

f\(x\)產生D的機率：$$P(x_1)f(x_1) \times P(x_2)(1-f(x_2))\times ...\times P(x_N)(1-f(x_N))$$

**這個機率大小會是所有hypothesis中最大的，趨近於1**

因此若是我們要找到一個hypothesis h\(x\)相近於f\(x\)

便將h\(x\)替換f\(x\)，並求最大化：$$P(x_1)h(x_1) \times P(x_2)(1-h(x_2))\times ...\times P(x_N)(1-h(x_N))$$

又由於sigmoid函式的特殊性質\(如下圖所示\)：$$1 - h(x) = 1- \theta(x) = \theta(-x) = h(-x)$$

![](/assets/jf98jw9e8jfew89jf.png)

又由於P\(x\)對於要競爭的每一個hypothesis都算是固定不變的

又利用特徵x與標籤y相乘可表示相對應的輸入

因此可改寫為$$h(x_1) \times h(-x_2)\times ...\times h(-x_N) = \prod_{n=1}^N{h(x_ny_n)}$$

再將h替換成w的關係式子

$$\prod_{n=1}^N{h(y_nx_n)} 
\propto \prod_{n=1}^N{\theta(y_nw^Tx_n)}$$

取以e為底的log

$$\prod_{n=1}^N{\theta(y_nw^Tx_n)} \propto ln\sum_{n=1}^N{\theta(y_nw^Tx_n)}$$

再從求最大值轉換為求最小值\(轉負號\)，並求平均

$$\frac{1}{N}\sum_{n=1}^N{-ln\theta(y_nw^Tx_n)}$$

最後再將$$\theta(s) = \frac{1}{1+exp(-s)}$$代入得：

$$\frac{1}{N}\sum_{n=1}^N{-ln(y_nw^Tx_n)}$$

