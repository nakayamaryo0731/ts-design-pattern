# Decorator

### Decoratorとは
- 基本となりオブジェクトに対して、柔軟に機能を追加するパターン
  - 継承よりも柔軟で、動的に機能追加が可能
  - 基本のオブジェクトを包むように見えるので、Wrapperパターンと呼ばれることもある。

### クラス図
![クラス図](./%E3%82%AF%E3%83%A9%E3%82%B9%E5%9B%B3.png)

- Component
  - 抽象クラス or インターフェース
  - 拡張される基本機能のAPIを定義
- ConcreteComponent
  - Componentを継承する小クラス
  - 基本機能の具体的な実装を行う
- Decorator
  - Componentを継承し、基本機能の拡張を行う抽象クラス
  - 内部にCOmponentのオブジェクトを保持
  - ComponentのAPI定義の実装は小クラスに任せる
- ConcreteDecorator
  - Decoratorを継承する小クラス
  - Componentの基本機能に具体的な拡張を行う

### オブジェクト指向的要素
- 継承、ポリモーフィズムを利用したパターン
  - ComponentとConcreteComponent、ComponentとDecorator、DecoratorとConcreteDecoratorが継承関係
  - 機能を「追加される側」のComponentと、「追加する側」のDecoratorが同じAPIを持っており、利用者はどちらかを操作しているかを意識する必要がない。

### メリデメ
- メリット
  - 実行時の機能追加が容易にできる
  - 複数の機能を組み合わせることが可能
- デメリット
  - 組み合わせた機能から特定の機能の削除は困難
  - 振る舞いがDecoratorの組み合わせ順序に依存する

### 使い所
- 追加したい機能のパターンが複数ある場合
- 追加したい機能のパターンに順序がある場合
- 継承を使ってオブジェクトの機能拡張が困難な場合