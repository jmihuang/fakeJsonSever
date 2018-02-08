# 使用 JSON Server 快速建置 Fake REST API 服務

保哥直播教學
[slideShare](https://www.slideshare.net/WillHuangTW/use-json-server-as-a-fake-rest-api)
[直播視頻](https://www.youtube.com/watch?v=uFKa4xrc42c)


** 安裝 **
```
 npm install -g json-server
```

** 啟動 **
```
 json-server --watch db.json
```

** 啟動account.json文件 **
```
 json-server -w account.json
```

** 指定不同port **
 ```
 json-server -w account.json --port 3004
 ```

** 測試API **
- localhost:3000 預設首頁文件
- GET localhost:3000/db 讀取完整資料庫資料
- GET localhost:3000/db/posts/1 讀取第一筆資料

** 命令提示字元打入s可以存一份備份 **

## 支援的HTTP的方法
- GET 取得資料
- DELETE 刪除資料
- POST 建立資料
- PUT 更新資料(完整)
- PATCH 更新資料(更新部分)

## 資料操作的方式
** 全文檢索 **
http://localhost:3000/accout?q=jamie
** 資料篩選(完全比對) **
http://localhost:3000/accout?user=jamie
http://localhost:3000/accout?user.name=jamie
** 資料分頁 **
http://localhost:3000/accout?_page=3
http://localhost:3000/accout?_page=3&_limit=3
http://localhost:3000/accout?_start=2&&_end=5
http://localhost:3000/accout?_start=2&_limit=2
** 資料排序 **
http://localhost:3000/accout?_sort=id&_order=DESC

## 進階資料篩選
** _like相似於字串 **
http://localhost:3000/accout_like=jamie
** _gte大於等於數值 **
http://localhost:3000/accout_like=jamie＆age_gte=30
** _lte小於等於數值 **
http://localhost:3000/accout_like=jamie＆age_lte=30
** _ne不等於 **
http://localhost:3000/accout_like=jamie＆age_ne=30

## 自訂網址路由

