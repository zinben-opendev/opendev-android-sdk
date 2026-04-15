# OpenDev SDK — Android（AAR 分发）

本仓库为 **预构建 AAR**，由 Walknote 主仓 `:core` 产出，便于在 **未接 Maven Central** 时通过 GitHub 引用。

## 产物

- `opendev-sdk-release.aar` — 推荐集成
- `opendev-sdk-debug.aar` — 调试（可选）

## Gradle（本地 `files`）

将对应 tag 检出或下载后：

```kotlin
dependencies {
    implementation(files("libs/opendev-sdk-release.aar"))
}
```

或通过 `flatDir` / `composite build` 接入；**Maven 坐标**（`io.github.zinben-opendev:opendev-android-sdk`）见主仓文档，待 Central 发布后切换。

## 版本与标签

请使用与本仓库 **Git tag**（如 `v2.0.0`）一致的目录快照；主仓 staging 脚本与推送脚本会保持 `package.json` / tag 对齐策略见 `Docs/01-SDK/SDK_GITHUB_BINARIES_DISTRIBUTION.md`。
