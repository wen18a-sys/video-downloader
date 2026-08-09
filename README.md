# 清夜视频下载助手

软件发行存档仓库（版本记录 + 首发时间证明）。

## 版本信息

| 项目 | 内容 |
|------|------|
| 软件名称 | 清夜视频下载助手 |
| 当前版本 | v3.2.0 |
| 首发日期 | 2026-08-09 |
| 作者 | 清夜无眠 |
| 官网 | https://downvid.cn |
| 授权方式 | 服务器授权验证（19.90 元永久授权） |

## 用途说明

本仓库用于：

1. **发行时间证明**：通过 GitHub commit 与 Release 的时间戳，记录本软件各版本
   的首次发布时间，避免版权争议。
2. **版本存档**：正式安装包通过 GitHub Release 提供下载备份。

## 版本历史

- **v3.2.0**（2026-08-09 首发）：新增客户端自动更新检查；修复下载 .exe 文件
  被误命名为 .mp4 的问题。
- **v3.1.0**（2026-08-06 首发）：支持 YouTube、Bilibili、优酷、抖音等 100+ 平台；
  支持 4K/8K 高清视频下载；浏览器扩展一键发送链接；服务器授权验证。

## 说明

- 安装包下载：见本仓库 Releases 页面
- 开源许可与对应源码：见 https://github.com/wen18a-sys/licenses
- 版权所有 © 2026 清夜无眠

---

## 如何发布新版本（操作指引）

> 供维护者使用。新版本打包完成后，按以下步骤存档并产生新的时间证明。

### 前提

- 本机已安装 GitHub CLI（`gh`）并登录：`gh auth login`
- 新安装包已生成（如 `清夜视频下载助手_Setup_v3.3.0.exe`）

### 步骤

**1. 更新本文件（README.md）版本信息**

```markdown
| 当前版本 | v3.3.0 |
| 首发日期 | 2026-xx-xx |

## 版本历史
- **v3.3.0**（2026-xx-xx 首发）：<更新内容说明>
```

**2. 提交并推送（产生 git 时间戳证明）**

```bash
cd D:/download/video-downloader-release
git add README.md
git commit -m "v3.3.0 首发存档：清夜视频下载助手（2026-xx-xx）"
git -c http.proxy= -c https.proxy= push origin master
```

> 注：`-c http.proxy=` 用于绕过本机 git 全局代理（21882），如代理未运行会推送失败。

**3. 创建 Release 并上传安装包**

```bash
gh release create v3.3.0 "D:/server/static/清夜视频下载助手_Setup_v3.3.0.exe" \
  --repo wen18a-sys/video-downloader \
  --title "v3.3.0 首发安装包" \
  --notes "清夜视频下载助手 v3.3.0 正式安装包（2026-xx-xx 首发）
官网: https://downvid.cn
版本记录: 见仓库 README"
```

上传完成后 Release 自动带时间戳，与 git commit 形成双重首发证明。

**4. 验证**

```bash
gh release view v3.3.0 --repo wen18a-sys/video-downloader
# 确认 draft: false 且 asset 已上传
```

### 版权争议时的取证材料

1. 本仓库链接：`https://github.com/wen18a-sys/video-downloader`
2. 首发 commit 哈希：`git log --format=%H -1`
3. Release 链接：`https://github.com/wen18a-sys/video-downloader/releases/tag/v3.3.0`
