# crowi-wiki

## How To Use
### 構築手順
teraformとかでやれよとかいう意見はききませぇーん

基本、https://qiita.com/7tsuno/items/4db90d6c5fad7388efa3 を参照してやった

#### AWSのインスタンスを作る
気合い

#### AWSのインスタンスに入る
```
 ssh -i "m19s_crowi_wiki.pem" ec2-user@ec2-{IPV4をここに入れてね}.ap-northeast-1.compute.amazonaws.com
```


### バックアップを撮りたい
#### コンテナバックアップ
```
docker run --rm \
  --volumes-from バックアップしたいコンテナ \
  -v $(pwd):/backup \
  boombatower/docker-backup backup
```

#### DBバックアップ
```
mongodump -d [データベース名] -c [コレクション名]
```
