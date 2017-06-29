* $$\min_{w\in\mathbb{R}}$$$$E_{in}(w) = \frac{1}{N}\sum_{n=1}^N(w^Tz_n - y_n)^2= \frac{1}{N}\sum^N_{n=1}(Zw-Y)^T(Zw-Y)$$

* $$s.t. \sum^Q_{q=0}w_q^2<C$$

上述兩點即表示了前述Regularization的限制及原本Error求最小的兩式

![](/assets/iasdjasoidjosajdoasdmport.png)

上圖的紫圈$$w^Tw = C$$表示了Regularization給的限制

**所有的解都只能在紫圈的範圍內**

而藍圈則代表錯誤的大小，外圍則越大，中心點為最小值

也就是當$$w = w_{lin}$$時，就是原本所訓練出的權重，所得到$$E_{in}$$也是最小的\(training set\)

> 但在紫圈的限制下，w要如何最佳化呢?

首先，我們還是要求最小的$$E_{in}$$，但是受限於紫圈的關係，因此**可預想最佳的w是在紫圈邊線上**\(靠近藍圈\)

為了盡可能的靠近$$E_{in}$$，即使在邊線上也要朝$$\nabla E_{in}$$的方向前進\(見Linear Reg\)

但為了不超出紫圈，因此將$$\nabla E_{in}$$的向量拆解成兩個：

1. 紫圈的切線\(綠色線\)
2. 法向量\(紅色線\)

**只要順著紫圈的切線前進，便可既降低E\_in，又不會超出Regularization的限制了**

