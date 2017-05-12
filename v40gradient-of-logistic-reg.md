# Minimize $$E_{in}(w)$$

前段所求的Cross-Entropy Error為$$\frac{1}{N}\sum_{n=1}^N ln({1+exp(-y_nw^Tx_n))}$$

$$\therefore Min(w)$$      $$  E_{in}(w) = \frac{1}{N}\sum_{n=1}^N ln({1+exp(-y_nw^Tx_n))}$$

![](/assets/jd28jd92jddt.png)

因為$$E_{in}(w)$$為一convex函數\(未詳細說明\)，因此可找到最佳解

而找到最佳解w意味著要令$$\nabla{E_{in}(w)} = 0$$

### 求$$\nabla{E_{in}(w)}$$

![](/assets/fj398fjwfj98e2jfh23f.png)

$$\therefore \nabla{E_{in}(w)} = \frac{1}{N}\sum_{n=1}^N{\theta(-y_nw^Tx_n)(-y_nx_n)}$$

### 令$$\nabla{E_{in}(w)} = 0$$

有兩種可能：

1.$$\theta(-y_nw^Tx_n) = 0 \Longrightarrow -y_nw^Tx_n = -\infty \Longrightarrow y_nw^Tx_n = \infty$$

但這代表所有預測$$Sign(w^Tx_n) = y_n$$，也就是Linear separable

但我們無法確定一定是Linear separable

2.Weight sum = 0

但我們沒有一個直接的方法來算出答案，怎麼辦呢?

### Iterative Optimization：Gradient Descent

參考PLA後的變形

$$w_{t+1} = w_t + \eta{v}$$

![](/assets/f434398rh39ght.png)

這邊的$$w_t$$會創造出一個$$E_{in}$$_，_$$w_{t+1}$$則是更新後的權重

> 那麼$$w_{t+1}$$要選什麼才能達到下降的目的\($$E_{in}$$變小\)?

首先使用Greedy來找到$$w_{t+1} ( = w_t+\eta{v} )$$ 帶入後所得最小的$$E_{in}$$

![](/assets/fejsfdosjf9843hf9438ht.png)

再利用Taylor expression來得到線性的式子\(前提：$$\eta$$ 很小\)

$$min_{\|v\|=1}$$     $$E_{in}(w_t+\eta{v}) \approx E_{in}(w_t) + \eta{v^T}\nabla{E_{in}}(w_t)$$

由於$$E_{in}與\eta$$ 對於不同的候選$$w_t$$ 都是不變的，因此可以直接忽略，換句話說只需比較以下的式子：

$$min_{\|v\|=1}$$     $$v^T\nabla{E_{in}(w_t)}$$

而$$\nabla{E_{in}(w_t)}$$是已知的，因此若要求得最小的值，$$v^T$$須為負的向量且向量長度為1：

$$v^T = \frac{\nabla{E_{in}(w_t)}}{\|\nabla{E_{in}(w_t)}\|}$$



$$\therefore w_{t+1} = w_t + \eta{\frac{\nabla{E_{in}(w_t)}}{\|\nabla{E_{in}(w_t)}\|}}$$\(最好的一步\)

