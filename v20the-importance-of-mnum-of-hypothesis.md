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

除此之外，以Perceptron為例，hypothesis有無數個\(無數條線\)，而有些線只要微調就是另一個hypothesis

![](/assets/impjr982fnhwiueort.png)

1. hypothesis1與hypothesis2對於test set的預估是相近的
2. 在絕大部分情形，hypothesis1與hypothesis2對於training set的結果是相同的

因此這會造成union bound過分高估。$$\because$$ 過多重疊且造成無限多的hypothesis

# 三、如何處理M高度重疊

> **換一個角度:由資料的視角出發**
>
> **我只在乎你是不是好人，不在乎你有多好、在哪裡做了什麼好事**

![](/assets/impojf982h9f2rt.png)

在平面上，用於分類$$x_1$$是O還是X可以說是無限多條的線。

然而若以$$x_1$$的角度出發，對它來說，真正重要的只是這條線會將它分成哪一類

![](/assets/ijr23j0f9port.png)

再多條線，真正重要的是它究竟會被分成哪類?

所以對$$x_1$$而言，只有兩條線：**把它分成O和分成X的**，如下圖所示

![](/assets/im8j432f9hport.png)

### 若是兩個點呢?

![](/assets/impj8293fj2ort.png)

對$$x_1跟x_2$$來說，只有4條線可將其分成4種結果

到這邊我們大概可以發現，對這種二元分類的資料來說，線只有$$2^N(N=num\ of\ data)$$個結果$$(2^N種可能性)$$

### 若是三個點呢?

![](/assets/impoj8329fwrt.png)

總有些事無法做到的hypothesis，在此例中，3個點有$$2^3=8$$種可能，這代表其應有8個hypothesis

然而有兩個分類是無法做到的，因此三個點中只有6種hypothesis的可能

### 小結

$$\mathbb{P}[\|E_{in}(g)-E_{out}(g)\|>\epsilon]\ \leq\ 2\bullet effective(N)\bullet exp(-epsilon^2N)$$

從上述例子中，我們發現M不再是遙不可及的範圍，而是一個可以去縮小運用的範圍

以二元分類為例，$$effective(N)\leq 2^N$$

![](/assets/imnf892hf32port.png)

因此，若是effective\(N\)可以取代M，且$$effective(N)\ll 2^N$$，在無限的hypothesis下學習便是一件可行的事



