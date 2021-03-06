# Perceptron

> 漸進式修正假設來得到最佳解

### 例子

資料如下圖分布，而需要找出一個hypothesis\(w\)將其分割成兩塊

![](/assets/example_perceptron_initial_map.png)

#### 修正模型

* 情境一：實際為正，預測為負

![](/assets/asdsa32import.png)

由於 $$w \bullet x$$ 為負的\(不是正的\)，代表其 $$cos\theta$$過大，需要降低彼此間的角度

解決辦法即讓[w再行加上x](http://www.czbaa.com//sites/default/files/field/image/wiki_img/xljf01.png)，降低其$$cos\theta$$

* 情境二：實際為負，預測為正

![](/assets/wehif4fimport.png)

同上，解決辦法為增加$$cos\theta$$，即讓w再行扣掉x，又因y為負數，因此直接加上$$y \times x$$

#### 實際運算

![](/assets/3489gtegimport.png)  
先隨意找一點判斷對錯，因為一開始根本沒有hypothesis，因此直接加上$$x \times y$$作為新的w\(t+1\)

這個w\(t+1\)為法向量[^2]，因此將資料劃分成兩群:

![](/assets/8934ifreimport.png)

第二輪發現$$x_9$$有錯，誤將正的資料歸類在負號區，因此進行調整：$$w(t+1) = w(t) + x\times y$$形成下圖

![](/assets/f3984fgimport.png)

第三輪發現$$x_14$$有錯，誤將負的資料歸類在正號區，因此進行調整：$$w(t+1) = w(t) + x\times y$$形成下圖

![](/assets/3fjwe8hf94import.png)

依此類推，最終找到可正確歸類所有資料的hypothesis

![](/assets/f98h432fimport.png)

#### 證明

$$Sign(W^T_tX_n)\neq y_n, W_t+1 \gets W_t + y_nx_n$$

第二式兩邊同時乘以$$y_nx_n$$得$$y_nx_nW_t+1 \gets y_nx_nW_t + (y_nx_n)^2$$

因此得知$$y_nx_nW_t+1 > y_nx_nW_t$$，此式即代表所做的修正是有用的\(若是$$sign(xw)\neq sign(y)$$表示其乘積為負\)

