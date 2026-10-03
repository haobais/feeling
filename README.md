# Feeling Remote Metadata

这个仓库只用于维护 Feeling 的远程更新信息和赞助用户记录。

仓库边界：

- 不存放源码、反编译文件、构建目录或开发环境配置。
- 不直接提交 APK、日志、设备信息或任何敏感凭据。
- 更新包应通过 GitHub Release 的附件发布，`updates/manifest.json` 只记录可验证的发布元数据。
- 赞助用户只有在获得公开展示许可后，才可以写入 `sponsors/sponsors.json`。

## 目录

- `updates/manifest.json`：更新器读取的稳定版更新清单；发布后可通过
  `https://raw.githubusercontent.com/haobais/feeling/main/updates/manifest.json`
  读取。
- `sponsors/sponsors.json`：经授权公开展示的赞助记录。
- `.github/workflows/validate.yml`：只校验 JSON 和仓库边界，不执行源码构建。

## 更新流程

1. 在 GitHub Release 上传正式 APK，并记录 SHA-256。
2. 更新 `updates/manifest.json` 中的版本、下载地址和校验值。
3. 提交变更后再发布远程更新。

这里的“更新清单（manifest）”是给客户端读取的结构化版本描述，不包含模块实现代码。
