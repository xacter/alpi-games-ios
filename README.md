# aLpi Games iOS

aLpi oyunlarının iOS imzalama ve App Store Connect yükleme hattı. Depoda oyun kaynağı yoktur.

1. Xcode projesi sunucuda Unity (Linux, iOS modülü) ile üretilir.
2. `ios-xcode.tar.gz` olarak `<oyun>-<sürüm>-<build>` etiketli bir sürüme eklenir.
3. `ios-sign.yml` macOS'ta arşivler, App Store Connect API anahtarıyla otomatik imzalar, IPA'yı artifact yapar ve
   istenirse TestFlight'a yükler.

```
gh workflow run ios-sign.yml -R xacter/alpi-games-ios -f release_tag=feedingtime-1.0.0-1 -f upload=false
```

Gerekli sırlar: `APPLE_TEAM_ID`, `ASC_KEY_ID`, `ASC_ISSUER_ID`, `ASC_KEY_P8`.
