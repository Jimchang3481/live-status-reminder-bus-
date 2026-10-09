# Bus+ 即時動態 (Live Updates for Bus+)

## 專案介紹

本專案是一個專為台灣熱門公車 App Bus+ 量身打造的輔助工具。

透過 Android 系統原生的通知監聽架構，在裝置本機即時提取 Bus+ 的路線與到站倒數資訊，並呼叫 Android 16 (API 36) 底層的原生 API，將其升級為狀態列動態膠囊與鎖定螢幕即時動態卡片。

## 特色

Android 16 原生即時動態：無縫串接系統級 Live Updates，公車到站資訊直接常駐於狀態列膠囊與鎖定螢幕。

狀態列膠囊精簡顯示：在「即將進站 / 將到站」關鍵時刻自動精簡文字長度，保證不遮擋狀態列其他系統圖示。

通知快捷跳轉：下拉通知卡片提供「返回 Bus+」快捷動作按鈕，一鍵返回母 App 檢視即時地圖與站點。

純本機端運作：本專案完全不要求 INTERNET 網路權限。

所有通知解析與文字處理 100% 於手機裝置端完成，不收集、不上傳任何個人隱私與通知資訊。



## 運作原理

[ Bus+ App ] 
     │ (發布常駐通知)
     ▼
[ NotificationListenerService ] (純本機即時攔截)
     │
     ▼
[ 本機字串解析器 (Regex Parser) ] (提取公車路線、倒數時間、到站狀態)
     │
     ▼
[ Android 16 Live Updates API ] (OngoingActivityStatus)
     │
     ▼
[ 系統狀態列膠囊 & 鎖定螢幕卡片 ]


## 安裝與系統要求

作業系統：建議 Android 16 (API 36) 或以上版本（支援原生 Live Updates 機型）。

依賴應用：請確保手機已安裝 Bus+ (hearsilent.busplus) 並開啟路線到站提醒通知。

必要權限：首次啟動請依引導授予「通知存取權限 (Notification Listener Permission)」。


## 致謝與開源授權

本專案基於 Jimmy Huang (jimmy90109) 之開源專案進行精簡、重構與專屬客製化開發。

本專案採用 MIT License 條款開放原始碼。
