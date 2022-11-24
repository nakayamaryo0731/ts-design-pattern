# State

### Stateとは
- 複数の状態を別個のクラスとして定義し、状態が変化したときに振る舞いを切り替えられるようにするパターン

### クラス図
![クラス図](./%E3%82%AF%E3%83%A9%E3%82%B9%E5%9B%B3.png)

- ConcreteState
  - インターフェース or 抽象クラス
  - Stateで定義された共通APIを満たすように各状態ごとの振る舞いを実装
- State
  - State型のオブジェクトを内部に保持
  - 具体的な処理はStateオブジェクトに移譲

### オブジェクト指向的要素
- 継承、ポリモーフィズム、移譲を利用したパターン
  - StateとConcreteStateは継承関係
  - Stateクラスで共通のAPIを定義し、クライアントはその共通APIを利用することで、具体的な状態クラスの切り替えが可能になる
  - ContextクラスはStateオブジェクトに処理を移譲する

### メリデメ
- メリット
  - 特定の状態における実装の詳細を別クラスに分離できる
  - 状態に固有の処理を選択するための条件文がなくなる
  - 状態の追加が容易になる
- デメリット
  - 過剰な設計になる可能性がある

### 使い所
- 現在の状態に応じて異なる振る舞いをするオブジェクトがあり、その状態数が多い場合
  - Contextに現在の状態をセットすることで振る舞いが切り替わる
- 状態の内容が頻繁に変更される場合
- 状態に固有の処理を実行させるために多くの条件分岐がある場合
  - 条件分岐を共通なAPIを持った個別のConcreteStateクラスに切り出している