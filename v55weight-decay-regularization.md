---

  $$\min_{w\in{R}}$$$$E_{in}(w) = \frac{1}{N}\sum_{n=1}^N(w^Tz_n - y_n)^2= \frac{1}{N}\sum^N_{n=1}(Zw-Y)^T(Zw-Y)$$

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

**只要順著紫圈的切線前進，便可既降低$$E_{in}$$，又不會超出Regularization的限制了**

### 那麼，要如何用數學式表示運算到最後的最佳解呢?
前進到最後，會發現再也沒有切線可以前進了

這時的$$w$$，是跟 $$\nabla E_{in}$$ 平行的
$$-\nabla E_{in}(w_{REG}) \propto w_{REG}$$

為了推導方便：$$\nabla E_{in}(w_{REG}) + \frac{2\lambda}{N} w_{REG} = 0$$, $$s.t. \lambda >=0$$

---

**解法一**

$$\nabla E_{in}(w_{REG}) + \frac{2\lambda}{N} w_{REG} = 0$$

$$\Rightarrow\frac{2}{N}(Z^TZw_{reg}-Z^Ty) + \frac{2\lambda}{N} w_{REG} = 0$$

$$\Rightarrow w_{REG} \leftarrow (Z^TZ + \lambda I)^{-1}Z^Ty$$

---

**解法二**

求$$\nabla E_{in}(w_{REG}) + \frac{2\lambda}{N} w_{REG} = 0$$ ，可將其視為下式\(Augmented error\)的微分

$$\Rightarrow E_{in}(w) + \frac{\lambda}{N}w^Tw$$

> 最小化Augmented error相當於最小化有條件\(C\)的$$E_{in}$$

---

### 小結

我們將$$\frac{\lambda}{N}w^Tw$$ 這一項視為**Weight-decay regularization**

而從上述推導中可得：

**很大的**$$\lambda$$** = 偏向小的**$$w$$**  = 小的**$$C$$

