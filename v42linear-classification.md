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



