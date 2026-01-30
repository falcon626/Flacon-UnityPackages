# Fl-ZIPDI（Falcon ZIP Drag Importer）

Unity エディタの Project（Assets）ウィンドウに `.zip` をドラッグ＆ドロップしたとき、ZIP 内の **`.unitypackage` を検出してインポート**し、さらに ZIP 内に `Assets/` 構造が含まれている場合は **生アセット（Prefab 含む）を展開して取り込む**ためのエディタ拡張です。

- 対応 Unity：**Unity 2022.3.22f1**
- 対象：**Editor 専用**（ビルドには含めない）

---

## 再配布は原則として許可していません。
## また、改変による不具合は自己責任とします。

### 内容物
- FlZipdiImporterCore.cs
- FlZipdiMenu.cs
- FlZipdiProcessedCache.cs
- FlZipdiSelectionWindow.cs
- FlZipdiSettings.cs
- FlZipdiZipDeletion.cs
- FlZipUnitypackageDropImporter.Editor.asmdef

### 概要

Fl-ZIPDI は次のことを行います。

1. Project（Assets）ウィンドウへ `.zip` が取り込まれたことを検知  
2. ZIP 内を走査し、`.unitypackage` があれば抽出して `AssetDatabase.ImportPackage()` でインポート  
3. ZIP 内に `Assets/` ルートがある場合、必要に応じて `Assets/Fl-ZIPDI/Extracted/...` などへ展開して Unity に取り込む（Prefab 対応）

---

### 主な機能

- Tools->Falcon->Fl-ZIPDI->Settings
- ✅ ZIP 内の `.unitypackage` を自動検出＆インポート
- ✅ `.unitypackage` が複数ある場合に以下を選択可能  
  - **All**（全て）  
  - **FirstOnly**（最初の1つ）  
  - **Manual**（リストから選択）
- ✅ Unity 標準の Import ダイアログ有り/無し切替
- ✅ ZIP を Assets に残す/残さない（デフォルト：残さない）
- ✅ Prefab 対応（ZIP 内 `Assets/` を展開して取り込み）

---