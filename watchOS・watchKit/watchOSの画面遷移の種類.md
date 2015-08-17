watchOSの画面遷移の種類
---
### 複数画面間の画面遷移は2種類のUIしか使えない

1. Page-Based Interface ページベースのUI
  * Storyboard で Interface Controller を置いて relationship を next page で接続するとページ化される
  * ページのセット（集合）は init メソッドなどで reloadRootControllersWithNames:contexts: メソッドを呼び出して変更する事ができる
  * 複数ページの中で最初に表示するページを指定するには init か awakeWithContext: で becomeCurrentPage メソッドを呼ぶ

2. Hierarchical Interface 階層的なUI
  * Storyboard ではボタン、グループ、テーブルの row から push segue を作成する
  * コードで画面遷移を行うには pushControllerWithName:context: メソッドを呼ぶ

※ 両方ともモーダルでの表示が可能
