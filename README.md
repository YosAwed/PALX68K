# PALX68K

ＰＡＬ（バージョン５．３）

これは、X68000で動作する言語です。PAL：継承階層を扱う拡張Prologと呼ばれています。

## 設定

- 以下の環境変数を設定して下さい。
```SETENV.BAT
setenv PALDIR  $(PAL)/
setenv PLIB    $(PAL)/plib/
setenv PIE     new
setenv EDIT    jvi
setenv INFO    off
```

- 例えば
```
setenv PALDIR       /mnt3/prolog/pie/       ;;最後の'/'を忘れないように
setenv PLIB         /mnt3/prolog/pie/plib/  ;;最後の'/'を忘れないように
setenv PIE          new                     ;;呪文ですので唱えて下さい
setenv EDIT         jvi                     ;;$(PAL)/plib/pie.man参照
setenv INFO         off                     ;;$(PAL)/plib/pie.man参照
```

## マニュアル
- $(PAL)/plib/pie.manを読んで下さい。
- あるいは、PAL起動後、(man)と入力するとマニュアルが読めます。

## テスト
例えばAppendという文字列を結合するプログラムは次のようになります。*は変数を表します。*xは変数xです。
```append.p
(as (append () *x *x))
(as (append (*a . *x) *y (*a . *z))
    (append *x *y *z))
```
これを入力後
```
(append (a) (b) *)
```
と入力すると*のところに結果が入り
```
(append (a) (b) (a b))
```
という結果がでてきます。
面白いのは、
```
(append (a) * (a b c))
```
と入力すると
```
(append (a) (b c) (b c))
```
という結果が返ってくるところです。

## バグ
- また、マニュアルには記載されていますが、使えない述語があります。
  - trans_clause
  - restrict/2　(restrict/1は使えます)
- さらに、マニュアル自体にもバグがありますので注意して下さい。
- このほか、まだまだ多くのバグが潜んでいると思われます。

- setenv.batの USERを適当な名前にしておく。もし autoexec.batで自分の
- USERを設定してあるなら、setenv.batのUSERは、消すこと。
