# Interpreter

### Interpreterとは
- 構造の解析を行って、その結果を利用して処理を行うパターン
  - 解析を行うための規則をクラスとして表現
  - 規則のツリー構造を扱うことができる
    - 構文木

### クラス図
![クラス図](./%E3%82%AF%E3%83%A9%E3%82%B9%E5%9B%B3.png)

- Context
  - 解析を行いたい値や情報を提供するクラス
- AbstractExpression
  - 規則を表す抽象クラス or インターフェース
  - 規則が解析を行うための共通APIを定義
- NonterminalExpression
  - AbstractExpressionを継承する子クラス
  - 具体的な規則を実装
  - 内部にAbstractExpression型のオブジェクトを保持することで、規則の親子関係を表現
- TerminalExpression
  - AbstractExpressionを継承する子クラス
  - 具体的な規則を実装
  - 末端の規則を表す

### オブジェクト指向的要素
- ポリモーフィズムを利用したパターン
  - AbstractExpressionでクライアントに対してアクセスさせるための共通APIを定義
  - NonterminalExpressionは内部にAbstractExpression型のオブジェクトを保持
  - クライアントやNonterminalExpressionは、共通APIを使用することで具体的な実装を意識する必要がなくなる
  - TerminalExpressionやNonTerminalExpressionの追加・削除・切り替え等が可能

### メリデメ
- メリット
  - 既存のコードを修正することなく、規則の追加・拡張が可能
- デメリット
  - シンプルな規則を実現する場合、コードがより複雑になる可能性がある

### 使い所
- 特定の文法で記述された内容を解析して処理したい場合
  - 正規表現
  - SQL解析
  - プログラミング言語