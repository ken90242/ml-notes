# 證明PLA在線性可分是會停止的

Assume linear separable D, does PLA always halt?

D = exists perfect $$W_f$$ such that $$y_n=Sign(W^T_fX_n)$$

### 1.停止代表最終找到的$$W_{t+1} 趨近於 W_f$$

> #### 那如何判定向量間是否接近? 由兩者的內積大小來判定

$$W_fW_{t+1} = W_f^T(W_t+y_{n(t)}x_{n(t)})$$

$$=W_f^TW_t+W_f^Ty_{n(t)}x_{n(t)}$$

$$\geq W_f^TW_t+min_n(y_nW_f^Tx_n)$$

$$> W_f^TW_t+0$$

$$\therefore W_{t}$$ 在每次更新後$$(W_{t+1})$$更趨近於$$W_f$$

但內積大小也代表著

