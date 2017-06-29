* $$\min_{w\in\mathbb{R}}$$$$E_{in}(w) = \frac{1}{N}\sum_{n=1}^N(w^Tz_n - y_n)^2= \frac{1}{N}\sum^N_{n=1}(Zw-Y)^T(Zw-Y)$$

* $$s.t. \sum^Q_{q=0}w_q^2<C$$

上述兩點即表示了前述Regularization的限制及原本Error求最小的兩式

![](/assets/iasdjasoidjosajdoasdmport.png)

上圖的紅圈$$w^Tw = C$$表示了Regularization給的限制

**所有的解都只能在紅圈的範圍內**

而藍圈則代表錯誤的大小，外圍則越大，中心點為最小值

也就是當$$w = w_{lin}$$

