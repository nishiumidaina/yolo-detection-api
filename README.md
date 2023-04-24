# yolo-detection-api
YOLOv8を使用した物体検出用API
## API
POST: [http://localhost:9000](http://localhost:9000/detect)  
リクエスト
```
[
    {
        "id": 1,
        "spots_url": "https://www.youtube.com/watch?v=3kPH7kTphnE"
    },
    {
        "id": 2,
        "spots_url": "https://www.youtube.com/watch?v=3CmwLOgQxIY"
    }
]
```
レスポンス
```
[
    {
        "id": 1,
        "count": 55
    },
        {
        "id": 2,
        "count": 32
    }
]
```
## 環境構築
1.コンテナをビルド  
```
docker compose up -d --build
```
2.コンテナに入る
```
docker container exec -it yolo-detection-api-python-1 bash
```
3.FastAPIのサーバーを立ち上げる
```
uvicorn api:APP --host=0.0.0.0 --port=9000
```
