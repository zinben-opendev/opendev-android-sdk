# OpenDev SDK — Android (prebuilt AAR)

**Documentation:** English (default) · [简体中文](README.zh-CN.md)

This repository contains **prebuilt AAR** artifacts for the **OpenDev SDK** (`androidTarget` in Kotlin Multiplatform). Use it when you consume the SDK from **GitHub** before **Maven Central** coordinates are available.

> **Brand:** Public name **OpenDev SDK**. References to **Walknote** are examples only.

## Technical stack (languages)

| Aspect | What this repo contains / uses |
|--------|--------------------------------|
| **SDK implementation (source, not in this repo)** | **Kotlin Multiplatform** `androidTarget` → **JVM bytecode** + Android packaging as **AAR**. |
| **Artifacts here** | **`opendev-sdk-release.aar`** (and optionally debug AAR) — no Java/Kotlin source tree. |
| **Typical consumer apps** | **Kotlin** or **Java** Android apps using Gradle `files(...)` / `flatDir` (or Maven coordinates when Central is enabled). |

## Contents

- `opendev-sdk-release.aar` — recommended for integration
- `CHECKSUMS.sha256` — integrity verification (`shasum -a 256 -c CHECKSUMS.sha256` or `sha256sum -c`)
- `sbom/` — resolved **Android release runtime** Maven coordinates (supply-chain transparency; not a full CycloneDX SBOM)
- `opendev-sdk-debug.aar` — present only if your maintainer published with `WALKNOTE_OPENDEV_DIST_INCLUDE_DEBUG_AAR=1` (omitted by default)

## Gradle (`files` dependency)

Check out or download the **same Git tag** you depend on (for example `v2.0.0`), then:

```kotlin
dependencies {
    implementation(files("libs/opendev-sdk-release.aar"))
}
```

You may also use `flatDir` or a composite build. For official Maven coordinates (`io.github.zinben-opendev:opendev-android-sdk`), follow the OpenDev publishing guide when Central is enabled.

## Integration notes

- Initialize the SDK with CDN / channel / environment configuration from your OpenDev project.
- Do not embed API secrets in source control; inject at build time or runtime via secure channels.

## Process

Staging and tags are described in the Walknote monorepo document **`Docs/01-SDK/SDK_GITHUB_BINARIES_DISTRIBUTION.md`** (maintainer-facing).

## Security

See [SECURITY.md](SECURITY.md).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

See [LICENSE](LICENSE).
