# Xcode とは
* Apple社が開発/リリースしているソフトウェアで、Mac や iPhone、iPad 向けのアプリケーションを行えるようにする統合開発環境（IDE）.

# xcode-select とは
* Xcode に含まれるコマンドラインツール.
* Xcode をインストールしなくても、xcode-select をインストールすれば、Homebrew を使用可能.
* Apple製品向けのアプリ開発をする予定がないのであれば、Xcodeはインストールせず、xcode-select だけをインストールするのが吉（Xcode は容量食いすぎる）.

# xcode-select のインストール
```zsh
# インストールされているか確認
xcode-selcet -v
-> インストールされていれば、「xcode-select version ????」が出てくる

# インストール
xcode-select --install
```

# 参考
[XcodeなしでHomebrewを使う方法【容量大幅削減】](https://dezanari.com/homebrew-without-xcode/)
