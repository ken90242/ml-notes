### 當k&gt;N時呢？

![](/assets/螢幕快照 2017-04-25 下午4.52.16.png)

我們可以用肉眼看出$$B(N,k) = B(N-1,k) + B(N-1,k-1)$$

也因此現在的問題在於如何證明這樣的關係

![](/assets/螢幕快照 2017-04-25 下午4.55.42.png)

### 以B\(4,3\) = 11為例

![](/assets/螢幕快照 2017-04-25 下午4.56.34.png)

將所有的可能解分成橘色的成雙解及紫色的單獨解\(單看$$x_1 \sim x_3$$\)

# 將橙色的解跟紫色的解\($$x_1 \sim x_3$$\)區分開來看

> 我們要藉此推導出在Bounding Function中，N=4與N=3的關係

![](/assets/螢幕快照 2017-04-25 下午5.01.04.png)

更進一步看，橙色與紫色的可能解被區分為$$2\alpha與\beta = (\alpha + \beta)+(\alpha)$$

### $$\alpha + \beta$$

### ![](/assets/螢幕快照 2017-04-25 下午5.00.53.png)

由於$$\alpha+\beta$$畢竟是從B\(4,3\)分割出來的三個點的版本，因此也會符合break point=3的限制

**不然將**$$x_4$$**加回去後就違反了break point=3了！**

也因此$$\alpha+\beta$$的Bounding Function便為B\(3,3\)了

### $$\alpha$$

### ![](/assets/螢幕快照 2017-04-25 下午5.08.20.png)

對$$\alpha$$來說，其break point為2，為什麼？

因為$$\alpha$$也是由B\(4,3\)分出來的三個點的版本，若是$$\alpha$$的break point=3，意味著其任意兩點可以滿足所有的可能解

若是再把$$\alpha$$加上$$x_4$$的兩種可能後，代表共有3個點可以滿足所有的可能解

原本的B\(4,3\)便會違反break point=3的規則

因此$$\alpha$$的Bounding Function即為B\(3,2\)

### B\(4,3\) & B\(3,?\)

B\(4,3\) = $$(2\alpha+\beta)=(\alpha+\beta)+(\alpha)$$的Bounding Function為B\(3,3\) + B\(3,2\)

得B\(4,3\) $$\leq$$ B\(3,3\)+B\(3,2\)，$$B(N,k) \leq B(N-1,k)+B(N-1,k-1)$$得證

# 所以我說當k&gt;N時呢？

![](/assets/螢幕快照 2017-04-25 下午5.17.51.png)

藉由剛剛推導的公式B\(N,k\) = B\(N-1,k\)+B\(N-1,k-1\)，可以將剩餘的表填上

# $$B(N,k) \leq \sum^{k-1}_{i=0} \lgroup^N_i \rgroup$$

# ![](/assets/螢幕快照 2017-04-25 下午5.24.05.png)

在固定break point=k的情況下，B\(N,k\)的上限為Polynomial function，因此$$m_H(N) = poly(N)$$，當break point存在時。

$$N(m_{h}(N), B(N,k))$$

![](/assets/螢幕快照 2017-04-25 下午5.25.47.png)

