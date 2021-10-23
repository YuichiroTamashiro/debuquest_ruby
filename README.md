# DebuQuest -Ruby-

## 実行方法

0. clone 後最初に以下を実行してください

```
bundle install --path vendor/bundle
```

1. アプリ直下で以下を実行

```
bundle exec ruby execution.rb
```

2. 挑戦したい問題番号を入力してください

```
挑戦する問題番号を入力してください！！
1
```

3. 「2」を実行すると、`execution.rb` 内の問題番号に対応したメソッドが実行されます
   例: 問 1 だと `q1メソッド` が実行されます。

4. 各問題の指示通りの挙動になるようにコードを修正してください

※修正対象のファイルは各問題番号に対応するフォルダの範囲内で修正してください。

例: 問 1 を修正する際は `q1フォルダ` 内のみで修正

## 問題

### 問 1

- プログラムが正しく動くようにしてください

### 江原ここから

問 8

#### 問題文

プログラムが正しい値を算出するように修正してください。
但し、execute 内の指定している箇所のコードは変更しないこと

#### 解答

- 変数 number を numbers に変更

- `calc.rb`内の`twice`メソッドの処理を変更
  - `arr * 2` -> `arr.map { |number| number * 2}` のように map を使った処理に変更することで正しい値が算出される

#### 解説

エラーを rescue で拾うようにして、エラー文を読んで回答することよりも binding.pry を使ってどの処理でエラーしているのか確認する練習に良いように構成してみました。
また配列についての問題だったため、map 処理の使い方を理解していないと回答できないようにも設定しています。

問 9

#### 問題文

ランダムに設定された 3 つの数値に対して、

- 3 つの数値が全て同じになった場合「大当たり！」
- 3 つの数値のうち 2 つの数値が同じになった場合「惜しい！」
- 全ての数値が違う場合「残念！ハズレ！」

と出力されるスロットマシーンのようなアプリがあります。
このコードは現状の状態では上記のような動作条件を満たしておりません。
正しく動作するようにコードを修正してください。

#### 解答

- 23 行目 numbers.sumple -> nunbers.sample へ変更
- `self.check_numbers` メソッドの条件分岐の値と、`self.count_same_numbers`メソッドの条件分岐の値にズレがあるため、適切な結果が返ってこないようにしています。（大当たりが一生出ません）規程を満たすためにはどちらかのメソッドの 0 〜 3 の値を正しく修正して、適切な表示が返ってくるように修正する必要があります。

#### 解説

配列に関しては sample メソッドの役割を調べる程度の難易度にしていますが、条件分岐を少し細かく設定したので、初見では処理を追いながらでなければ解けないように設定しています。
問 8 同様にエラーは rescue で拾うようにしています。

### 江原ここまで
