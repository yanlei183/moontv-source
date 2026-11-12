# MoonTV Source / TVBox / 影视仓 配置

原始 MoonTV / LunaTV 配置保持不变；以下 TVBox / 影视仓 版本为独立文件，可按需导入。配置仅整理原仓库公开列出的接口，接口可用性及客户端兼容性请自行验证。

## TVBox / 影视仓 多仓入口

可先尝试导入统一多仓入口，客户端会从中列出不同分类仓库：

`https://raw.githubusercontent.com/yanlei183/moontv-source/feature/tvbox-yingshicang/tvbox-multi.json`

多仓入口使用 `urls` 列出各配置地址。不同 TVBox / 影视仓 分支对多仓入口的支持可能不同；如果客户端无法识别，请改为直接导入下方对应配置。

| 配置 | 用途 | Raw 地址 |
| --- | --- | --- |
| `tvbox.json` | 综合点播及直播 | https://raw.githubusercontent.com/yanlei183/moontv-source/feature/tvbox-yingshicang/tvbox.json |
| `tvbox-config.json` | `config.json` 的非成人点播源 | https://raw.githubusercontent.com/yanlei183/moontv-source/feature/tvbox-yingshicang/tvbox-config.json |
| `tvbox-films.json` | 综合电影、剧集、动漫点播源 | https://raw.githubusercontent.com/yanlei183/moontv-source/feature/tvbox-yingshicang/tvbox-films.json |
| `tvbox-movie.json` | 电影源 | https://raw.githubusercontent.com/yanlei183/moontv-source/feature/tvbox-yingshicang/tvbox-movie.json |
| `tvbox-tv.json` | 剧集源 | https://raw.githubusercontent.com/yanlei183/moontv-source/feature/tvbox-yingshicang/tvbox-tv.json |
| `tvbox-anime.json` | 动漫源 | https://raw.githubusercontent.com/yanlei183/moontv-source/feature/tvbox-yingshicang/tvbox-anime.json |
| `tvbox-live.json` | 直播 M3U 源 | https://raw.githubusercontent.com/yanlei183/moontv-source/feature/tvbox-yingshicang/tvbox-live.json |
| `tvbox-adults.json` | 成人分类源（請自行確認年齡及當地法規） | https://raw.githubusercontent.com/yanlei183/moontv-source/feature/tvbox-yingshicang/tvbox-adults.json |

## MoonTV / LunaTV 原始配置

原始配置文件保留，請按客戶端需求使用：

- [config.json](https://raw.githubusercontent.com/yanlei183/moontv-source/feature/tvbox-yingshicang/config.json)
- [config-films.json](https://raw.githubusercontent.com/yanlei183/moontv-source/feature/tvbox-yingshicang/config-films.json)
- [config-movie.json](https://raw.githubusercontent.com/yanlei183/moontv-source/feature/tvbox-yingshicang/config-movie.json)
- [config-tv.json](https://raw.githubusercontent.com/yanlei183/moontv-source/feature/tvbox-yingshicang/config-tv.json)
- [config-anime.json](https://raw.githubusercontent.com/yanlei183/moontv-source/feature/tvbox-yingshicang/config-anime.json)
- [config-live.json](https://raw.githubusercontent.com/yanlei183/moontv-source/feature/tvbox-yingshicang/config-live.json)
- [config-adults.json](https://raw.githubusercontent.com/yanlei183/moontv-source/feature/tvbox-yingshicang/config-adults.json)

## 使用注意

- 导入前请确认数据源合法且适用于你的地区，遵守版权法规。
- 成人分类仅面向成年人；请遵守当地法律法规。
- 本仓库不托管视频内容，仅整理公开配置接口；源的安全性、合法性和可用性由使用者自行判断。
