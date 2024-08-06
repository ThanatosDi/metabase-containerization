# metabase
建立 Metabase BI 的 docker compose 環境

Metabase 是一款 Business Intelligence (BI) 工具，透過友善的使用者體驗和整合工具進行快速分析，讓您的公司能夠自行探索數據。

![](https://www.metabase.com/images/home/homepage_video.gif)

# 部署

1. 複製 .env
    ```bash
    cp .env.example .env
    ```
2. 修改 .env 中內容
   1. 設定 `POSTGRES_PASSWORD`
   2. 設定 UID 和 GID 為 Host 的 ID
   3. 設定 Cloudflare TUNNEL_TOKEN
3. 執行 `docker-compose up -d` 啟動服務

> [!NOTE]  
> 請注意，預設所有服務都不會映射 port 到 Host 上。如需映射，請在 .env 中修改 `PORT` 為自己想要的 port  
> Metabase 的服務僅會透過 Cloudflare TUNNEL 來進行訪問  
> Metabase 預設 port 為 `3000`  
> Postgres 預設 port 為 `5432`

# 其他資訊

### 轉移主機
如需要轉移架設主機連帶 portgres 資料夾也需要一同轉移至新主機上，因 Metabase 的所有儀表板或提問都保存於 portgres 中