# Regularization

> 解決over-fitting的方法

![](/assets/ij8fw9ef9ewjfwemport.png)

### 概念：**Step Back**

![](/assets/ijf098h8wehfiwqojfmport.png)

over-fitting是因為有著過多或是高維度的feature，因此其解決方法便是將可能多餘的feature給去除

![](/assets/imdijaojd9832hf92h39fh32fpofdsport.png)

但未必僅保留前三項，也可能是將其他feature忽略，只要將feature的數量降到一定程度就行了

**但此為NP-Hard的問題，因此很難去解決**



### Regression with softer constraint

![](/assets/impjfoewjf28f9324jf43iofjewoif98320ort.png)

再更進一步放寬規定，降低feature的數量最根源的目的就是要降低他們的影響力，因此並非一定要將某些feature歸零；

將這些feature的平方和限縮在一定量C以內一樣可以達到一樣的目的。

隨著C大小的不同，其所構建出的hypothesis sets也跟著伸縮，當C為無限大時，就等同沒有reguarization的限制

這樣做的好處為：可以有效的找出**最佳解**

