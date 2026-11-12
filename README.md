# MoonTV Source (影視源配置庫)

本倉庫專門為 MoonTV / LunaTV、TVBox 及 影视仓等兼容客戶端提供配置數據源。
為減少一次載入過多資源造成的檢索負擔，原始版本採用分類專用配置檔；另外新增了可直接導入的 TVBox / 影视仓 兼容版配置文件，方便直接使用。

## 📂 目前文件結構

| 文件名 | 說明 | 建議用途 |
| --- | --- | --- |
| `config.json` | 綜合通用配置（可選） | 一般使用 |
| `config-films.json` | 電影 + 劇集 + 直播頻道 | 影音綜合 |
| `config-anime.json` | 動漫專用 | 動漫用戶 |
| `config-movie.json` | 電影專用 | 只看電影 |
| `config-tv.json` | 劇集專用 | 追劇用戶 |
| `config-live.json` | 直播頻道專用（IPTV） | 電視直播 |
| `config-adults.json` | 成人內容專用（獨立分離） | 成人模式 |
| `tvbox.json` | TVBox / 影视仓 直接使用配置 | 直接導入 |

> 每個分類檔案約控制在 30~50 個有效源，避免過度檢索。

## 🚀 使用方法

### 1. 取得 Raw 連結

GitHub Raw 格式：

```bash
https://raw.githubusercontent.com/yanlei183/moontv-source/main/檔案名
```

常用範例：
- MoonTV / LunaTV：`https://raw.githubusercontent.com/yanlei183/moontv-source/main/config-films.json`
- TVBox / 影视仓：`https://raw.githubusercontent.com/yanlei183/moontv-source/main/tvbox.json`
- 直播：`https://raw.githubusercontent.com/yanlei183/moontv-source/main/config-live.json`
- 成人專用：`https://raw.githubusercontent.com/yanlei183/moontv-source/main/config-adults.json`

### 2. 在 MoonTV / LunaTV 中配置

1. 打開客戶端 → 設置 (Settings) → 配置源 (Source)
2. 將對應的 Raw 連結貼到「配置地址」
3. 點擊確認 / 更新配置

### 3. 在 TVBox / 影视仓 中使用

1. 打開 TVBox / 影视仓
2. 導入配置地址：
   `https://raw.githubusercontent.com/yanlei183/moontv-source/main/tvbox.json`
3. 等待配置同步即可使用

### 4. 國內加速（推薦）

如果 GitHub Raw 存取較慢，可使用 jsDelivr：

```bash
https://cdn.jsdelivr.net/gh/yanlei183/moontv-source@main/tvbox.json
```

### 5. Docker 掛載範例（可選）

```bash
docker run -d \
  --name moontv \
  -v $(pwd)/moontv-source:/app/config \
  -p 3000:3000 \
  ghcr.io/senshinya/moontv:latest
```

## 🧩 影视仓兼容版說明

`tvbox.json` 是為 TVBox / 影视仓 專門生成的直接導入配置，使用的是通用 `sites` 配置格式：

```json
{
  "sites": [
    {
      "key": "guangsu",
      "name": "光速资源",
      "api": "https://api.guangsuapi.com/api.php/provide/vod",
      "type": 1,
      "searchable": 1,
      "quickSearch": 1,
      "filterable": 1
    }
  ],
  "lives": [
    {
      "name": "IPTV-Org 全球",
      "url": "https://iptv-org.github.io/iptv/index.m3u"
    }
  ]
}
```

這種格式可以直接被多數 TVBox / 影视仓 客戶端導入。

## 🤝 歡迎貢獻！一起維護更好的資源庫

本倉庫採開放維護方式，歡迎大家一起更新內容。
無論是回報失效源、推薦新源，或直接提交 Pull Request，都非常感謝。

### 貢獻方式

1. 回報失效源
   - 直接開 Issue，標題建議寫：`[失效] 檔案名 - 源名稱`
   - 請附上失效的 api 地址，方便快速確認。

2. 推薦新源
   - 開 Issue 或直接提 PR
   - 須符合以下條件：
     - 免費可直接使用
     - 接口格式為 Apple CMS V10（`/api.php/provide/vod`）
     - 非成人內容請勿提交到 `config-adults.json` 以外的檔案
     - 請提供可驗證的 api 地址與簡單說明

3. 直接提交 Pull Request
   - Fork 本倉庫 → 修改對應分類檔案 → 提交 PR
   - 請盡量保持每個分類檔案源數量在 30~50 個之間
   - 新增源時建議放在檔案後方（作為備用）
   - 提交前請先簡單測試源是否可用

### 貢獻注意事項

- 成人內容只能提交到 `config-adults.json`
- 請勿提交需要密碼、付費或有明顯廣告劫持的源
- 直播源請優先使用更新積極的公共倉庫（如 iptv-org、fanmingming 等）
- 提交時請簡單說明修改內容，方便審核

感謝每一位幫忙維護的貢獻者！讓我們一起把這個資源庫維護得更好。

## 🛠️ 維護說明

- 所有配置均為公開免費源，定期更新與清理失效接口。
- 成人內容已完全獨立至 `config-adults.json`，與其他檔案分離。
- 更新後請手動在客戶端點擊「更新配置」或重啟應用以刷新緩存。
- TVBox / 影视仓 可直接使用 `tvbox.json`，不需要再額外轉碼。

## ⚠️ 免責聲明

1. 本倉庫僅供學習與技術交流使用，不存儲任何視頻內容。
2. 所有接口數據均來自互聯網公開資源，版權歸原權利人所有。
3. 請遵守當地法律法規，勿用於商業用途。
4. 使用本配置產生的任何後果由使用者自行承擔。
5. 如有侵權內容，請提交 Issue，我們會盡快處理。

---

維護者：[@yanlei183](https://github.com/yanlei183)
最後更新：2026-11-12
