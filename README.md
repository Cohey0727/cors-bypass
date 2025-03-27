# CORS Bypass

シンプルなNginxベースのCORSバイパスプロキシサーバー。APIリクエストに必要なCORSヘッダーを自動的に追加します。

## 機能

- すべてのリクエストにCORSヘッダーを追加
- 環境変数による簡単な設定
- Dockerコンテナとして実行可能

## セットアップ

1. リポジトリをクローン
2. `.env.example`を`.env`にコピーして設定
3. Dockerコンテナを起動

```bash
cp .env.example .env
# .envファイルを編集してUPSTREAM_URLを設定
docker compose up -d
```

## 使用方法

プロキシサーバーが起動したら、`http://localhost:9999`にリクエストを送信することで、設定したアップストリームURLにCORSヘッダー付きでリクエストが転送されます。

テストエンドポイント:
```
curl http://localhost:9999/__healthcheck
```

## 環境変数

- `PORT`: プロキシサーバーのポート番号（デフォルトは9999）
- `UPSTREAM_URL`: プロキシ先のURLを指定

## 注意事項

開発環境専用です。本番環境での使用は推奨されません。
