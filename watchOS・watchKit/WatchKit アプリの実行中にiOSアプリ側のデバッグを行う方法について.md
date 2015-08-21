WatchKit アプリの実行中にiOSアプリ側のデバッグを行う方法について
---

* WatchKitアプリのシュミレータ実行中に親のiPhoneアプリのprintなどのデバッグログがコンソールに表示されない  

  表示する方法
  * WatchAppのRun実行後、XcodeメニューのDebug > Attach to Process > （Likely TargetのYOUR iOS App) を選択
  * ブレークポイントをクリックして出てくる吹き出し中のActionにLog Message、Debugger Commandを指定して表示することができる  
  （???: らしいが、うまくいかない、、、  
  AppDelegateのhandleWatchKitExtensionRequest内でログが表示されない、watch側にreplyは返ってきている）
* 親アプリとは別プロセスなのでデバッグメッセージは、それぞれ別々のデバッグコンソールに表示される（左ペインのReport Navigatorタブを表示して確認:Command + 8）

参考:
https://realm.io/jp/news/more-watchkit-mistakes/  
Natasha Murashev
