# Mac ターミナルユーザ名変更
* デフォルトの表示
  ```zsh
  ユーザ名@ホスト名 ~ %
  ```
* 変更例
  * ユーザ名とホスト名を表示しないように変更した場合
    ```zsh
    ~ %
    ```

* .zshrc の編集
  ```zsh
  export PS1="表示させたい内容"

  # 上記変更例の場合
  export PS1="%1~ %# "
  ```
  
* 有効化
  ```zsh
  source ~/.zshrc
  ```

* 参考
  * [Macのターミナルのユーザー名の変更](https://qiita.com/yosyosyoyoyo/items/f72d2df0deb120cf1e5f)
