# 一、M的重要性

![](/assets/m74hfwh982port.png)

當M越小\(hypothesis的數量\)，其選到壞資料的機率就越小，然而選擇卻很少\($$E_{in}(g)\ small?$$\)

當M越大，其選擇變多，然而選到壞資料的機率卻增加了$$E_{out}(g)\ \ v.s.\ \ E_{in}(g)$$

M無論變大變小，都有其優缺點。

> 我們無法保證光是將M調到最大或最小
>
> **便可降低選到壞資料的機率、並讓訓練後的精準度是準的。**

# 二、剛剛好的M

因此M的大小不可太大、太小，因此如何取到剛好的M便是一門學問

hypothesis的數量將近無限多種，首先在避免選到壞資料便是個大問題

複習一下M是如何得出的:

$$\mathbb{P}[\beta_1\
 or\ \beta_2\ or\ \beta_3\ or\ ...\ or\ \beta_M]\ 
\ \leq\ \ \mathbb{P}[\beta_1]+\mathbb{P}[\beta_2]+\mathbb{P}[\beta_3]+...+\mathbb{P}[\beta_{M}]$$

而最壞的情況就是每個$$\mathbb{P}[\beta_x](x=1...M)$$ 都沒有交集

但正常情況下，$$\mathbb{P}[\beta_x](x=1...M)$$或多或少都會有所交集，如下圖所示

![](/assets/impj843hf2ort.png)

三、

