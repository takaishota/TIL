watchOSのライフサイクルについて
---
* init  
  ↓
* awakeWithContext：iOSにおける viewDidLoad に近いイメージ  
  ↓
* willActivate：iOSにおけるviewWillAppear: に近いイメージ  
  ↓
* didDeactivate：iOSにおけるviewDidDisappear: に近いイメージ

![ライフサイクル](img/tumblr_inline_nnwiq5ALwD1r0hcti_1280.png)

画像は以下より引用：(http://blog.mikeswanson.com/post/118262770484/watchkit-controller-life-cycle)