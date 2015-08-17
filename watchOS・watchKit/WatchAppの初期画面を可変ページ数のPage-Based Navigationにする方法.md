WatchAppの初期画面を可変ページ数のPage-Based Navigationにする方法
---

1. WatchAppのエントリ画面のクラス（デフォルトはInterfaceController.swift）のwillActivateで下記のクラスメソッドを実行する。
identifierの配列数分のページ数ができる。

        WKInterfaceController.reloadRootControllersWithNames(storyboardIds, contexts: info)

  * storybordIds:storyboardに配置したInterface Controllerに指定したIdentifier名の配列（[AnyObject]）
  * info:storyboardに配置したInterface Controllerに対応するクラスで受け取るデータの配列（[AnyObject]?）
2. storyboardIdsに対応するクラスのawakeWithContext(context: AnyObject?)でデータを取得してラベルに代入するなどに使用する。
