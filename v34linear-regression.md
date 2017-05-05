# Hypothesis

$$y\approx \sum_{i=0}^dw_ix_i$$

$$h(x) = w^Tx$$

# Error Measure

$$square\ error: err(\hat{y},y) = (\hat{y}-y)^2$$  ，$$\hat{y}$$為預測的值

### in-sample:

$$E_{in}(h) = \frac{1}{N}\sum^N_{n=1}(h(x_n)-y_n)^2$$

$$E_{in}(w) = \frac{1}{N}\sum^N_{n=1}(w^Tx_n-y)^2$$

### out-sample:

$$E_{out}(w) = \varepsilon_{(x,y)\sim P}(w^Tx-y)^2$$

# How to minimize $$E_{in}$$ ?

再轉為matrix form後，$$min_wE_{in}(w) = \frac{1}{N}\|Xw-y\|^2$$

由於此函數是可微的，因此得到一個convex的模型，藉此得到**最佳解**

![](/assets/83wqur239fraud.png)

而這個最低點\(最佳解\)的梯度\(微分\)是多少呢?

![](/assets/98r32hjdjdoisadj3289.png)

皆應該要為0，使其成為最佳解的必要條件

# 求得$$E_{in}的梯度(\nabla E_{in})$$

# 



