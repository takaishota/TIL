git_diffで行末に「^M」が表示される問題の解決方法
----------
gitでWindowsとMac/Linuxを併用している場合に改行コードの違いから行末に「^M（WindowsのCRが変換されたもの）
」が表示されることがある。  
config color.ui autoなどでdiffにカラー設定している場合に起こるらしい。    
以下の方法でCRを無視するように設定できる。

解決方法（CRを無視する）：
```
git config --global core.whitespace cr-at-eol
```

gitconfigに記載する場合は

```
[core]
        whitespace = cr-at-eol
```

※ 前提として、gitのリポジトリにはLFのみ追加するようにしておくべきらしい。  
Windowsで開発している場合には、以下の設定をしておくとgitで自動的にCRLFからLFに変更してくれる。

```
git config --global core.autocrlf true
```

またはgitconfigに

```
[core]
        autocrlf = true
```

* true: コミット時に CRLF -> LF。チェックアウト時に LF -> CRLF。
* input: コミット時に CRLF -> LF に変換。チェックアウト時に　Windows：CRLFに変換を行う、Mac/Linux： LFのまま。
* false: 変換しない。
