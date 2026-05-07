# AI-Xray Free

跨境电商免费加速器，基于 Cloudflare，零成本，5分钟部署。[AI-Xray](https://github.com/ScientificInternet/AI-Xray) 免费版。

Free cross-border e-commerce accelerator powered by Cloudflare. Zero cost, 5-min deploy. Free tier of [AI-Xray](https://github.com/ScientificInternet/AI-Xray).

---

## 免费版 vs 专业版

| | 免费版（本项目） | 专业版（[AI-Xray](https://github.com/ScientificInternet/AI-Xray)） |
|---|---|---|
| 成本 | 零 | VPS $5-20/月 |
| 节点 | Cloudflare 共享 | 独享带宽 |
| 速度 | 够用，偶尔波动 | 稳定快速 |
| 协议 | VLESS | VLESS + Reality + Vision |
| 部署时间 | 5分钟 | 3-5分钟 |
| 适合 | 轻度使用，先试试看 | 日常工作，稳定需求 |

轻度使用选免费版。每天要用的选[专业版](https://github.com/ScientificInternet/AI-Xray)。

---

## 部署教程

两种方式，选一个。

### 方式一：CF Pages 部署（推荐）

适合不懂技术的人。全程点点点，不用写代码。

**第一步：Fork 本仓库**

点击本页面右上角的 **Fork** 按钮，将仓库复制到你的 GitHub 账号下。

**第二步：部署到 Cloudflare Pages**

1. 打开 [Cloudflare Dashboard](https://dash.cloudflare.com)，注册或登录
2. 左侧菜单选 **Workers & Pages**，点 **创建**，选 **Pages**，选 **连接到 Git**
3. 授权 GitHub，选择你刚 fork 的 **AI-Xray-Free** 仓库
4. 点 **开始设置**，什么都不用改，直接点 **保存并部署**
5. 等1-2分钟部署完成

**第三步：设置管理员密码**

1. 部署完成后，进入项目，**设置**，**环境变量**
2. 点 **添加变量**：
   - 变量名：`ADMIN`
   - 值：你的管理员密码（随便设一个，记住就行）
3. 点 **保存**

**第四步：绑定 KV 存储**

1. **设置**，**绑定**，**添加**，**KV 命名空间**
2. 变量名填 `KV`，选择一个命名空间（没有就新建一个）
3. 点 **保存**，然后重新部署一次

**第五步：访问后台**

打开 `https://你的项目名.pages.dev/admin`，输入管理员密码登录。

在后台可以：查看节点信息、获取订阅链接、修改配置。

---

### 方式二：CF Workers 部署

适合有一点技术基础的人。

1. 打开 [Cloudflare Dashboard](https://dash.cloudflare.com)
2. **Workers & Pages**，**创建**，**Worker**
3. 给 Worker 取个名字，点 **部署**
4. 点 **编辑代码**，把本仓库 `_worker.js` 的内容全部粘贴进去，点 **保存并部署**
5. **设置**，**变量**，添加 `ADMIN` = 你的密码
6. **设置**，**绑定**，添加 KV 命名空间，变量名 `KV`
7. 重新部署，访问 `https://你的worker名.workers.dev/admin`

---

## 客户端配置

拿到节点信息后，用以下客户端连接：

| 平台 | 推荐客户端 | 教程 |
|------|-----------|------|
| iPhone / iPad | Shadowrocket | [入门教程](https://ssr.dedyn.io/ios/shadowrocket/) |
| Android | V2RayNG | [入门教程](https://ssr.dedyn.io/android/v2rayng/) |
| Windows | V2RayN | [入门教程](https://ssr.dedyn.io/windows/v2rayn/) |
| macOS | ClashX Meta | [入门教程](https://ssr.dedyn.io/macos/clashx-meta/) |

更多客户端教程：[ssr.dedyn.io](https://ssr.dedyn.io)

---

## 速度不够？

免费版使用 Cloudflare 共享节点，速度取决于运营商和时段。

如果你需要稳定高速连接（日常办公、广告投放、直播），建议升级到 **AI-Xray 专业版**：

```bash
bash <(curl -fsSL https://raw.githubusercontent.com/ScientificInternet/AI-Xray/v1.3.0/install.sh)
```

一行命令，3-5分钟装好，独享VPS带宽。详情：[AI-Xray](https://github.com/ScientificInternet/AI-Xray)

**推荐 VPS：**

| 商家 | 线路 | 价格 | 适合 |
|------|------|------|------|
| [搬瓦工](https://bwh81.net/aff.php?aff=20308) | CN2 GIA | $49.99/年 | 电信用户 |
| [DMIT](https://www.dmit.io/aff.php?aff=3138) | CMI | $6.9/月 | 移动用户 |
| [Vultr](https://www.vultr.com/?ref=9631926-9J) | 全球节点 | $5/月 | 新手试水，送$300 |

---

## 常见问题

**Q：部署完了打不开后台？**

检查是否设置了 ADMIN 环境变量，是否绑定了 KV 命名空间。两个都设好后需要重新部署一次。

**Q：节点连不上？**

免费版偶尔会被运营商干扰。换个时间试，或者升级到[专业版](https://github.com/ScientificInternet/AI-Xray)。

**Q：速度慢？**

正常。免费版是共享节点。日常办公需求建议用专业版。

**Q：安全吗？**

代码完全开源，你部署在自己的 Cloudflare 账号下，数据只经过 Cloudflare 和你自己的节点。

---

## 致谢

核心代码基于 [edgetunnel](https://github.com/cmliu/edgetunnel)（GPL v2），感谢 [cmliu](https://github.com/cmliu) 和所有贡献者。详见 [NOTICE.md](NOTICE.md)。

---

## 相关项目

- [AI-Xray](https://github.com/ScientificInternet/AI-Xray) - 专业版，VPS + VLESS Reality，一行命令安装
- [ssr.dedyn.io](https://ssr.dedyn.io) - 客户端入门教程，22个客户端全覆盖

---

## 法律提示

本项目定位为跨境电商网络加速器，用于合法的跨境商业活动。用户应遵守所在地区的法律法规。
