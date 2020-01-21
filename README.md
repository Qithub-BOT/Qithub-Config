# Qithub-Config

Qithub サーバーの環境変数や各種設定ファイル置き場です。（テンプレート含む）

- ファイル名から `.tpl` を削除し、変数の値を設定して利用します。

## Qithub サーバーの挙動

Qithub のサービス（各種 Docker コンテナ）が起動される際に、別スクリプトにて以下の動作が行われます。

1. `git pull origin` でローカルのこのリポジトリを最新状態にします。
2. サーバーに環境変数を読み込みます。
3. `docker-compose up -d` でサービス・コンテナを起動します。

## 環境変数が使われるタイミング

サーバー（ホスト）側で `docker-compose up -d` が実行されると、該当 `docker-compose.yml` に記載されたサーバーの環境変数のみがコンテナに渡されます。

- 参考文献：[Docker で環境変数をホスト OS 側からゲスト OS （コンテナ）に渡す方法（各種）](https://qiita.com/KEINOS/items/518610bc2fdf5999acf2) @ Qiita
