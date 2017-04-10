# 為什麼要用Pocket algorithm?

> 當有Noisy data或是不清楚是否Linear separable時，使用貪心法則Pocket algorithm:每次都保持口袋最滿的狀態

![](/assets/43jfigfhjsogfdgimport.png)

第一步：隨便找一個點然後修正$$W_t$$_為_$$W_{t+1}$$

第二步：若是$$W_{t+1}$$犯的錯比$$\hat{W}$$少\(所有錯誤的分類數量$$\rightarrow$$代表要全部跑過一次\)，則指定$$\hat{W}$$為$$W_{t+1}$$

若沒有則使$$\hat{W}$$保持原樣



### 若有一線性可解問題，同時使用pocket algo和perceptron，差異?

皆可找到最佳解，然而pocket algorithm每次都需要再檢視全部的點，因此會跑的較慢

