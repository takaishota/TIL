ATSによるHTTP接続制限の回避方法
---
info.plistに以下の設定を追加する

      <key>NSAppTransportSecurity</key>
      <dict>
          <key>NSAllowsArbitraryLoads</key>
          <true/>
      </dict>

![キャプチャ](img/ats_img.png)
