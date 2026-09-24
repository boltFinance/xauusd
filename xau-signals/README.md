# XAU Signals (XAUUSD live signals app)

## Get the APK (no Android Studio needed)
1. Create a free GitHub repo and upload all files in this folder (keep the .github folder).
2. Open the repo's **Actions** tab -> "Build APK" -> wait ~5 min.
3. Download the `xau-signals-apk` artifact, unzip, and install `app-debug.apk` on your phone
   (allow "install unknown apps").

## Or build locally
npm install && npx cap add android && npx cap sync android
cd android && ./gradlew assembleDebug
(APK: android/app/build/outputs/apk/debug/app-debug.apk)

## First run
Get a free key at twelvedata.com, open the app's Settings, paste it, and Save.
Free tier allows 800 requests/day, so the app refreshes every 2 minutes.

## Signal logic (5-min XAU/USD candles)
BUY: EMA9 crosses above EMA21 within last 3 candles, price above EMA50, RSI 50-70.
SELL: mirror image (RSI 30-50, price below EMA50).
SL = 1.5 x ATR(14); TP1 = 1R; TP2 = 2R. Otherwise WAIT.
Rule-based indicators only. Not predictions, not financial advice.
