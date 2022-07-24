# 仮想環境
* Python を使用して、開発や実験を行う時に、用途に応じて専用の実行環境を作成し、切り替えるのが一般的であり、このように一時的に作成する実行環境を「仮想環境」という.

# 仮想環境のメリット
* システム全体で使用する Python 環境に影響を与えずにモジュールの追加/入れ替えが可能.
* 異なるバージョンの Python を使い分けたり、同じモジュールの複数のバージョンの使い分けが可能.

# 仮想環境の種類
* 主に以下の4つの方法を利用できる.

  * venv（virtualenv）
  * pyenv
  * conda系
  * Docker

  → venv 使用を推奨？
  
# 各仮想環境構築法の概要
* venv
  * このような仕組みを整備した最初のツールの1つ. 2008年に出版された Expert Python Programming ですでにベストプラクティスとして取り上げられている.
  * Python3.3 以降で venv という名前で標準ライブラリに取り込まれたので、今後の主流となっていく可能性が高い.
  * Python のデファクトスタンダードなので、各種ツールのサポートが充実. JetBrains社の Python IDE の PyCharm はプロジェクトごとの環境設定で環境の選択ができ、venv でプロジェクト以下に環境を作成してから PyCharm で開くと、選択しなくてもデフォルトで venv環境 を使用するようになっている.

* pyenv
  * Python のバージョン管理ができるコマンドラインツール. PC に異なるバージョンの Python をインストールして自由に切り替えることができる.
  * venv にはできず、pyenv にしかできないことは、複数バージョンの処理系を入れること.
  * Windows では使用できない. あまり推奨はされていない.
  <img width="621" alt="スクリーンショット 2022-07-23 13 15 39" src="https://user-images.githubusercontent.com/53923545/180640026-efe9339c-94e0-4540-a554-bb8baff17a48.png">

* conda系
  * データ分析系で人気のディストリビューション. データ分析に使用可能なライブラリやツールを含めて提供.
  * 開発環境に依らず使用でき、docker image 等を使用して他者への配布等もラク.
  * Docker の学習コストがいる.

# venv のインストール
* 生の Python（version3.3以降） のインストール
  * mac Monterey 12.3 release により Python2.7 は削除されているので、Python をインストールしていない状態だと pythonコマンド を叩いても反応しない.
    ```zsh
    brew install python3
    ```
* pythonコマンドの修正
  * デフォルトで pythonコマンド は python2 のパスを指していたが、上記アップデートで python2 が削除されたことで、command not found になる.  
  -> python 実行時に python3 のパスを指すように環境変数を設定！
  * zsh の場合は .zshrc、bash の場合は .bash_profile に環境変数を設定する.  「.zshrc」がない場合は自分で作成する.
    ```zsh
    # エイリアスの設定
    alias python='python3'
    alias pip='pip3'

    # 環境変数の設定
    # export 環境変数名=環境変数の値
    export PYTHON_HOME="fullpath"

    # パスの追加
    # export PATH=通したいパス:$PATH
    export PATH="$PYTHON_HOME:$PATH"
    ```
  * 設定の有効化
    ```zsh
    source ~/.zshrc
    ```

# venv の使用方法
* 新しい環境の作成
  ```zsh
  mkdir [project_dir]
  cd [project_dir]
  python3 -m venv [new_env_name]

  # 上記で、「alias python='python3'」のエイリアスを設定した場合
  python -m venv [new_env_name]
  ```
* Activate
  ```zsh
  # sourceによるactivate
  source [new_env_name]/bin/activate

  # activateスクリプトによるactivate
  . [new_env_name]/bin/activate
  ```
* deactivate
  ```zsh
  deactivate
  ```
* 環境の削除
  ```zsh
  rm -rf [project_dir]
  ```

# 参考
* [仮想環境: Python環境構築ガイド](https://www.python.jp/install/windows/venv.html)
* [pyenvが必要かどうかフローチャート](https://qiita.com/shibukawa/items/0daab479a2fd2cb8a0e7)
* [DockerでPython実行環境を作ってみる](https://qiita.com/jhorikawa_err/items/fb9c03c0982c29c5b6d5)
* [acOS版Pythonのインストール: Python環境構築ガイド](https://www.python.jp/install/macos/install_python.html)
* [[初心者向け]python3インストール後にpython3を実行できるがpythonコマンドでエラーになる？](https://dev.classmethod.jp/articles/python-commands-give-me-not-found-errors/)
* [初めて Mac で zsh を使う人のためのチュートリアル](https://mollifier.hatenablog.com/entry/2013/02/22/025415)
* [zshのmacでPATHを通す方法（設定ファイルに環境変数を加える）](https://amateur-engineer.com/mac-path-zsh/)
* [venvで作成した仮想環境内のPythonバージョンを変更したい](https://dev.classmethod.jp/articles/change-venv-python-version/)
* [venv: Python 仮想環境管理](https://qiita.com/fiftystorm36/items/b2fd47cf32c7694adc2e)
