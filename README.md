# ts-design-pattern
### これはなに
typescriptでSOLID原則やデザインパターンを勉強するリポジトリ

### SOLID原則とは
S: Single Responsibility Principle: 単一責任の原則
O: Open Closed Principle: オープンクローズドの原則
L: Liskov Substitution Principle: リスコフの置換原則
I: Interface Segregation Principle: インターフェース分離の原則
D: Dependency Inversion Principle: 依存性逆転の原則

- ソフトウェア構築時に従うべきガイドライン
- オブジェクト指向プログラミングにおいて
  - 変更しやすい
  - 理解しやすい
  - 再利用しやすい

なモジュールを設計/開発するための5つの原則

#### S: Single Responsibility Principle: 単一責任の原則
クラスはたった一つのアクターに対して責務を負うべきである。
違反すると、あるアクターのために行った変更の影響が別のアクターにも及び、バグの原因となる可能性がある。

#### O: Open Closed Principle: オープンクローズドの原則
ソフトウェアの構成要素は拡張に対して開かれていて、修正に対して閉じていなければならない。
違反すると、if分岐が増えコードが複雑になり、バグの原因となる可能性がある。

#### L: Liskov Substitution Principle: リスコフの置換原則
サブタイプはそのスーパータイプと置換可能でなければならない。
正しい継承 = 「is-a関係」+「振る舞いの同等性」

#### I: Interface Segregation Principle: インターフェース分離の原則
インターフェースのクライアントにとって利用しないフィールドやメソッドへの依存を強制してはならない。

#### D: Dependency Inversion Principle: 依存性逆転の原則
a. 上位のモジュールは下位のモジュールに依存してはならない。どちらもモジュールの「抽象」に依存すべき。
b. 「抽象」は実装の詳細に依存してはならない。実装の詳細が「抽象」に依存すべきである。

Dependency Injectionとは
クラス間の依存関係をソースコードから排除するために、コンストラクタやセッターメソッドを通じて外部からオブジェクトを渡せるようにするパターン