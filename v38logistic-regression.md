# Logistic Regression

> 想要知道的不是【有沒有】，而是【可能性】

* ### Hypothesis

先使用權種w跟特徵x來計算出一個機率數值s

$$s = \sum_{i=0}^dw_ix_i$$

再將s轉換為$$[-1,1]$$區間的機率$$\theta(s)$$，此$$\theta$$ 函數唯一個sigmoid函數\(S型\)

  
$$\theta(s) = \frac{e^s}{1+e^s} = \frac{1}{e^{-s}+1} $$

![](/assets/fh2983hf9823djed.png)

> $$\theta$$ 函數是為了 將



**因此，logistic hypothesis為**$$h(x) = \theta(w^Tx)$$



