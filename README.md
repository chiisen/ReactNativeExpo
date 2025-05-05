# ReactNativeExpo
依據 React Native + Expo(基於JS技術) 開發 Android App

---

# React Native (最佳JS方案)

- 優勢：使用JavaScript/TypeScript，熱重載加速開發
- 工具需求：Node.js + Android Studio
- 特點：豐富的UI元件庫，跨平台支援
- 快速開始指令：
```bash
# 初始化專案 (在PowerShell 7執行)
npx create-expo-app iching-app --template expo-template-blank-typescript
cd iching-app
```

# 安裝專案依賴套件
🔧 必要依賴安裝 (PowerShell 7 指令)：
```bash
# 1. 確保 Node.js 已安裝 (v18+)
node --version

# 2. 安裝 Expo CLI 全域工具
npm install -g expo-cli

# 3. 進入專案目錄安裝本地依賴
cd  iching-app
npm install
```
📦 檢查 package.json 核心依賴：
- 主要依賴已包含：
```json
"dependencies": {
  "expo": "~53.0.7",
  "react": "19.0.0",
  "react-native": "0.79.2"
}
```
- 🚀 執行專案指令：
```bash
# 開發模式 (會自動開啟瀏覽器介面)
npm start

# 或直接運行 Android 模擬器
npm run android
```

# 安裝 Android Studio
https://developer.android.com/studio?hl=zh-tw  

# 下載 Gradle
https://gradle.org/releases/?locale=zh_TW  

# 安裝 Java
https://github.com/ikatyang/emoji-cheat-sheet

# 設定環境變數 (PowerShell 7 指令)
```bash
code $profile
```
新增下面的環境變數：
```bash
# 臨時設定 (僅當前 session 有效)
$env:ANDROID_HOME = "C:\Users\你的使用者名稱\AppData\Local\Android\Sdk"
$env:PATH += ";$env:ANDROID_HOME\emulator;$env:ANDROID_HOME\platform-tools"

# 將 ANDROID_SDK_ROOT 路徑加入 PATH
$env:ANDROID_SDK_ROOT = "C:\Users\$env:USERNAME\AppData\Local\Android\Sdk"
$env:PATH += ";$env:ANDROID_SDK_ROOT"

# 將 JAVA_HOME 路徑加入 PATH
$env:JAVA_HOME = "C:\Program Files\Java\jdk-24\bin"
$env:PATH += ";$env:JAVA_HOME"

# 將 Gradle 路徑加入 PATH
$env:Path += ";C:\gradle-8.14-bin\gradle-8.14\bin"
```

# 檢查 adb
```bash
# 檢查 ADB 裝置列表
adb devices

# 重啟 ADB 服務
adb kill-server
adb start-server
```

# 1. 檢查環境變數設定
```bash
# 確認 Java 路徑
$env:JAVA_HOME

# 確認 Android SDK 路徑
$env:ANDROID_SDK_ROOT
```
# 2. 測試基本指令
```bash
# 檢查 adb 是否可用
adb version

# 檢查 gradle 版本
gradle --version
```
# 3. 啟動模擬器測試
```bash
# 列出可用 AVD 裝置
emulator -list-avds

# 啟動模擬器 (替換 Your_AVD_Name 為實際名稱)
emulator -avd Your_AVD_Name -writable-system
```
# 4. 建立測試專案

1. 在 Android Studio 中選擇 "New Project" → "Empty Activity"
2. 點擊 Run 'app' 按鈕 (綠色箭頭)
3. 選擇已啟動的模擬器或實體裝置
常見問題排查：

- 若出現 adb server version doesn't match 錯誤，執行：
```bash
adb kill-server
adb start-server
```
# 5. 重新啟動 PowerShell 後測試
```bash
emulator -list-avds
```