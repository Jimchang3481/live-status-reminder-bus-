# Bus+ 即時動態 (Live Updates for Bus+)

## 專案介紹

本專案是一個專為台灣公車 App Bus+ 量身打造的輔助工具。

透過 Android 系統原生的通知監聽架構，在裝置本機即時提取 Bus+ 的路線與到站倒數資訊，並呼叫 API ，將其升級為狀態列即時動態卡片。

## 運作原理

```
[ Bus+ App ] 
     │ (發布常駐通知)
     ▼
[ NotificationListenerService ] (純本機攔截)
     │
     ▼
[ 本機字串解析器 (Regex Parser) ] (提取公車路線、倒數時間、到站狀態)
     │
     ▼
[ Android 16 Live Updates API ] (OngoingActivityStatus)
     │
     ▼
[ 系統狀態列 ]
```


## 安裝與系統要求

作業系統：建議 Android 16 (API 36) 或以上版本。

依賴應用：請確保手機已安裝 Bus+ (hearsilent.busplus) 並開啟路線到站提醒通知。

必要權限：首次啟動請依引導授予「通知存取權限」。


## 致謝與開源授權

本專案基於 Jimmy Huang (jimmy90109) 之開源專案進行精簡、重構與專屬客製化開發。

本專案採用 MIT License 條款開放原始碼。
