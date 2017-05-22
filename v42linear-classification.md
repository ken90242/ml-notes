# Error Function revisited

![](/assets/fchewcwhe9fwe213.png)

> 這邊統一由y,s表示error是為了之後的比較

Linear Regression：$$err_{SQR}(s,y) = (s-y)^2 = \frac{y^2(s-y)^2}{y^2(=1)} = (ys-1)^2$$

### Error Plot

![](/assets/fj3289fj39j2234324fffft.png)

從上圖可得出：

1. **Linear Regression**：小的$$err_{sqr}$$ $$\Rightarrow$$ 小的 $$err_{0/1}$$
2. **Logistic Regression**：小的$$err_{ce}$$ $$\Leftrightarrow$$ 小的 $$err_{0/1}$$

> scaled ce是一個以$$log_2$$為底的error function\(以$$log_{e}$$為底\)

![](/assets/xxmxwoi83894r1.png)

![](/assets/jasodj4309jf3042t.png)

把$$err_{ce}$$乘上$$\frac{1}{ln2}$$後，會得到一條新的錯誤曲線：$$err_{scaled\ ce}$$，這樣做的目的是為了當ys為0時，讓該線通過變化點

：小的$$err_{sce} $$ $$\Leftrightarrow$$  小的$$err_{0/1}$$

### Relationship of different function\(Upper Bound\)

$$err_{0/1} \leq err_{sce} = \frac{1} {ln2}\times 
 err_{ce}$$

$$\Rightarrow E_{in}^{0/1}(w) \leq E_{in}^{SCE}(w) = \frac{1}{ln2}E_{in}^{CE}(w)$$

$$\Rightarrow E_{out}^{0/1}(w) \leq E_{out}^{SCE}(w) = \frac{1}{ln2}E_{out}^{CE}(w)$$

> $$VC$$ on 0/1

$$E_{out}^{0/1}(w) \leq E_{in}^{0/1}(w) + \Omega^{0/1}$$

$$\Rightarrow E_{out}^{0/1}(w) \leq \frac{1}{ln2}E_{in}^{CE}(w) + \Omega^{0/1}$$

> $$VC_{Reg}$$ on CE

$$E_{out}^{0/1}(w) \leq \frac{1}{ln2}E_{out}^{CE}(w)$$

$$\Rightarrow E_{out}^{0/1}(w) \leq \frac{1}{ln2} E_{in}^{CE}(w) + 
 \frac{1}{ln2}\Omega^{CE} $$

**兩種不同的推導都會得到同一個結論：小的**$$E_{in}^{CE}(w) \Rightarrow$$**小的**$$E_{out}^{0/1}(w)$$

> **同樣的推導也適用**$$E_{in}^{SQR}(w)$$**：Linear/Logistic Reg.都可以用來進行Linear classification**

### 比較：Regression for classification

|  | PLA | Linear Regression | Logistic Regression |
| :--- | :--- | :--- | :--- |
| 優 | 快 | 最簡單且最佳化 | 簡單且最佳化 |
| 缺 | 須Linear separable | **當ys取絕對值很大時**：寬鬆的upper bound | **當ys為負且非常小時**：寬鬆的upper bound |

> **Linear Reg.經常用來運初始值**$$w_0$$**，提供給其他algorithm：PLA/Logistic Reg./pocket**

# Stochastic Gradient Descent\(SGD\)

> 每次更新w都要花上O\(N\)的時間，能否改進?

![](/assets/jfew8fjwejfojidsofsdft.png)

拖累$$-\nabla{E_{in}W_t}$$主要是$$\frac{1}{N}\sum^N_{n=1}$$，當將其視為一個\(數個\)隨機點的平均梯度時，便可將時間複雜度限縮在O\(1\)了

![](/assets/jf98ewj9fwjef932234t.png)

Stochastic gradient = true gradient + noise direction

優點：效率高，適用於big data與online learning

缺點：較不穩定\(隨機\)，無法確信到達最低點\(若要確認等於時間白省了\)

### 很像PLA

![](/assets/ifjew98fj23fkpwoefmport.png)

SGD很像soft版本\(可以微調\)的PLA\(說1就是1\)，當$$\eta=1$$且$$w^T_tx_n$$很大時，$$SGD \approx PLA$$



