## ノードの取得
- Get系
    - `getElementById(id)`：idから取得  
複数ＩＤがある事は想定されていないので、挙動の保証はない。  
必ず同じＩＤは１つにすること。
    - `getElementsByTagName(name)`：タグ名から取得
        - 複数が想定されている
        - 例：`document.getElementByTagName('a')`
    - `getElementsByName(name)`：name属性から取得
        - 複数が想定
    - `getElementsByClassName(clazz)`：class名から取得
- query系（selectorから取得）
    - `querySelector(selector)`：selector式から１つ取得
    - `querySelectorAll(selector)`：selector式から複数取得

Selector一覧

- 元々はCSSで使われていたものを逆輸入した。

|Selector|概要|例|
|:-|:-|:-|
|* |全て |*|
|#id|指定したIDから取得 |#main|
|.class |指定したクラス名から取得 |.external|
|elem |指定したタグ名から取得 |li |
|[attr] |指定した属性を持つ要素を取得 |[type] |
|[attr=value] |指定した属性を持つ要素がvalueに等しいとき |[type='button'] |
|[attr^=value]|指定した属性を持つ要素がvalueから始まる |[href^='https://'] |
|[attr$=value]|指定した属性を持つ要素がvalueで終わる|[src$='.jpg']|
|[attr*=value]|指定した属性を持つ要素がvalueを含む|[title*='sample']|
|selector1, selector2, ... |or条件の合致で取得 |#main, li |
|[selector1][selector2][...] |and条件の合致で取得 |[src][alt] |
|parent_selector > child_selecotr |parent要素の子要素childを取得 |#main > .external |
|ancestor descendant |ancestor要素の小孫要素descendantをすべて |#list li |
|prev + next|prev要素の直後のnext要素 |#main+div |
|prev ~ siblings|prev要素移行のsiblings兄弟要素を取得|#main~div |


※ちなみに、getXxxメソッドとQueryXxxxメソッドはgetの方がパフォーマンスは激速

## ノードウォーキング

上の要素を取得した後、そこから親要素、兄弟要素、子要素などで別の要素を指定できる。

- 子要素
    - 全て：`document.getElementById('#main').childNodes`
    - はじめ：`document.getElementById('#main').firstChild`
    - 次のノード：`document.getElementById('#main').nextSibling`


## イベントドリブンモデル
- 処理内容を定義するコードの塊：イベントハンドラー、イベントリスナー
