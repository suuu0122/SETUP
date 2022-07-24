# VSCode とは
* 2015年から Microsoft社 が開発し続けているエディタ.
* Mac OS, Linux, Windows で使用可能.
* 半永久的に無料で使い続けることができ、機能制限がない.
* 拡張機能を追加することが可能.
* 毎月アップデートが有り、拡張機能を追加することでのみ使用できた機能がデフォルトに組み込まれることがある.

# VSCode のデフォルト機能
* ファイル名検索
  * VSCode で開いている親ディレクトリを起点に全ファイル名を検索可能（部分一致で検索することが可能）.
  * command + p
* 正規表現による文字列検索
  * VSCode による文字列検索の方法は以下の2つの方法が存在する.  
    * 1つのファイルに対しての文字列検索
    * 親ディレクトリ以下に存在する全ファイルに対しての文字列検索
  * 上記2つの方法それぞれに対して、以下の3つのオプションを付けて、検索することが可能.
    * 大文字小文字を区別して検索
    * 正規表現で検索
    * 単語検索
  * 上記検索オプションを組み合わせて、ファイル内の文字列の個別 or 一括置換も可能.
  * command + f / command + shift + f
* 複数行を同時に編集可能
  * カーソルを複数行に選択して操作可能.
  * command + option + ↑↓
* ウィンドウの複数表示が可能

# VSCode のインストール
* 下記コマンド実行
  ```zsh
  brew install visual-studio-code
  ```
  * 2022/4/16時点で、下記コマンドで「--cask」オプションを付けなくても自動的に補完されるようになっている. オプションを付けても問題はない.

* --caskオプション とは
  * Homebrew では、CUIアプリ以外にもGUIアプリ も管理可能.
  * GUIアプリをインストールするときに付けるオプション.
  * Homebrew のバージョンアップで --caskオプションは不要になった.

# 参考
* [VS Codeをなぜ、使い続けているのか？](https://zenn.dev/kenkenlysh/articles/a3f7f45bc0144e)
* [恥ずかしくて聞けないHomeBrew Caskが超絶便利だったこと](https://eng.shibuya24.info/entry/homebrew-cask)