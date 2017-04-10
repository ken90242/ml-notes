# 選擇到的只是假象

> 偶然間的必然性：丟150次硬幣，出現連續5次人頭的機率&gt;99%

Hoeffding's Inequality所保證的是$$E_{in} \approx E_{out}$$，其不相等的機率是相對較小的

然而不相等的情形是一定會發生的，就像下圖一樣

![](/assets/nfd432734hgimport.png)

BAD出現的機率是相對小的。\(這邊的BAD指的是會讓$$E_{in}跟E_{out}$$相差很大的資料\)

![](/assets/im398hy4gfh34port.png)

Hoeffding保證的只是BAD資料出現機率較小

# BAD data?

便是會讓演算法踩到雷，誤因其$$E{in}$$很小而選擇很大的$$E{out}$$

### 當出現多個hypothesis時

![](/assets/iy7f32fuhmport.png)

每個紅色的BAD都是一塊地雷，而當hypothesis選到該資料時便會發生$$E_{in}很小但E_{out}很大$$的情況

最慘的情況便是最後選擇了踩到地雷的hypothesis

要嘛選擇$$D_1$$然後輸出$$h_1$$、或是選擇$$D_2$$輸出$$h_3$$、選擇$$D_{5678}$$輸出$$h_M$$、...

**因此只要含有BAD的資料一律不能用**

### Bad data的範圍上限

> 每個hypothesis的Hoeffding**聯集**

如下圖所示\(假設有M個hypothesis\)

![](/assets/ihf87324fr2mport.png)

#### **因此可以推得**$$\mathbb{P} \leq 2M exp(-2\epsilon^2N)$$

#### **當N大到一定程度時，不論選擇什麼hypothesis，皆可保證**$$E_{in} \approx E_{out}$$

#### 

![](/assets/impo8943hfh123rt.png)

