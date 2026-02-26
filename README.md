# FB_group_crawler_with_RESTful_API

使用 FastAPI 建立 RESTful API，  
提供 Facebook 社團貼文與留言資料之查詢介面。  

## 專案架構
├── app/  
│ ├── main.py # API 路由與入口  
│ ├── models.py # 資料模型定義  
│ └── data_provider.py # 資料存取層  
│  
├── data/  
│ └── mock_data.json # 模擬爬蟲輸出資料  

## API 端點  

| 方法 | 路徑 | 說明 |
|------|------|------|
| GET | `/health` | API 狀態確認 |
| GET | `/items` | 取得貼文與留言 |
| GET | `/posts` | 取得貼文資料 |
| GET | `/posts/{post_id}/comments` | 取得指定貼文留言 |  

## 回傳資料格式

每筆資料包含以下欄位：  
{  
"type": "post 或 comment",  
"content": "內容",  
"time": "時間 (ISO 格式)",  
"author": "發文者或留言者"  
}

此設計可於未來直接替換為實際爬蟲或資料庫來源，  
而不需修改 API 介面。  

  
## 實作說明

由於 Facebook 平台存在資料存取限制，  
目前尚未完整實作實際爬蟲流程，  
但已完成 API 架構與資料層設計，  
可支援後續資料收錄模組整合。  
