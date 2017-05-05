# Linear Reg可以用來做Binary分類嗎?

![](/assets/j098f9whf9ewf.png)

相比於linear classification，linear regression顯得有效率多了

那麼我們能先利用linear regression先行求出一個數字，再利用一個界線來定義其分類嗎?



![](/assets/h98732hd98h32d98.png)

從上圖中可以看出，所有linear classification的錯誤一定都比linear regression小\(因為在lin reg最佳解上也代表分類分對，誤差也為0\)

![](/assets/230jr923jre032jr09t.png)

也因為這個特性，我們可以利用upper bound的性質將限縮在regression的誤差內

也就是用上限交換了效能

而這個求得的w是一個很有用的初始權重，可用在initial PLA vector

