## 概要
* 全てのオブジェクトのひな型
* Javaでもあるあれと同じようなイメージ

## 主なメソッド
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
`Object.assign(target, source, ...) // source：コピー元`
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
var merged =  Object.assign(pet, pet2, pet3);
// pet1にも影響が及ぶ。
// 及ぼさないようにするには下記。
// let merged = Object.assign({}, pet, pet2, pet3)
// 再起マージは非対応なので、descriptioniは{food: 'ジャーキー'}のみが残る
```

* create
    * オブジェクトの生成。  
`Object.create(proto [, props]) // protoは元となるオブジェクト`
```
var object= Object.create(Object.prototype, {
    x: {value: 1. writable: true, configurable: true, enumerable: true}
    , y: {value: 1. writable: true, configurable: true, enumerable: true}
}
```

|属性|概要|デフォルト値|
| :- | :- | :- |
|configurable | 属性の変更やプロパティの削除が可能か | false |
|enumerable | 列挙を可能とするか | false |
|value | 値 ||
|writable | 書き換え可能か | false |
|get,set |ゲッターセッター関数 ||

## オブジェクトの不変を設定（privateとかそんなイメージ）

|メソッド| プロパティ追加 | プロパティ削除 | プロパティ値変更 |
|:- | :-: | :-: | :-: |
|preventExtensions|×|〇|〇|
|seal|×|×|〇|
|freeze|×|×|×|

```
'use strict';
var pet = {type: 'ダックスフンド', name: 'アレン'}
// Object.preventExtensions(pet);
// Object.seal(pet);
// Object.freeze(pet);
pet.name = 'クリリン'; //変更系
delete pet.type; //削除系
pet.weight = 24; //追加系
```
