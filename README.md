# Python 練習用

各章の問題を解いてください。回答がわからない場合は、問題の下の解説を読みもう一度問題を解いてみてください。

# 目次
* Python 練習用
* 目次
* 問題
    * 1.Pythonについて
    * 2.環境構築
    * 3.基本的な文法
    * 4.変数とデータ型、演算子
    * 5.制御文(条件分岐、繰り返し)
    * 6.データ形式(リスト、辞書、リスト内包形式)
    * 7.関数、クラス
    * 8.ファイル操作
    * 9.モジュール
    * 10.発展問題

# 問題
## 1. Pythonについて

### 問1
Pythonとはどんな動物か？

<details><summary>解説</summary>

Python言語の製作者グイド・ヴァン・ロッサムが
「Monty Python's Flying Circus（空飛ぶモンティ・パイソン）」
で知られるイギリスの喜劇集団Monty Python
の熱狂的なファンであったため、
自身の作成した言語にPythonと名付けた。
以下「Python」と表記があった場合は、基本的にPython言語を指す。

</details>

<details><summary>正解</summary>

蛇の一種、ニシキヘビのこと。

</details>

### 問2
Pythonはコンパイラ型かインタープリタ型のどちらか？

<details><summary>解説</summary>

コンパイラ型言語とインタープリタ型言語は、プログラムを実行する際にコードをどのように処理するかに基づく分類である。

### コンパイラ型言語
コンパイラ型言語では、ソースコードを一度に全て機械語（バイナリコード）に変換し、その後実行する。そのため、プログラムは、実行前に「コンパイル」というプロセスを経る。

#### 特徴：
1. **高速な実行**: コンパイル後、機械語の実行ファイルが生成されるため、プログラムの実行はとても高速。
2. **事前エラーチェック**: コンパイル時に文法エラーや型のミスマッチなどが検出されるため、プログラムの正確性が高まる。
3. **プラットフォーム依存性**: コンパイルされたバイナリファイルは特定のプラットフォーム用に生成されるため、他のプラットフォームで動作させるには再コンパイルが必要である。
4. **開発時間が長い**: プログラムの修正後、再度コンパイルが必要であり、実行に至るまでの手順が長いことがある。

#### 代表的な言語：
- C、C++
- Rust
- Go

### インタープリタ型言語
インタープリタ型言語では、ソースコードを逐次解析し、その場で実行する。事前にコンパイルするプロセスを必要としない。ソースコードを逐次解析するプログラムをインタプリタという。

#### 特徴：
1. **実行速度が遅い**: ソースコードをその場で1行ずつ解析・実行するため、コンパイル型言語に比べて実行速度はかなり遅くなる。
2. **クロスプラットフォーム**: プラットフォーム上で動くインタープリタさえ存在すれば、どのプラットフォームでも同じソースコードを実行できるため、移植性が高い。
3. **実行時エラーが多い**: コンパイル型言語とは異なり、実行時にエラーが発生することが多く、事前に検出されるエラーは限られる。
4. **動的な実行**: 実行時にコードを変更したり、動的にコードを生成して実行したりすることが容易であり、柔軟な開発が可能である。

#### 代表的な言語：
- Python
- JavaScript
- Ruby

### ハイブリッドアプローチ
一部の言語（例：Java、C#など）は、コンパイラとインタープリタの両方を組み合わせたアプローチを取っている。これらの言語は、一度中間コードといわれるバイナリファイルにコンパイルされる。そして、中間コードを動作させることのできるインタープリタで動作する。中間コードは、元のプログラム言語より機械語に近いため、高速に実行しつつ、すべてのプラットフォームで同じ中間コードを使用するため、クラスプラットフォームの開発が行える。

</details>

<details><summary>正解</summary>

インタープリタ型

</details>

### 問3
PythonはどんなOSで動作する？

<details><summary>解説</summary>

Pythonはクロスプラットフォーム言語であるため、様々なオペレーティングシステムで動作する。これは、Pythonインタープリタが異なるOS向けにビルドされているためである。また、Pythonの標準ライブラリや多くのサードパーティライブラリは、OS依存の部分を抽象化しているため、ほとんどのコードは異なるOS間でそのまま動作する。

</details>

<details><summary>正解</summary>

Pythonは以下の環境で動作する。

* Windows
* Mac OS
* Linux
* UnixベースのOS

最近はRTOS上で動作するMicro Pythonも存在する。

</details>

## 2. 環境構築

### 問4
Pythonをインストールせよ

<details><summary>解説</summary>

[ここ](https://www.python.org/downloads/)からPythonのインストーラーをダウンロードする。</br>
インストーラーの指示に従い、インストールを進める。</br>
※途中、`Add Python to environment variables`に必ずチェックを入れる。

余裕のある人は、AnacondaやPyenv、Pipenv、Poetry、Ryeなどのパッケージ管理・バージョン管理システムについて調べてインストールするのがおすすめ。科学者には、Anacondaが広く使われており、個人的にはRyeがおすすめ。

</details>

<details><summary>正解</summary>

PythonがPCに正しくインストールされた。

</details>

### 問5
インストールしたPythonのバージョンはいくつか？ターミナルに表示させよ。

<details><summary>解説</summary>

### Windowsの場合

1. スタートボタン をクリックして、検索バーに「cmd」または「PowerShell」と入力しターミナルを開く。
2. ターミナルが表示されたら、`python --version`と入力し、エンターキーを押す。

### Mac OSの場合

1. Finderで「アプリケーション」フォルダを開き、「ユーティリティ」フォルダに移動する。
2. そこに「ターミナル」というアプリがあるので、それをダブルクリックして開く。
3. ターミナルが表示されたら、`python --version`と入力し、エンターキーを押す。


### 正しく表示されない場合

インストール手順が間違っている可能性があるので、もう一度見直す。

</details>

<details><summary>正解</summary>

以下のように表示される。
```bash
$ python --version
Python [使用しているバージョン]
```

</details>

### 問6
テキストエディタを列挙せよ。

<details><summary>解説</summary>

テキストエディタとはテキストファイルを編集するツール。このツールを用いてプログラムを作成する。</br>
似ているツールにVisual StudioやEclipsが挙げられるが、これはIDE(エディタと実行環境、デバッガなどの便利機能を合わせたもの。エディタより動作が重い。)といわれるものである。</br>
現在、広く使われているVS codeはIDEに拡張可能であるが、非常に軽量である。

</details>

<details><summary>正解</summary>

Windows メモ帳、Mac テキストエディット、VS Code、Vim、Emacs、Nano、Atom、Sublime Text、TeraPad、秀丸、サクラエディタ、etc...

</details>

### 問7
VS Codeをインストールして、起動せよ。

<details><summary>解説</summary>

Visual Studio Code (VS Code) は、Microsoftが提供している軽量なコードエディタで、多くのプログラミング言語や開発ツールに対応している。

#### インストール手順：

1. [公式サイト](https://code.visualstudio.com/) にアクセスし、使用しているOSに合ったVS Codeのインストーラをダウンロードする。
2. ダウンロードしたインストーラを起動し、インストールを進める。
3. インストール時に「PATHに追加する」にチェックを入れることをおすすめ。
4. インストールが完了したら、VS Codeを起動する。

#### 初期設定（Python環境の場合）：

1. VS Codeの「拡張機能」アイコンをクリックし、`Japanese`拡張機能を検索してインストールする。
2. VS Codeの「拡張機能」アイコンをクリックし、`Python`拡張機能を検索してインストールする。
3. 一度VS Codeを再起動して、拡張機能を有効化させる。

これでPythonの開発環境が整う。

</details>

<details><summary>正解</summary>

VS Codeが正しくインストールされ、起動する。

</details>

### 問8
作業用のフォルダを作成し、VS Codeで開き、VS Code上からhello.pyというファイルを作成せよ。

<details><summary>解説</summary>

Pythonの開発を始める際には、プロジェクトごとに作業フォルダを作成し、そのフォルダ内でファイルを管理するのが一般的である。

#### 作業フォルダを作成する手順：

1. **Windowsの場合**：エクスプローラを開き、任意の場所（例: デスクトップ）で右クリックし、「新規作成」→「フォルダ」を選択してフォルダを作成する。名前を `python_leaning` などに設定する。
   
   **Mac OSの場合**：Finderを開き、任意の場所で「右クリック」→「新規フォルダ」を選択してフォルダを作成し、名前を `python_leaning` などに設定する。

2. 作成したフォルダを **VS Code** で開くには、VS Codeを起動し、「ファイル」→「フォルダーを開く」から作成したフォルダを選択する。

#### hello.pyファイルを作成する手順：

1. フォルダを開いた状態で、VS Codeの「エクスプローラー」サイドバーに移動し、「新しいファイル」アイコンをクリックして `hello.py` というファイルを作成する。
2. hello.py 内に以下のコードを入力して`ctrl` + `s`で保存する。

```python
print("Hello, World!")
```

これでファイルが作成され、Pythonのプログラムが書ける状態になる。

</details> <details><summary>正解</summary>

作業フォルダが作成され、VS Code上でhello.pyというファイルを作成した。

</details>


### 問9
VS Code上で新しいターミナルを作成し、hello.pyを実行せよ。

<details><summary>解説</summary>

VS Codeには統合ターミナル機能があり、エディタ上から直接Pythonスクリプトを実行することができる。

#### ターミナルを開く手順：

1. VS Codeを開いた状態で、上部メニューの「ターミナル」から「新しいターミナル」を選択すると、画面下部にターミナルが表示される。
   
2. 新しいターミナルが表示されたら、Pythonが正しくインストールされていることを確認するために以下のコマンドを入力する。

```bash
$ python --version
```

Pythonのバージョンが表示されれば、環境が整っている。

#### hello.pyを実行する手順：

2. `hello.py` を実行するために以下のコマンドを入力する。

```bash
$ python hello.py
```

これで、ターミナル上に `Hello, World!` と表示される。

</details>

<details><summary>正解</summary>

ターミナルを作成し、hello.pyを実行して `Hello, World!` と表示される。

</details>


## 3. 基本的な文法

## 4. 変数とデータ型、演算子

## 5. 制御文(条件分岐、繰り返し)

## 6. データ形式(リスト、辞書、リスト内包形式)

## 7. 関数、クラス

## 8. ファイル操作

## 9. モジュール

## 10. 発展問題