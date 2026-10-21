# KloseDL-v2-notes

Klose Downloader v2 的**内置笔记发布仓库**。

⚠ 这里只放 Release 资产，**不存笔记源文件**。笔记源在应用仓库 [Klose2/KloseDL](https://github.com/Klose2/KloseDL) 的 `notes/` 目录。

## 每个版本的 Release 固定两个资产

| 资产 | 内容 |
|---|---|
| `builtin-notes.json` | 全部笔记的清单（`name` / `category` / `content`） |
| `notes-version.json` | 版本号，例如 `{"version":"0.0.1"}` |

客户端读的是固定地址，`latest` 永远指向最新 Release：

```
https://github.com/Klose2/KloseDL-v2-notes/releases/latest/download/builtin-notes.json
https://github.com/Klose2/KloseDL-v2-notes/releases/latest/download/notes-version.json
```

## 发版

在应用仓库（`Klose-downloader`）执行：

```bash
node publish-notes.js          # 补丁号 +1（0.0.1 → 0.0.2）
node publish-notes.js 0.1.0    # 指定版本
```

脚本会自动打包、建 Release、上传两个资产；本仓库不需要任何提交。
