# custom-request-transformer

kongのプラグインのカスタマイズのサンプルになります  
ここでは`request-transformer`に環境変数の値を追加しています

詳しくは[Zennの記事](https://zenn.dev/naoto_raimi/articles/443399837088a1)をご覧ください

## App Start

```
docker compose up -d --build
```

## Sample Request 

```
curl -X POST -H "Content-Type: application/json" -d '{"test": "test"}' http://localhost:8000/httpbin/post

>>> 
{
  "args": {}, 
  "data": "{\"secret\":\"secret\",\"test\":\"test\"}", 
  "files": {}, 
  "form": {}, 
  "headers": {
    "Accept": "*/*", 
    "Content-Length": "33", 
    "Content-Type": "application/json", 
    "Host": "httpbin.org", 
    "User-Agent": "curl/7.79.1", 
    "X-Forwarded-Host": "localhost", 
    "X-Forwarded-Path": "/httpbin/post", 
    "X-Forwarded-Prefix": "/httpbin/post"
  }, 
  "json": {
    "secret": "secret", 
    "test": "test"
  }, 
  "url": "http://localhost/post"
}
```