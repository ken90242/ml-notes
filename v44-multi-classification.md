# Multi-classification

![](/assets/idsofj983jf934jf432ft.png)

直覺的辦法即為一次針對一個類別去劃出decision boundary，然後得到4個分類器

> 但要怎麼尚未清楚分類的灰色地帶要怎麼辦呢\(下圖圈起處\)

![](/assets/jfoewjfiew32u849r2h3rf2foort.png)

因此改為softly的分類\(logistic regression\)

![](/assets/jfewifjo3298f9321hr213hf.png)

![](/assets/jfiojsifj2398fj43ft.png)

**用不同的分類器來計算資料在各個類別的機率，最後再挑選最大者分類。\(因為只是比大小，因此**$$\theta$$**函式並非必要\)**

