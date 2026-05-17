# 貢獻指南

## 基本原則

- `translation/` 是專案輸出的單一來源；所有最終要打包的翻譯、補釘與覆蓋內容都應落在此處。
- `source/` 只追蹤翻譯相關文字來源，不放完整模組包、jar、圖片、音效或其他二進位內容。
- ParaTranz-managed 譯文以 ParaTranz 為準；本地 `paratranz/` 的 `translation` 欄位不作為人工修改入口。
- `config.toml`、`.modpack-meta/`、`source/`、`translation/`、`paratranz/` 與 `dist/` ignore 規則由 `modpack-toolkit init` 產生或更新。
- GitHub Actions、release 上傳與自動化流程不屬於模板的預設內容；若專案需要，請在個別專案中獨立設計。

## 翻譯與補釘變更

1. 先確認目前工作區乾淨，避免把不相關變更混入同一 PR。
2. 更新上游來源時執行：

```bash
modpack-toolkit fetch --latest
modpack-toolkit convert to-paratranz --clean
modpack-toolkit doctor
```

3. 從 ParaTranz 拉回譯文時執行：

```bash
modpack-toolkit sync download --convert
modpack-toolkit doctor
```

4. 建構發布檔前執行：

```bash
modpack-toolkit build all --keep-going
```

## Pull Request 檢查

- 說明變更目的與影響範圍。
- 標明對應的上游模組包版本或 artifact。
- 附上已執行的 `modpack-toolkit` 指令與結果摘要。
- 不提交 `dist/` 產物，除非該專案明確要求。
- 不提交 toolkit 不應管理的二進位來源檔。
