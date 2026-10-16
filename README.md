# F1 Replay Timing - LazyCat App

[F1 Replay Timing](https://github.com/adn8naiagent/F1ReplayTiming)（F1 直播/回放计时可视化）的懒猫微服（LazyCat）打包。

## 模式

- **镜像模式（mirror）**：`ghcr.io/adn8naiagent/f1replaytiming` 镜像经 `ghcr.1ms.run` 加速器拉取，`require_digest_match: true` 校验镜像内容与上游一致。
- **自动跟随上游**：每日检查上游三段式 semver tag（`channel: stable`），发现新版本自动更新版本号与镜像、构建 LPK、发布商店。
- **喵喵商店发布**：仅私有商店（MiaoMiao private store），不发布官方商店。

## 设置向导参数（均可选）

| 参数 | 说明 |
| --- | --- |
| 访问口令 | 整站口令认证；留空不启用 |
| OpenRouter API Key | 启用截图同步（AI 从截图读时间塔） |

## 说明

- 单容器（Next.js 前端 + FastAPI 后端同端口），数据卷 `/lzcapp/var/f1timing:/data`
- 会话数据按需处理并本地缓存（2024 年起的练习/排位/正赛）
- 地图瓦片与 F1 SignalR 直播数据需公网访问
- 官方商店已有同作者旧版（`cloud.lazycat.app.f1replaytiming` 1.0.3），本包 `community.` 前缀更新到 2.1.3

## 所需 Secrets

| Secret | 说明 |
| --- | --- |
| `APPSTORE_URL` / `APPSTORE_TOKEN` | 喵喵商店 API 地址与发布令牌 |
| `APP_ID` | 可选 |
| `PRIVATE_STORE_GROUP_CODES` | 可选，私有分组码 |

## 许可

MIT（上游）
