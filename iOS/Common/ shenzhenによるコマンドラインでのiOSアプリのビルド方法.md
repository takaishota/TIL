shenzhenによるコマンドラインでのiOSアプリのビルド方法
---

※1 github: https://github.com/nomad/shenzhen
※2 参考：shenzhenを使って超簡単ipaファイル作成
http://qiita.com/k_kinukawa/items/8718aba35060cf838ffa

## インストール方法

```
$ gem install shenzhen
```

## ビルド方法

```
$ cd /path/to/iOS Project/
$ ipa build (-s スキーマ名)（-c Debug/Release）
```
* -s を指定しなければ、ipa実行後にスキーマを選択させる入力待ち状態になります。
* -c を指定しなければ、Build-ConfigurationがDebugの状態でビルドされます。
* 正常完了するとカレントディレクトリにipaファイルが生成されます。

```
$ ipa info
```

* 上記のコマンドで適用されるプロビジョニングプロファイルの情報が表示されますので
* そちらで適用されているプロファイルが正しいか確認してみてください。

## ビルド -> 配布

```
$ cd /path/to/iOS Project/
$ ipa build
$ ipa distribute:（ftp、itunesconnect、DeployGateなど配布先）
```

* ipaファイルが配信先にアップロードされる
* 配布先の指定方法の詳細は※1 githubを参照。
