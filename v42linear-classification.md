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





