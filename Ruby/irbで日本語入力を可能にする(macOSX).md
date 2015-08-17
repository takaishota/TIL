irbで日本語入力を可能にする(macOSX)
---
ターミナルからirbへのコマンド入力ライブラリをOSX標準のlibeditから日本語対応しているreadlineに変更する

* readlineのインストール  
```ruby
brew install readline
```

* irbの参照ライブラリをlibeditからreadlineへ切り替え  
```ruby
# install_name_tool -change 古いライブラリのパス  
新しいライブラリのパス 参照しているbundleのパス
$ sudo install_name_tool -change "/usr/lib/libedit.3.dylib" "/usr/local/Cellar/readline/6.3.8/lib/libreadline.dylib" "/System/Library/Frameworks/Ruby.framework/Versions/2.0/usr/lib/ruby/2.0.0/universal-darwin14/readline.bundle"
```
    * readlineのパスの確認方法
    ```
        brew list readline | grep libreadline.dylib
    ```
    * irbが参照しているbundleのパスの確認方法
    ```
        $ irb
        irb(main):001:0> puts $LOADED_FEATURES.grep /readline/  
    ```
    * libeditのパスの確認方法
    ```
        otool -L /System/Library/Frameworks/Ruby.framework/Versions/2.0/usr/lib/ruby/2.0.0/universal-darwin14/readline.bundle
    ```
