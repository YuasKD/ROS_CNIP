# RouterOS CNIP List (Auto-Updated)

![License](https://img.shields.io/github/license/YuasKD/ROS_CNIP)
![Release](https://img.shields.io/github/v/release/YuasKD/ROS_CNIP?include_prereleases&label=Latest%20List)

本项目利用 GitHub Actions 每日自动拉取高精度的中国大陆 IP 地址列表，并将其转换为 RouterOS (ROS) 可直接导入的 `.rsc` 脚本文件。

## ✨ 特性

* **数据纯净**：上游数据源自 [Hackl0us/GeoIP2-CN](https://github.com/Hackl0us/GeoIP2-CN)，剔除了大量误标 IP，分流更精准。
* **格式优化**：自动生成 `.rsc` 脚本，包含 `remove` 旧列表指令，一键导入。
* **防误杀**：默认合并了**私有网段 (Private IP)** 和 **运营商级 NAT (CGNAT)**，防止内网或光猫后台无法访问。
    * `192.168.0.0/16`
    * `10.0.0.0/8`
    * `172.16.0.0/12`
    * `100.64.0.0/10` (ISP CGNAT)
* **全自动**：每天北京时间中午 12:00 自动更新并发布到 GitHub Release。

## 📥 下载链接

| 📦 项目 | 📄 文件名 | 🐙 GitHub Release | 🚀 国内加速 (推荐) | 🔧 适用范围 |
| :--- | :--- | :---: | :---: | :--- |
| **ROS CNIP** | `cnip.rsc` | [**点我下载**](https://github.com/YuasKD/ROS_CNIP/releases/download/cnip/cnip.rsc) | [**点我起飞**](https://cdn.jsdelivr.net/gh/YuasKD/ROS_CNIP@main/cnip.rsc) | RouterOS 导入专用 |

## 📥 如何使用

### 方式一：手动导入

1.  进入本项目的 [Releases 页面](../../releases/latest)。
2.  下载最新的 `cnip.rsc` 文件。
3.  将文件拖入 RouterOS 的 `Files` 窗口。
4.  在 Terminal 执行：`/import cnip.rsc`。

🤝 致谢
核心数据来源：Hackl0us/GeoIP2-CN - 感谢大佬提供的高质量 IP 库。

📄 License
本项目遵循 GPL-3.0 开源协议。
