## high avaliavility submit

### ResourceName

StackName: udagramMiyaoka
s3BucketName: udagram-test-seiya

### About paramter file

ignore parameter file. need parameter is

```json
[
  {
    "ParameterKey": "EnvironmentName",
    "ParameterValue": "Your value"
  },
  {
    "ParameterKey": "PrivateSubnet1CIDR",
    "ParameterValue": "Your value"
  },
  {
    "ParameterKey": "PrivateSubnet2CIDR",
    "ParameterValue": "Your value"
  },
  {
    "ParameterKey": "KeyPair",
    "ParameterValue": "Your value"
  },
  {
    "ParameterKey": "S3BucketName",
    "ParameterValue": "Your value"
  }
]
```



### how to

*create stack*

```sh
./create.sh stack-name udagram_tmp.yml udagram_parameter.json
```

*update stack*

```sh
./update.sh stack-name udagram_tmp.yml udagram_parameter.json
```

*delete stack*

```sh
./delete.sh stack-name
```



### japanese memo

- サーバをprivateサブネットに配置。
- apache server
- s3
- server size 4
- 自分でapacheはいれるhttps://www.linuxacademy.ne.jp/lablog/infrastructure/532/
- s3に他の開発者がデータを配置する予定
- [ ] ubuntuimage amiを探す ami-07b4f3c02c7f83d59
- roleの作成が絡むと https://blog.websandbag.com/entry/2017/12/30/234729 capabilitiyの設定が必要
- keypairはブラウザで作成した
- Download dirにある
- keyなしで作成してあとからkeyを付与はできなかった, なのでインスタンスを増やしてそちらでテスト
- vpcに関連づけられるmain route tableを変更してみる
- routeテーブルの設定ができていないとトラッフィックの処理をしないのでsshできない
- aws s3 sync src/ s3://udagram-test-seiya一旦実行

configure

![lucidchartimg](./images/udacity_exam.png)