# {Modpack Template}

[![Version][version_badge]][version_link]
[![Download][download_total]][version_link]
[![License][license_badge]][license]
[![Discord][discord_badge]][discord]

{Modpack Template} 中文化補丁與模組翻譯專案。模組包譯名：{模組包譯名}。

## 簡介

此倉庫由 `Modpack-Template` 建立，只保留人類維護的專案入口文件、授權、貢獻說明與 issue templates。

翻譯來源、ParaTranz cache、建構設定、上游 artifact 狀態與輸出目錄由 `modpack-toolkit init` 產生與檢查，不應直接放在模板倉庫中。

## 初始化

建立新專案後，先替換 README 中的 `{Modpack Template}`、`{ModpackTemplate}`、`{模組包譯名}` 等占位文字，再執行：

```bash
modpack-toolkit init
modpack-toolkit doctor
```

`init` 會建立 toolkit 管理的骨架，例如：

- `config.toml`
- `.modpack-meta/`
- `source/`
- `translation/`
- `paratranz/`
- `dist/` 的 ignore 規則

接著依專案需要編輯 `config.toml`，再執行 fetch / convert / sync / build 流程。

## 常用流程

```bash
modpack-toolkit fetch --latest
modpack-toolkit convert to-paratranz --clean
modpack-toolkit doctor
```

拉回 ParaTranz 譯文並建構：

```bash
modpack-toolkit sync download --convert
modpack-toolkit build all --keep-going
```

## 下載

請前往 [發布頁面][version_link] 下載最新版本的中文化補丁。

## 貢獻

請參閱 [CONTRIBUTING.md](CONTRIBUTING.md)。翻譯相關內容以 ParaTranz 為譯文來源，原文與 toolkit 狀態以 git 中的 `source/`、`paratranz/`、`.modpack-meta/` 為準。

## 授權許可

本著作係採用 [創用 CC 姓名標示-非商業性-禁止改作 4.0 國際 授權條款][license]（[正體中文]）授權。

<!-- Badges -->
[version_badge]: https://img.shields.io/github/v/release/TeamKugimiya/{ModpackTemplate}?include_prereleases
[version_link]: https://github.com/TeamKugimiya/{ModpackTemplate}/releases/latest
[download_total]: https://img.shields.io/github/downloads/TeamKugimiya/{ModpackTemplate}/total
[license_badge]: https://img.shields.io/badge/License-CC%20BY--NC--ND%204.0-orange
[discord_badge]: https://img.shields.io/discord/947630690315411476?logo=discord

<!-- Links -->
[discord]: https://discord.gg/7BbPMtygHU
[正體中文]: https://creativecommons.org/licenses/by-nc-nd/4.0/deed.zh_TW
[license]: LICENSE
