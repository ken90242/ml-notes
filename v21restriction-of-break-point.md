Growth function $$m_H(N)$$:最多可能的解的數量

# Break point的含義

> 露出曙光的開始：從這個數量後\(k\)，$$m_H(N)$$開始小於$$2^N$$

![](/assets/螢幕快照 2017-04-25 下午3.51.19.png)

break point為2，代表兩個點無法表示所有的可能解：ＯＯ、XO、XX、OX，之後三個點也無法表示所有的解了

**因為positive rays只會將一條線上切成左邊為負右邊為正，因此不會出現OX的解**

![](/assets/螢幕快照 2017-04-25 下午3.54.43.png)

**positive interval只會將一條線選取一個範圍，分類該範圍的所有點為正，因此不會出現OXO的解**

![](/assets/螢幕快照 2017-04-25 下午3.56.11.png)

**covex sets由於可以做到所有的可能解，因此沒有break point，其**$$m_H(N)=2^N$$

![](/assets/螢幕快照 2017-04-25 下午3.57.41.png)

**2D perceptrons在無法區分出此種解，由於對稱關係\(OX互換\)，其最大可能解也只有**$$2^4-2=16-2=14$$**種**

# 所以呢？

> What "must be true" when minimum break point = 2?

![](/assets/螢幕快照 2017-04-25 下午4.01.22.png)

break point=2代表：一個點可以做到所有的可能解、但是兩個點就不行了，因此兩個點的最大可能解頂多為3



