# kev-mirror

CISA Known Exploited Vulnerabilities (KEV) Catalog 镜像仓库。

## 背景

- 官方源：`https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json`
- 本仓库由 GitHub Actions 每日自动同步（`.github/workflows/sync-kev.yml`），仅存放官方 KEV JSON 原样副本。
- 用途：供 OWASP dependency-check 的 `knownExploitedUrl` 指向本仓库 raw 文件，规避官方域（www.cisa.gov）对特定出口 IP 的 403 封禁。

## 文件

- `known_exploited_vulnerabilities.json`：CISA 官方 KEV Catalog 原样 JSON（每日同步）。

## 用法（dependency-check-maven）

```bash
mvn dependency-check:check \
  -DknownExploitedUrl="https://raw.githubusercontent.com/AceOnGames-TD/kev-mirror/main/known_exploited_vulnerabilities.json"
```

> 数据来源：CISA Known Exploited Vulnerabilities Catalog（美国国土安全部网络安全与基础设施安全局公开数据）。
