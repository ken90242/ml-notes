
---

程式：以Javascript開發

```js
// 將資料導入
import { trainDatas, trainFlags } from 'hw1_18_train.dat';
import { testDatas, testFlags } from 'hw1_18_test.dat';
```

```js
function main() {
  // 隨機初始化x0:Array(5)，並將其指定為目前最好的w、計算產生的錯誤數
  let wRace = randomizeSeeds();
  let wOpt = wRace;
  let wOptError = countErrors(trainDatas, trainFlags, wOpt);
  let loopTimes = 2000;
  // 所有2000次的錯誤數總和
  let errorRes = 0;

  // 為統計，循環測試2000次
  for(let i = 0; i < loopTimes; i += 1) {
    let updateLimit = 50;
    do {
      // 隨機選取一個x及對應的y
      const rand = getRandomNumber(trainDatas.length)
      const x = trainDatas[rand];
      const y = trainFlags[rand];

      if (!predictIsSame(x, y, wRace)) {
        // 若h(x)不等於y，則更新w
        wRace = updateFeature(x, y, wRace);

        // 若是w的錯誤數比現有最好的w的還少，更新最好的w
        const newError = countErrors(trainDatas, trainFlags, wRace);
        if(newError < wOptError) {
          wOptError = newError;
          wOpt = wRace;
        }
        updateLimit -= 1
      }
      errorRes += countErrors(testDatas, testFlags, wOpt);
      // 僅更新50次即進入下一個測試
    } while(updateLimit > 0);
  }
  // 輸出結果
  console.log(`Optimized Error Rate:${errorRes / (loopTimes * testDatas.length)}`);
}
```

```js
//根據上一個w進行更新
function updateFeature(x, y, w) {
  let res_w = [];
  for(let i=0;i<5;i++) {
    const newW =  w[i] + y * x[i] * 0.5;
    res_w.push(newW);
  }
  return res_w;

}
```

```js
// 計算每個w的錯誤
function countErrors(datas, flags, w) {
  let errs = 0
  datas.forEach((data, idx) => {
    const x = data;
    const y = flags[idx];
    if (!predictIsSame(x, y, w)) {
      errs += 1;
    }
  });
  return errs;
}
```

```js
// 判斷hypothesis(x)與y是否相同
function predictIsSame(x, y, w) {
  // 取正負號
  function SIGN(val) {
    return val === 0 ? -1 : (val > 0) ? 1 : -1; 
  }
  // 矩陣相乘
  function MUL(arr1, arr2) {
    if (arr1.length !== arr2.length) {
      throw 'arrays length isnt same!';
    }
    let res = 0;
    for (let i = 0; i < arr1.length; i += 1) {
      res += arr1[i] * arr2[i];
    }
    return res;
  }

  return y === SIGN(MUL(x,w));
}
```



