# Desk Racer — Android (Capacitor)

Game web (Three.js + Rapier) dibungkus jadi app Android. Landscape terkunci, fullscreen, kontrol sentuh.

## Kontrol sentuh (landscape)
- Kiri bawah: LEFT / RIGHT (steer)
- Kanan bawah: ACCEL / BRAKE
- Tengah bawah: CAM (ganti kamera 1-4), MENU, SOUND
- Multi-touch: steer + gas bersamaan.

## Build APK
Butuh internet saat `npm run build`: model .glb diunduh dari gstatic lalu dibundel ke APK (offline setelah itu).

### Lokal (Node 20+, JDK 21, Android SDK)
```
npm install
npm run build
npm run android:add     # sekali saja
npx cap sync android
cd android && ./gradlew assembleDebug
```
APK: `android/app/build/outputs/apk/debug/app-debug.apk`

Atau `npm run android:open` lalu Run di Android Studio.

### Tanpa Android Studio
Push ke GitHub. Tab Actions → "Build Android APK" → Run workflow. Unduh artifact `desk-racer-debug-apk`.

## Web
`npm run dev` tetap jalan. Kontrol sentuh aktif otomatis di perangkat touch landscape.
