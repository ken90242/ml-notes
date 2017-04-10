# 證明PLA在線性可分是會停止的

Assume linear separable D, does PLA always halt?

D = exists perfect $$W_f$$ such that $$y_n=Sign(W^T_fX_n)$$

### 1.停止代表最終找到的$$W_{T+1} 等於目標 W_f$$

$$W_fW_{t+1} = W_f^T(W_t+y_{n(t)}x_{n(t)})$$

$$=W_f^TW_t+W_f^Ty_{n(t)}x_{n(t)}$$

$$\geq W_f^TW_t+min_n(y_nW_f^Tx_n)$$

$$> W_f^TW_t+0$$

$$W_t$$

