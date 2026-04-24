# ERP MBOM Windows 安装包版本差异

本说明用于记录 `ERP/PLM/MOM/` 目录下两个历史 Windows 安装包的差异，方便分发和回溯。

## 文件清单

| 版本 | 文件名 | 归档大小 | 打包时间 | SHA256 |
| --- | --- | ---: | --- | --- |
| P15 / 2026-04-22 | `ERP_MBOM_WPF_InstallerPackage_20260422_023222.zip` | 145.73 MB | 2026-04-22 02:32 | `8C665981DFD32DEDC54E38D97804632D917850B44413CAF878A0231E4E6C7B37` |
| P16 / 2026-04-23 | `ERP_MBOM_WPF_InstallerPackage_20260423_172809.zip` | 156.26 MB | 2026-04-23 17:28 | `D515D283E73DD69FA0CF5C939D4893E916055030428B123CDD107CE0728D1EED` |

## 主要差异

- P16 是 2026-04-23 重新打包发布的安装器归档，作为 P15 之后的更新版本。
- P16 归档比 P15 增加约 10.53 MB；内部 `ERP_MBOM_WPF_Installer.exe` 从 151.59 MB 增加到 162.13 MB。
- P16 归档内增加了一层时间戳目录：`ERP_MBOM_WPF_InstallerPackage_20260423_172809/`，便于解压后识别版本。
- 两个版本都包含 `ERP_MBOM_WPF_Installer.exe`、`Windows安装说明.html`、`Windows安装说明.md`。
- 两个版本的 Windows 安装说明文件内容和大小一致，安装方式没有变化。
- 两个版本安装器的 Windows 文件版本信息仍为 `ProductVersion 1.0.0`、`FileVersion 1.0.0.0`，实际区分请以文件名时间戳和 SHA256 为准。

## 安装和运行说明

- 推荐对外发送完整安装包归档，也就是 `ERP_MBOM_WPF_InstallerPackage_*.zip`。
- 解压后运行 `ERP_MBOM_WPF_Installer.exe`。
- 安装后程序使用 WPF 桌面壳加载内置 Flask 服务。
- 稳定访问端口为 `http://127.0.0.1:5058/`。
- P16 打包后已做本地冒烟验证：桌面程序可启动，`/` 和 `/api/health` 返回正常。

## 选择建议

- 新分发优先使用 P16：`ERP_MBOM_WPF_InstallerPackage_20260423_172809.zip`。
- 需要回退或对比历史环境时保留 P15：`ERP_MBOM_WPF_InstallerPackage_20260422_023222.zip`。
