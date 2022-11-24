# Strategy

### Strategyとは
- 複数のアルゴリズムを個別のクラスとして定義し、切り替えができるようにするパターン
  - 親クラスでクライアントにアクセスさせるための共通APIを定義
  - 子クラスで具体的なアルゴリズムを実装

### クラス図
![クラス図](./%E3%82%AF%E3%83%A9%E3%82%B9%E5%9B%B3.png)

- Context
  - Strategy型のオブジェクトを内部に保持
  - 具体的な処理はStrategyオブジェクトに移譲

### オブジェクト指向的要素
- 継承、ポリモーフィズム、移譲を利用したパターン
  - StrategyとConcreteStrategyは継承関係
  - Strategyクラスで共通のAPIを定義し、クライアントはその共通APIを利用することで、具体的なクラスの切り替えが可能になる
  - ContextクラスはStrategyオブジェクトに処理を移譲する

### メリデメ
- メリット
  - 実行時にオブジェクト内で使用されるアルゴリズムを交換できる
  - アルゴリズムの実装の詳細を利用側のコードから分離できる
  - アルゴリズムの追加が容易になる
- デメリット
  - アルゴリズム数が少ない場合、過剰になる

### 使い所
- ある問題を解決するための方法が複数あり、プログラム実行時に動的に切り替えたい場合
  - Contextに渡すConcreteStrategyによってアルゴリズムが切り替わる
- クラス内にアルゴリズムを切り替えるためのに多くの条件文がある場合
  - 条件分岐を共通なAPIを持った個別のConcreteStrategyクラスに切り出している