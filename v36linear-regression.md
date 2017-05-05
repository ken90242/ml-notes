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

