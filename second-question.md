# 證明PLA在線性可分是會停止的

Assume linear separable D, does PLA always halt?

D = exists perfect $$W_f$$ such that $$y_n=Sign(W^T_fX_n)$$

### 1.停止代表最終找到的$$W_{t+1} 趨近於 W_f$$

> #### 那如何判定向量間是否接近? 由兩者的內積大小來判定

$$W^T_fW_{t+1} = W_f^T(W_t+y_{n(t)}x_{n(t)})$$

$$=W_f^TW_t+W_f^Ty_{n(t)}x_{n(t)}$$

$$\geq W_f^TW_t+min_n(y_nW_f^Tx_n)$$

$$> W_f^TW_t+0$$

$$\therefore W_{t}$$ 在每次更新後$$(W_{t+1})$$的向量變大，更趨近於$$W_f$$

#### 但內積大小由長度及角度\($$cos\theta$$\)共同決定，因此有可能只是長度變長而已

### 2.向量成長的速度限

$$Sign(W_t^Tx_{n(t)}) \neq y_{n(t)} \Longleftrightarrow y_{n(t)}W_t^Tx_{n(t)} \leq 0$$

> 上面的意思為向量僅在犯錯時$$y_{n(t)}W_t^Tx_{n(t)} \leq 0$$更新

$$\|W_{t+1}\|^2 = \|W_t+y_{n(t)}x_{n(t)}\|^2$$

$$=\|W_t\|^2+2y_{n(t)}W_t^Tx_{n(t)}+\|y_{n(t)}x_{n(t)}\|^2$$

$$\leq \|W_t\|^2+0+\|y_{n(t)}x_{n(t)}\|^2$$

$$\leq \|W_T\|^2+MAX_n\|y_nx_n\|^2$$

$$\leq \|W_t\|^2+MAX_n\|\pm1 \times x_n\|^2$$

$$\therefore $$  Mistake limit $$\|W_t\|^2$$ growth, even when updating with longest $$x_n$$$$\Rightarrow$$ 長度慢慢地成長

從上述兩項可得到綜合結論

1. $$W_f^TW_t < W_f^TW_{t+1}$$
2. $$\|W_{t+1}\|^2 \leq \|W_t\|^2 + MAX_n\|x_n\|^2$$

**向量更新後會更貼近彼此\(向量變大\)，又因**$$W_{t+1}$$**長度成長有限，代表角度明顯變小**

