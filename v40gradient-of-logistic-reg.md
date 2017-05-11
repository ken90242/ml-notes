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

1. $$\theta(-y_nw^Tx_n) = 0 \Longrightarrow -y_nw^Tx_n =  -\infty \Longrightarrow y_nw^Tx_n = \infty
    $$

但這代表所有預測$$Sign(w^Tx_n) = y_n$$，也就是Linear separable

asdasdasd





