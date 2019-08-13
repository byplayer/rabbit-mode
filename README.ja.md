# このリポジトリは

https://github.com/rabbit-shocker/rabbit/tree/master/misc/emacs
のリポジトリを qelpa でインストールできるようにするためにコピーしました。

# -_- rd -_-

= README.ja

$Id$

== rabbit-mode.el

Rabbit のソースファイル用の Emacs メジャーモードです．

== インストール

.emacs に以下を記述してください．

(autoload 'rabbit-mode "rabbit-mode" "major mode for Rabbit" t)
(add-to-list 'auto-mode-alist '("\\.\\(rbt\\|rab\\)\$" . rabbit-mode))

== 目次

=== Rabbit の操作

- ((<Emacs から Rabbit を起動する>))

=== 移動

- ((<次のスライドへ移動する>))
- ((<前のスライドへ移動する>))

=== 挿入

- ((<タイトルを挿入する>))
- ((<画像のテンプレートを挿入する>))
- ((<スライドを挿入する>))
- ((<箇条書きを挿入する>))

=== スライド操作

- ((<スライドを削除する>))
- ((<スライドをコピーする>))
- ((<スライドを複写する>))

=== 設定

- ((<画像テンプレートのデフォルトのサイズ指定方法を変える>))
- ((<rabbit-mode の変数>))

== Rabbit の操作
=== Emacs から Rabbit を起動する

rabbit-run-rabbit を実行します．デフォルトのキーバインドは C-c C-r です．

(('*'))Rabbit<ファイル名>*というバッファが作られ，Rabbit のメッセージが書き込
まれます．

== 移動
=== 次のスライドへ移動する

rabbit-next-slide を実行します．デフォルトのキーバインドは M-n です．

=== 前のスライドへ移動する

rabbit-previous-slide を実行します．デフォルトのキーバインドは M-p です．

== 挿入
=== タイトルを挿入する

rabbit-insert-title-template を実行します．デフォルトのキーバインドは
C-c C-t です．

プレゼンテーションのタイトルとメタデータを入力します．デフォルトのメタ
データを変数に設定可能です．設定できるメタデータは

- rabbit-author(著者)
- rabbit-institution(所属)
- rabbit-theme(テーマ)

です．

=== 画像のテンプレートを挿入する

画像サイズは割合で指定するのが便利だと思いますので，割合指定がデフォル
トになっています．

==== 画像サイズを割合で指定する場合

rabbit-insert-image-template-default を呼びます．デフォルトのキーバイン
ドは C-c C-i です．

画像ファイルのパス，キャプション，画像サイズの割合を入力します．ファイ
ルパス以外は省略可能です．

==== 画像サイズの指定方法も決める場合

rabbit-insert-image-template を呼びます．デフォルトのキーバインドは C-c i です．

画像ファイルのパス，キャプション，サイズ指定の方法，サイズを入力します．
ファイルパス以外は省略可能です．

サイズ指定の方法は

- relative
- normalized
- pixel(幅と高さを指定)

から選びます．

=== スライドを挿入する

rabbit-insert-slide を呼びます．デフォルトのキーバインドは C-c C-s です．

=== 箇条書きを挿入する

rabbit-insert-items を呼びます．キーバインドは割り当てられていません．

項目を入力していき，空文字を入力すると修了します．

== スライド操作
=== スライドを削除する

rabbit-delete-slide を実行します．デフォルトのキーバインドは C-c C-d です．

=== スライドをコピーする

rabbit-copy-slide を実行します．キーバインドは割り当てられていません．

現在のスライドがキルリングに保存されます．

=== スライドを複写する

rabbit-duplicate-slide を実行します．キーバインドは割り当てられていません．

現在のスライドのコピーを，次のスライドとして挿入します．現在のスライド
の内容を少しだけ変えたい場合に便利です．

=== 画像テンプレートのデフォルトのサイズ指定方法を変える

変数 rabbit-default-image-size-unit にサイズ指定方法をセットします．デフォ
ルトは"relative"です．

有効な値

- "relative"
- "normalized"
- "pixel"

== 変数

: rabbit-command

Rabbit の起動コマンドです(デフォルトは"rabbit")．

: rabbit-author

著者名です．タイトルページのテンプレートで使われます(デフォルトは nil)．

: rabbit-institution

著者の所属です．タイトルページのテンプレートで使われます(デフォルトは nil)．

: rabbit-theme

プレゼンテーションのテーマです(デフォルトは"rabbit")．

: rabbit-default-image-size-unit

画像ファイルのテンプレート挿入で使われるデフォルトのサイズ
指定方法です(デフォルトは"relative")．

: Faces

rabbit-mode の各 face です．

     * rabbit-heading-face
     * rabbit-emphasis-face
     * rabbit-verbatim-face
     * rabbit-term-face
     * rabbit-footnote-face
     * rabbit-link-face
     * rabbit-code-face
     * rabbit-description-face
     * rabbit-keyboard-face
     * rabbit-variable-face
     * rabbit-comment-face
