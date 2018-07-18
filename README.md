# Grid Layout

Grid Layoutは、Boxesとsizingと配置を制御するCSSの新しいレイアウトモデルです。

[CSS Grid Layout Module Level 1](https://www.w3.org/TR/2017/CR-css-grid-1-20171214/)

下の図は典型的なflex-layout  
![flex-layout](images/flex-layout.png)

次の図はgrid-layout  
![grid-layout](images/grid-layout.png)

[使用可能なブラウザ](https://caniuse.com/#feat=css-grid)

## 用語

まず覚えること。
1. コンテナ：グリッド全体を囲む要素
2. アイテム：コンテナの直接の子要素
3. ライン：グリッドを作る線
4. トラック：行と列のこと。行トラック、列トラック
5. セル：アイテムを配置する枠
6. エリア：アイテムを配置する枠

## 使い方

サンプルのCSSコード参考
全体のグリッドのサイズはコンテナ（親要素）に記述する。
1. コンテナに対してここにグリッドを作ると宣言する。  
具体的には、`display: grid;`とするだけ。
2. コンテナに対して、トラックのサイズを決める。トラックをどのようにするか決めるプロパティが次の2つになる。  
  * grid-template-rows: 行のトラックの高さを半角スペースで区切って指定
  * grid-template-columns: 列のトラックの幅を半角スペースで区切って指定
  * グリッドには、柔軟なグリッドトラックを作成できるようにするため、追加の長さの単位が導入されています。  
  新しい fr 単位は、グリッドコンテナー内の利用可能な空間の分数 (a fraction) を表します。
  
fr単位のみで指定した場合、fr単位で指定された比率で分割されます。また、px単位と併用された場合はpx単位で固定配分され、残りをfr単位で分割します。

### repeat() 記法によるトラック列挙
多くのトラックを持つ大きなグリッドは、repeat() 記法を使用して、すべてまたは一部のトラックのセクションを繰り返すことができます。

例 

```
grid-template-columns: 1fr 1fr 1fr;
```

repeat()記法を使うと以下のようになります。

```
grid-template-columns: repeat(3, 1fr);
```

次のような記述もOKです。

```
grid-template-columns: 20px repeat(6, 1fr) 20px;
```

これで枠組みができるので、あとはそれぞれのアイテムをどこの枠に落とし込むかを決めていく。
この設定はそれぞれのアイテム（直接の子要素）に対して行う。

* grid-row: アイテムが占める行のラインの番号をスラッシュ区切りで指定する
* grid-column: アイテムが占める列のラインの番号をスラッシュ区切りで指定する


![glid](images/glid.png)
