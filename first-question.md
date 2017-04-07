# Perceptron

> 漸進式修正假設來得到最佳解

### 例子

資料如下圖分布，而需要找出一個hypothesis\(w\)將其分割成兩塊

![](/assets/img/example_perceptron_initial_map.png)

#### 修正模型

* 情境一：實際為正，預測為負

![](/assets/asdsa32import.png)

由於$$w \bullet x 為負的(不是正的)，代表其  cos\theta 過大，需要降低彼此間的角度$$ w\bulletx為負

解決辦法即

* 情境二：實際為負，預測為正

![](/assets/wehif4fimport.png)

