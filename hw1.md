code:

```
//將資料導入
importData('./hw1_18_train.dat', trainDatas, trainFlags);
importData('./hw1_18_test.dat', testDatas, testFlags);
```



    function main() {
      const startTime = Date.now();
      let wRace = [0, 0, 0, 0, 0];
      wRace = wRace.map(() => { 
        const rand = Math.random();
        const plusOrMinus = rand < 0.5 ? -1 : 1;
        return rand * plusOrMinus;
      });
      let wOpt = wRace;
      let wOptError = countErrors(trainDatas, trainFlags, wOpt);

      let updateLimit = 50;
      let loopTimes = 2000;
      let errorRes = 0;

      for(let i = 0; i < loopTimes; i += 1) {
        do {
          const rand = getRandomArbitrary(0, trainDatas.length)
          const x = trainDatas[rand];
          const y = trainFlags[rand];
          if (!predictIsSame(x, y, wRace)) {
            wRace = updateFeature(x, y, wRace);
            const newError = countErrors(trainDatas, trainFlags, wRace);
            if(newError < wOptError) {
              wOptError = newError;
              wOpt = wRace;
            }
            updateLimit -= 1
          }
          errorRes += testErrors(testDatas, testFlags, wOpt);
        } while(updateLimit > 0);
        // console.log(errorRes);
        errorRes += wOptError;
      }
      console.log(`Optimized Error Rate:${errorRes / (loopTimes * testDatas.length)}`);
      console.log(`total cost:${Date.now() - startTime}`);
    }

    function testErrors(datas, flags, w) {
      let errs = 0;
      datas.forEach((data, idx) => {
        const x = data;
        const y = flags[idx];
        if(!predictIsSame(x, y, w)) {
          errs += 1;
        }
      });
      return errs;
    }

    function getRandomArbitrary(min, max) {
      return Math.floor(Math.random() * (max - min)) + min;
    }




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
//計算每個w的錯誤
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
//計算hypothesis(x)與y是否相同
function predictIsSame(x, y, w) {
  function SIGN(val) {
    return val === 0 ? -1 : (val > 0) ? 1 : -1; 
  }
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

  return y.toString() === SIGN(MUL(x,w)).toString();
}
```





