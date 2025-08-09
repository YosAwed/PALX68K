# PALX68K

ＰＡＬ（バージョン５．３）

これは、X68000で動作するPrologに似た言語です。

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

## バグ
- SONY NEWS(R3000)での情報付き変数を使う場合、数値演算の述語にバグがあります。
- また、マニュアルには記載されていますが、使えない述語があります。
  - trans_clause
  - restrict/2　(restrict/1は使えます)
- さらに、マニュアル自体にもバグがありますので注意して下さい。
- このほか、まだまだ多くのバグが潜んでいると思われます。
- バグを見つけた方はご連絡下さい。

- SONY NEWS(MC680X0, R3000)での動作を確認しています。
- SUN3なら問題ないと思いますが、SUN4(SPARC)はちょっと心配です。

- setenv.batの USERを適当な名前にしておく。もし autoexec.batで自分の
- USERを設定してあるなら、setenv.batのUSERは、消すこと。
