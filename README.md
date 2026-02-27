# 📱 ReactNativeExpo 🚀

這是一個基於 **React Native + Expo** (JavaScript/TypeScript 技術棧) 的 Android App 開發指南。本文件將帶領你從零開始完成環境配置與專案啟動。✨

---

## 🌈 React Native - 為跨平台而生 (最佳 JS 方案) 💡

*   **優勢**：使用熟悉的 JavaScript/TypeScript，支援**熱重載 (Hot Reloading)**，徹底加速開發週期！⚡
*   **工具需求**：Node.js + Android Studio 🛠️
*   **特點**：擁有極其豐富的 UI 元件庫與龐大的社群支援，實現真正的跨平台開發。🌐

### 🚀 快速開始 (Quick Start)

在 **PowerShell 7** 中執行以下指令來初始化你的專案：

```bash
# 初始化專案
npx create-expo-app iching-app --template expo-template-blank-typescript
cd iching-app
```

---

## 🛠️ 安裝專案依賴 (Dependencies)

### 🔧 必要環境安裝 (PowerShell 7 指令)：

1.  **確保 Node.js 已安裝 (建議 v18+)** 🟢
    ```bash
    node --version
    ```
2.  **安裝 Expo CLI 全域工具** 🌍
    ```bash
    npm install -g expo-cli
    ```
3.  **進入專案目錄並安裝本地依賴** 📦
    ```bash
    cd iching-app
    npm install
    ```

### 📦 核心依賴檢查 (`package.json`)：

專案初始化後，請確認包含以下核心套件：

```json
"dependencies": {
  "expo": "~53.0.7",
  "react": "19.0.0",
  "react-native": "0.79.2"
}
```

### 🏃‍♂️ 執行專案：

```bash
# 開發模式 (會自動開啟瀏覽器介面與開發選單)
npm start

# 或直接在 Android 模擬器中執行
npm run android
```

---

## 🏛️ 開發環境配置 (Environment Setup)

為了順利開發 Android App，你需要配置以下工具：

### 1️⃣ Android Studio
👉 [官方下載頁面](https://developer.android.com/studio?hl=zh-tw) 📥

### 2️⃣ Gradle 建置工具
👉 [Gradle Releases](https://gradle.org/releases/?locale=zh_TW) 🐘

### 3️⃣ Java 開發套件 (JDK)
*這部分請確保安裝對應版本的 JDK (建議 JDK 17 或更高)。*
👉 [JDK 下載參考](https://www.oracle.com/java/technologies/downloads/) ☕
> [!NOTE]
> 原文件中提供的連結為 `emoji-cheat-sheet`，若需查找 Emoji 可以參考：[ikatyang/emoji-cheat-sheet](https://github.com/ikatyang/emoji-cheat-sheet) 🎨

### ⚙️ 設定環境變數 (PowerShell 7)

執行 `code $profile` 來編輯你的 PowerShell 設定，並新增以下路徑：

```powershell
# 設定 Android SDK 路徑
$env:ANDROID_HOME = "C:\Users\你的使用者名稱\AppData\Local\Android\Sdk"
$env:PATH += ";$env:ANDROID_HOME\emulator;$env:ANDROID_HOME\platform-tools"

# 設定 Android SDK ROOT
$env:ANDROID_SDK_ROOT = "C:\Users\$env:USERNAME\AppData\Local\Android\Sdk"
$env:PATH += ";$env:ANDROID_SDK_ROOT"

# 設定 Java Home (請依據實際安裝路徑修改)
$env:JAVA_HOME = "C:\Program Files\Java\jdk-24" # 範例路徑，請改為 jdk 安裝根目錄
$env:PATH += ";$env:JAVA_HOME\bin"

# 設定 Gradle 路徑
$env:Path += ";C:\gradle-8.14-bin\gradle-8.14\bin"
```

---

## 🔍 聯機與除錯 (Debug & Check)

### 📲 檢查 ADB 狀態
```bash
# 檢查已連接的裝置清單
adb devices

# 若發生異常，可嘗試重啟 ADB 服務
adb kill-server
adb start-server
```

### 🧪 環境檢驗步驟
1.  **確認環境變數**：
    ```powershell
    $env:JAVA_HOME
    $env:ANDROID_SDK_ROOT
    ```
2.  **測試工具指令**：
    ```bash
    adb version
    gradle --version
    ```
3.  **啟動模擬器測試**：
    ```bash
    # 列出所有可用的 AVD (Android Virtual Device)
    emulator -list-avds

    # 啟動模擬器 (請將 Your_AVD_Name 替換為實際名稱)
    emulator -avd Your_AVD_Name -writable-system
    ```

---

## 🏗️ 建立測試專案 (Hello World)

1.  在 Android Studio 中選擇 **"New Project"** → **"Empty Activity"**。
2.  點擊右上角的 **"Run 'app'"** 按鈕 (綠色箭頭 🟢)。
3.  選擇你剛啟動的模擬器或已連接的實體裝置。

---

## ❓ 常見問題排查 (Troubleshooting)

- **adb server version doesn't match 錯誤**：
  這是典型的版本衝突，請執行：
  ```bash
  adb kill-server
  adb start-server
  ```

- **重新啟動終端機後生效**：
  修改環境變數後，建議重新啟動 PowerShell 並執行以下指令確認狀態：
  ```bash
  emulator -list-avds
  ```

---
*祝開發順利！Happy Coding!* 💻✨