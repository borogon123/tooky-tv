# 📺 Тооку ТВ — Android приложение

Приложение для просмотра канала Тооку-тв на Android TV и обычных Android телевизорах.

---

## 🚀 Как собрать APK (бесплатно, онлайн)

### Способ 1: Через сайт Appetize / BuildStore (проще всего)

1. Идите на сайт: **https://www.apkonline.net/compile-android-app**
   или используйте **Android Studio** на компьютере

### Способ 2: Android Studio (рекомендуется)

1. Скачайте и установите **Android Studio**: https://developer.android.com/studio
2. Откройте папку `TookyTV` как проект
3. Нажмите **Build → Build APK(s)**
4. APK файл будет в папке: `app/build/outputs/apk/debug/`

### Способ 3: GitHub Actions (бесплатно, онлайн)

1. Создайте бесплатный аккаунт на **github.com**
2. Создайте новый репозиторий и загрузите все файлы из папки `TookyTV`
3. Создайте файл `.github/workflows/build.yml`:

```yaml
name: Build APK
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-java@v3
        with:
          java-version: '17'
          distribution: 'temurin'
      - name: Build APK
        run: ./gradlew assembleDebug
      - uses: actions/upload-artifact@v3
        with:
          name: TookyTV.apk
          path: app/build/outputs/apk/debug/app-debug.apk
```

4. После загрузки файлов GitHub автоматически соберёт APK
5. Скачайте APK во вкладке **Actions → Build APK → Artifacts**

---

## 📱 Установка на Android TV

1. На телевизоре включите **"Разрешить установку из неизвестных источников"**
   (Настройки → Безопасность → Неизвестные источники)
2. Скопируйте APK на USB флешку
3. Установите через файловый менеджер

---

## ✅ Совместимость

- ✅ Android TV (все производители: Sony, Philips, Hisense и др.)
- ✅ Android TV приставки (Xiaomi Mi Box, NVIDIA Shield и др.)
- ✅ Телефоны и планшеты Android 5.0+
- ⚠️ LG TV (webOS) — требует отдельная разработка

---

## ⚙️ Технические детали

- Минимальная версия Android: 5.0 (API 21)
- Целевая версия: Android 14 (API 34)
- Ориентация: альбомная (для TV)
- Автоматический полноэкранный режим
