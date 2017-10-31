## 概要
* JavaScript上、唯一のオブジェクト。
* インスタンス化などはできない。
* 参照するときは`Global.～`とは書かずに、これでOK
    ```
    変数名
    関数名(引数...)
    ```

## Numberオブジェクトへ移動したメソッド
* isFinite
    * 有限ですか？（Infinityではないよね？）
* isnaN
    * 数値ですか？
* parseFloat
* parseInt

## URI関数
* encodeURI
* decodeURI
* encodeURIComponent
* decodeURIComponent

～Componentとの違いはエンコード対象の文字列。  
とはいえ、やってることは大体同じ。

## eval関数
あまり好ましく思われないこいつ。
* 文字列をコードとして実行する。
