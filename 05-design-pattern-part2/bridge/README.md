# Bridge

### Bridgeとは
- 機能を提供するクラスと、実装を提供するクラスを独立させるためのパターン
  - 目的と手段を分離する
  - 移譲を使うことで、機能と実装の橋渡しをしているように見える

### クラス図
![クラス図](./%E3%82%AF%E3%83%A9%E3%82%B9%E5%9B%B3.png)

- Abstraction
  - 基本機能を提供するクラス
  - 内部に実装を行うオブジェクトを保持しており、具体的な処理はそのオブジェクトに移譲
- RefinedAbstraction
  - Abstractionを継承する小クラス
  - 基本機能の拡張や別の機能を追加
- Implementor
  - 実装を提供するインターフェースもしくは抽象クラス
  - 機能を実現するためのAPIを定義
  - AbstractionのAPIと一致している必要はない
- ConcreteImplementor
  - Implementorを実装する子クラス
  - 機能の具体的な実装を行う

### オブジェクト指向的要素
- 継承、ポリモーフィズム、移譲を利用したパターン
  - Abstractionのフィールドを抽象であるImplementoとすることで、具体的な実装を意識する必要がなくなる
  - 機能を提供するクラスの具体的な処理は、実装を提供するクラスに移譲される。

### メリデメ
- メリット
  - 機能の拡張と実装の修正が容易になる
  - プログラムの実行時に実装を切り替えられる
  - 機能や実装のバリエーションが豊富な場合、最終的に作成すべきクラス数を抑えることができる。
- デメリット
  - 機能や実装にバリエーションが少ない場合、余計にクラス数が増え、コードが複雑になる可能性がある。

### 使い所
- 機能と実装の組み合わせが多い場合
  - 継承のみで実現する場合、組み合わせ分のクラスを作成する必要がある
  - Bridgeパターンでは、親クラス(2)+機能数+実装数のクラスを作成する。