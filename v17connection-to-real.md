# 選擇到的只是假象

> 偶然間的必然性：丟150次硬幣，出現連續5次人頭的機率&gt;99%

Hoeffding's Inequality所保證的是$$E_{in} \approx E_{out}$$，其不相等的機率是相對較小的

然而不相等的情形是一定會發生的，就像下圖一樣

![](/assets/nfd432734hgimport.png)

BAD出現的機率是相對小的。\(這邊的BAD指的是會讓$$E_{in}跟E_{out}$$相差很大的資料\)

![](/assets/im398hy4gfh34port.png)

Hoeffding保證的只是BAD資料出現機率較小

### BAD data?

指的便是會讓演算法踩到雷$$$$，誤因其$$E_{in}_$$很小而選擇很大的$$_E_{out}$$

### 當出現多個hypothesis時

![](/assets/iy7f32fuhmport.png)

可以將其想像為

