# MatchaProxy modification notice

MatchaProxy is an unofficial, independently branded derivative. It is not affiliated with,
sponsored by, or endorsed by SagerNet or the upstream maintainers.

This distribution was modified by `kahpoh19` on 2026-07-16 from these exact upstream
sources:

- Core tag `v1.13.14`, commit `25a600db24f7680ad9806ce5427bd0ab8afe1114`.
- Android client commit `aa686b2f1ac4ca9e888d4d068ce79ee1abd309fc`, which is the
  Android gitlink recorded by that core commit.

The Android changes are recorded in
`.github/patches/matchaproxy-android.patch` and include:

- Independent product name, package ID (`io.github.kahpoh19.matchaproxy`), APK prefix,
  deep-link scheme, notification/VPN labels, and privileged data names.
- Original matcha-cake launcher artwork and derived launcher, adaptive, round, store, and
  notification icon assets. The launcher artwork is scaled within the white canvas to
  provide balanced safe-area spacing under Android rounded-square masks. The approved
  high-resolution artwork is preserved under `.github/assets/`.
- A source-code link and update endpoint that point to this distribution.
- Device-ABI-aware update selection for split APK releases.
- Four ABI APKs (`arm64-v8a`, `armeabi-v7a`, `x86_64`, and `x86`) with no universal
  APK and no Android 5 legacy APK.

The software remains licensed under GPL-3.0-or-later, including the additional naming
condition in the upstream license files. Both upstream license files are included in the
complete corresponding source archive. No warranty is provided.
