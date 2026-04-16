# OpenDev SDK — Android（预构建 AAR）

**文档语言：** 默认以英文 [`README.md`](README.md) 为准；本页为简体中文补充。

本仓库提供 **OpenDev SDK**（Kotlin Multiplatform `androidTarget`）的 **预构建 AAR**，用于在 **Maven Central** 坐标尚未启用时，通过 **GitHub** 引用。

> **品牌：** 对外产品名为 **OpenDev SDK**。文中 **Walknote** 仅作示例说明。

## 技术栈与语言

| 方面 | 说明 |
|------|------|
| **SDK 源码实现**（不在本仓） | **Kotlin Multiplatform** `androidTarget`，产出 **JVM 字节码** 并打 **AAR**。 |
| **本仓产物** | **`opendev-sdk-release.aar`** 等预编译包，**无** Java/Kotlin 源码树。 |
| **集成方应用** | 多为 **Kotlin** 或 **Java** 的 Android 工程（Gradle `files` / `flatDir` 等）。 |

## 产物

- `opendev-sdk-release.aar` — 推荐集成
- `CHECKSUMS.sha256` — 完整性校验
- `sbom/` — Android release runtime 解析后的 Maven 坐标（非完整 CycloneDX）
- `opendev-sdk-debug.aar` — 仅当发版方显式启用 `WALKNOTE_OPENDEV_DIST_INCLUDE_DEBUG_AAR=1` 时存在（默认通常不含）

## Gradle（`files`）

检出或下载与依赖一致的 **Git tag**（例如 `v2.0.0`）后：

```kotlin
dependencies {
    implementation(files("libs/opendev-sdk-release.aar"))
}
```

亦可使用 `flatDir` 或 composite build。官方 Maven 坐标见 OpenDev 发布文档（Central 就绪后）。

## 集成注意

- 使用你们 OpenDev 项目的 CDN / channel / environment 参数初始化 SDK。
- 勿在源码仓库硬编码密钥；通过构建期或安全通道注入。

## 流程说明

维护者发版流程见 Walknote 主仓 **`Docs/01-SDK/SDK_GITHUB_BINARIES_DISTRIBUTION.md`**。

## 许可证

见 [LICENSE](LICENSE)。
