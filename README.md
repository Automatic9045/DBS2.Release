# 発車標２（DBS2） for 聖光学院交通研究部
本体ソフトウェアのプロジェクトです。

## Wiki

GitHubにて公開しています。[こちら](https://github.com/Automatic9045/DBS2.Release/wiki)

## バグかな？と思ったら

#### 1. WikiのFAQを確認する

よくある質問を[Wiki](https://github.com/Automatic9045/DBS2.Release/wiki)のFAQにまとめてあるので、まずはこちらを確認して下さい。

#### 2. Issuesを確認する

既に確認されている不具合は[こちら](https://github.com/Automatic9045/DBS2.Release/issues)にまとめてあるので、既知の不具合か確認して下さい。

#### 3. Issuesに投稿するか、開発者へ連絡する

未知の不具合の場合、あるいは既知の不具合であっても何か情報を提供頂ける場合は、

**GitHubアカウントをお持ちの場合**……Issuesに追加して下さい。

**GitHubアカウントをお持ちでない場合**……開発者に連絡して下さい。

## リリースノート

同梱しているプラグインに関する内容も含まれます。

### Version 2.0.0-beta1（2020/6/5）

Version 1.xからコードを全て書き直しました。

#### 本体

- 描画をGDIによるものからDirectXによるものに変更しました。描画が高速に、そして綺麗になりました。
- ショートカット機能が使いやすくなりました。表示変更の効率化に貢献します。
- コントロール（旧称：オブジェクト）名を検索できるようになりました。
- Version 1.xにおける「メインファイル」を、「パネルファイル」に置き換えました。XML形式となり、保守性・可読性が格段に向上しました。
- プラグインの作成に可読性・保守性の高い.NET系の言語（C#、VisualBasic.NET、C++/CLIなど）を利用できるようになりました。

※ショートカット機能は未実装です。

#### サンプルプロジェクト

- Version 1.xに同梱していたサンプルの表示を再現したサンプルプロジェクトを同梱しました。

#### LEDプラグイン

- 一つのパーツのコマ画像として複数枚の画像を登録、グループ化できるようになりました。
- パーツ名、グループ名、コマ名を検索できるようになりました。
- ニーズにお応えし、自由入力機能が使いやすく進化しました。パーツ単位でオリジナルの表示を行えます。
- 今までカンマ区切りで書いていたパーツファイル等がXML形式に。保守性・可読性が格段に向上しました。

※自由入力、お知らせ表示は未実装です。

#### 標準ストラクチャープラグイン

- 直線、長方形、画像といったよく使われるものをコントロールとして実装、プラグインとしました。
  - Version 1.xではメインファイルにHSPコードで記述する必要がありましたが、簡単なコードを1行記述するだけで埋め込めるようになります。

### Version 2.0.0-RC2（2021/1/1）

#### 本体

- ショートカット機能を実装しました。編集ウィンドウから利用可能で、検索も可能です。
- 誤終了防止ロック機能を実装しました。使用中に誤ってウィンドウを閉じてしまう心配が無くなりました。
- 「別のプロジェクトを開く」機能を実装しました。

#### LEDプラグイン

- 自由入力機能を実装しました。Version 1.xから大幅にパワーアップし、パーツ単位でオリジナルの表示が出来るようになりました。
- 一行表示（旧称：自由入力、お知らせ表示を統合）機能を実装しました。スクロールの有無も設定可能です。

### Version 2.0.0-RC3（2020/1/26）

#### 本体

- アプリケーション終了時、各プラグインが表示内容をバックアップ出来るようになりました。次回起動時にバックアップから表示内容を復元出来ます。
- 予期せぬエラーが発生した際、自動的にアプリケーションの再起動とウィンドウの状態及び表示内容の復元を行うようになりました。
- 新しいバージョンがリリースされている場合、アプリケーション起動時に通知するようになりました。
- 「プロジェクトのリロード」機能を実装しました。
- 「別のプロジェクトを開く」実行時、アプリケーションが再起動するようになりました。メモリ消費の抑制が期待出来ます。
- 右クリックメニューの「取扱説明書を開く」を削除、新たに「Wiki を開く」を追加しました。
- デバッグ用に、右クリックメニューに「エラーを発生させる」を追加しました。正規バージョンリリース時に削除予定です。
- ディスプレイの表示スケールが100%以外に設定されている場合、全画面表示時にウィンドウがずれる不具合を修正しました。

#### サンプルプロジェクト

- 上部の表記「今度の発車は」を「只今走行中の車両は」に変更しました。

#### LEDプラグイン

- 表示内容のバックアップに対応しました。
- 直感的でなかったコントローラーの一部のレイアウトを変更しました。
- ```MillisecLedDisplay```（現在の経過ミリ秒数を5桁で表示するLEDディスプレイコントロール）の一万の位が機能しない不具合を修正しました。

#### 標準ストラクチャープラグイン

- ```Rectangle```（長方形）コントロールの```Fill```（塗りつぶし色）プロパティに```Stroke```（枠線色）プロパティの値が適用される不具合を修正しました。