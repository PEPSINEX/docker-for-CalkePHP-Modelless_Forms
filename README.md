# docker-for-CalkePHP-Modelless_Forms

# Usage
```bash
# 1. リポジトリの複製
git clone git@github.com:PEPSINEX/docker-for-CalkePHP-Modelless_Forms.git

# 2. docker-composeのあるフォルダへ移動
cd docker-for-CalkePHP-Modelless_Forms/docker/

# 3. アプリケーションフォルダの作成
mkdir ../html

# 4. コンテナの作成、バックグランドで起動
docker-compose up -d
# 4'. （コンテナの再構築が必要な場合）
docker-compose up --build -d

# 5. 作成したコンテナに入る
docker exec -it myapp-web bash

# 6. CakePHP4アプリケーションの作成
composer self-update && composer create-project --prefer-dist cakephp/app:4.* .
# 6'. （既にアプリケーション作成済で、vender配下のパッケージをインストールするだけの場合。「composer.json」の存在するフォルダにて）
composer install

# 7. 作成したアプリケーションのパーミッション設定(/html/config/app.php に以下の記述を追加）
'Log' => [
    'debug' => [
        'mask' => 0666,
    ],
    'error' => [
        'mask' => 0666,
    ],
],
```
