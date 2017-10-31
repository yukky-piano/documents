## 概要
* 全てのオブジェクトのひな型
* Javaでもあるあれと同じようなイメージ

* toString
    * 文字列を返す
* valueOf
    * 文字列以外の基本型の値が返される
```
var date = new Date();
console.log(date.toString());  // "Tue Oct 31 2017 23:21:15 GMT+0900 (東京 (標準時))"
console.log(date.valueOf());   // 1509459675816
```
* assign(ES2015)
    * オブジェクトをマージする
```
let pet = {
  type: 'ダックスフンド'
  , name: 'アレン'
  , description: {
    birth: '2005-01-01'
  }
};

let pet2 = {
  name: 'クリリン'
  , color: '茶'
  , description: {
    food: 'ジャーキー'
  }
};

let pet3 = {
  weight: 20
}

var pet4 =  Object.assign(pet, pet2, pet3);
// pet1にも影響が及ぶ。
// 再起マージは非対応なので、descriptioniは{food: 'ジャーキー'}のみが残る
```

