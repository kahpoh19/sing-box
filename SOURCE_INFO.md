# MatchaProxy 1.13.14-matchaproxy.2 source and build information

The release APKs correspond exactly to:

- Core: `SagerNet/sing-box` commit
  `25a600db24f7680ad9806ce5427bd0ab8afe1114` (tag `v1.13.14`).
- Android client: `SagerNet/sing-box-for-android` commit
  `aa686b2f1ac4ca9e888d4d068ce79ee1abd309fc`.
- Modifications: `.github/patches/matchaproxy-android.patch` in this repository.
- Approved icon source and launcher master: `.github/assets/` in this repository.
- Build recipe: `.github/workflows/android-apk.yml` in this repository.

The attached release archive `MatchaProxy-1.13.14-matchaproxy.2-source.tar.gz` contains
the complete upstream core tree, the complete Android tree with the MatchaProxy patch
already applied, the unmodified patch file, both icon source files, this notice, the
modification notice, and the exact GitHub Actions workflow used for the binaries.

## Rebuilding

The reproducible build recipe is the GitHub Actions workflow. It pins Go 1.25.11,
Java 17, Android NDK r28, both source commits, the product version, and Android
`versionCode`. It builds only `:app:assembleOtherRelease`, then verifies four split APKs
with `apksigner`.

To sign a rebuild, supply your own Android keystore and Gradle properties. The workflow
expects the keystore as the `ANDROID_KEYSTORE_BASE64` Actions secret and a base64-encoded
Java properties file as `LOCAL_PROPERTIES` containing `KEYSTORE_PASS`, `ALIAS_NAME`, and
`ALIAS_PASS`. Private signing keys and passwords are intentionally not part of
Corresponding Source. A rebuild signed with another key will have different APK bytes,
but is built from the same source and recipe.

The pinned upstream Android commit itself tracks an `app/release.keystore` file. The
source archive preserves that upstream file and verifies it byte-for-byte against the
pinned commit; it is not the private keystore used to sign the MatchaProxy release APKs.

The release also includes `SHA256SUMS` for all four APKs, updater metadata, and the source
archive.
