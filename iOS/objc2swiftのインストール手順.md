objc2swiftのインストール手順
---
指定した.h/.mファイルをswift形式に出力するだけなのでプロジェクトに適用するには他にツールが必要と思われる。
既存のプロジェクトにどれぐらい適用できるかは調査中。

* JDK（7以上）のインストール
下記からダウンロードしてインストール
http://www.oracle.com/technetwork/java/javase/downloads/index.html

* Gradleのインストール

```
brew install gradle
gradle -v
```

* gradleのプロキシ設定
.gradle/gradle.propertiesを作成し、以下を記載


```
systemProp.http.proxyHost=host
systemProp.http.proxyPort=port
systemProp.http.proxyUser=user
systemProp.http.proxyPassword=***

systemProp.https.proxyHost=host
systemProp.https.proxyPort=port
systemProp.https.proxyUser=user
systemProp.https.proxyPassword=***
```

* Scalaのインストール

```
brew install scala
scala -version
```

* 環境変数の設定

```bash
# .bash_profileなどに追記
export SCALA_HOME=/path/to/scala_dir
export PATH=$PATH:$SCALA_HOME/bin
```

* ANTLRのインストール（不要かもしれません）

```
cd /usr/local/lib
sudo curl -O http://www.antlr.org/download/antlr-4.5.1-complete.jar
export CLASSPATH=".:/usr/local/lib/antlr-4.5.1-complete.jar:$CLASSPATH"
alias antlr4='java -jar /usr/local/lib/antlr-4.5.1-complete.jar'
alias grun='java org.antlr.v4.gui.TestRig'
```

* objc2swiftをgit cloneする

```
git clone  
https://github.com/yahoojapan/objc2swift.git
```

* サンプルの実行

```
gradle build
java -jar build/libs/objc2swift-1.0.jar sample/sample.h sample/sample.m
```
