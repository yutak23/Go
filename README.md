## Lambda by Go

Slack から AWS Chatbot 経由で Lambda 実行をする仕組みを構築した際の Lambda 関数のサンプル

## zip 作成手順

[.zip ファイルアーカイブを使用して Go Lambda 関数をデプロイする](https://docs.aws.amazon.com/ja_jp/lambda/latest/dg/golang-package.html)を実施するための手順は以下。

### 1、build-lambda-zip ツールを GitHub からダウンロード

`go.exe get -u github.com/aws/aws-lambda-go/cmd/build-lambda-zip`を cmd で実行（初回のみ）

### 2、build-lambda-zip ツールで zip を作成

`set GOOS=linux`を cmd で実行（初回のみ）<br>
続いて以下のコマンドを順に実行して zip を作成する

```
go build -o main main.go
%USERPROFILE%\Go\bin\build-lambda-zip.exe -output main.zip main
```

zip 作成後は AWS Management console から zip を upload して Deploy をする
