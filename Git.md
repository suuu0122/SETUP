# Mac デフォルトの Git
* Mac にデフォルトで Git が入っている.
  ```zsh
  git --version
  # git version 2.30.1 (Apple Git-130)
  ```
  
# Homebrew での Git への変更
* 以下コマンドで Git のインストール.
  ```zsh
  brew install git
  ```
* パスの変更
  * whichコマンド で git のパスを取得
    ```zsh
    which git
    ```
  * .zshrc にパス追加.
    ```zsh
    export PATH="whichコマンドで取得したパス:$PATH"
    ```
* 設定の有効化
  ```zsh
  source ~/.zshrc
  ```

# Git のデフォルトブランチを master から main に変更
* Git の version を確認
  * 2.28.0 以降ならコマンドでデフォルトのブランチ名を変更可能. 2.28.0 未満ならアップデートする.
    ```zsh
    git --version
    ```
* git config でデフォルトブランチの変更
    ```zsh
    git config --global init.defaultBranch main
    ```

# 参考
* [Git/M1/MaxOS】Apple のデフォルトGit から Homebrew の Git へ切り替える方法](https://44igarashi.hatenablog.com/entry/m1_homebrew_git_install)
* [Gitのデフォルトブランチをmasterからmainに変更する方法](https://qiita.com/fk_chang/items/a4839a595fef9a2c3724)
    
