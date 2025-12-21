# Sotusei 5.2 - Unreal Engine プロジェクト

Unreal Engine 5.2を使用したコンサートステージ・ライブ演出プロジェクトです。DMX照明制御、VRMキャラクター、リップシンク機能などを統合したライブ演出システムです。

## プロジェクト概要

このプロジェクトは、以下の機能を提供します：

- **DMX照明制御**: Art-Netプロトコルを使用した照明制御システム
- **VRMキャラクター**: VRM4UプラグインによるVRMモデルのインポート・表示
- **リップシンク**: OVRLipSyncによる音声同期リップシンク
- **コンサートステージ**: モジュラーなコンサートステージシステム
- **ペンライト制御**: ペンライトの同期制御機能
- **LiveLink連携**: 外部データとの連携機能

## 必要な環境

- **Unreal Engine**: 5.2
- **プラットフォーム**: Windows 64-bit

## 必要なプラグイン

このプロジェクトは以下のプラグインを使用しています：

### エンジン標準プラグイン
- DMXControlConsole
- DMXEngine
- DMXFixtures
- DMXPixelMapping
- DMXProtocol
- RemoteControlProtocolDMX
- ModelingToolsEditorMode
- RawInput
- LiveLink

### カスタムプラグイン
- **OVRLipSync**: リップシンク機能
- **VRM4U**: VRMモデルサポート（[GitHub](https://github.com/ruyo/VRM4U)）

## セットアップ手順

1. **Unreal Engine 5.2のインストール**
   - Epic Games LauncherからUnreal Engine 5.2をインストール

2. **プロジェクトのクローン**
   ```bash
   git clone <repository-url>
   cd "sotusei 5.2"
   ```

3. **プロジェクトの開く**
   - `sotusei_1004.uproject`をダブルクリックしてUnreal Editorで開く
   - 初回起動時、モジュールの再コンパイルが求められる場合は「Yes」を選択

4. **プラグインの確認**
   - エディタで「Edit」→「Plugins」を開き、必要なプラグインが有効になっているか確認
   - VRM4Uプラグインは既にプロジェクトに含まれています

## プロジェクト構造

```
sotusei 5.2/
├── Content/                    # ゲームコンテンツ
│   ├── DMXTemplate/           # DMXテンプレート
│   ├── ModularConcertStage/   # コンサートステージアセット
│   ├── mystaff/               # カスタムコンテンツ
│   │   ├── BP/               # ブループリント
│   │   ├── DMX/              # DMXライブラリ
│   │   ├── lipsync/          # リップシンク関連
│   │   ├── map/              # マップ
│   │   ├── mdoel/            # モデル
│   │   ├── motion/           # モーション
│   │   └── penlight/         # ペンライト
│   └── Movies/               # 動画ファイル
├── Config/                    # 設定ファイル
├── Plugins/                   # プラグイン
│   ├── OVRLipSync/          # OVRLipSyncプラグイン
│   └── VRM4U/               # VRM4Uプラグイン
└── sotusei_1004.uproject     # プロジェクトファイル
```

## DMX設定

プロジェクトはArt-Netプロトコルを使用してDMX照明を制御します。設定は`Config/DefaultEngine.ini`に含まれています：

- **Input Ports**: InputA, InputB, InputC
- **Output Ports**: OutputA, OutputB, OutputC
- **Protocol**: Art-Net
- **Refresh Rate**: 30 FPS

## 使用方法

1. **マップの起動**
   - デフォルトマップ: `/Game/DMXTemplate/Maps/Fixtures`
   - エディタで「Play」ボタンをクリックして実行

2. **DMX制御**
   - DMX Control Consoleを使用して照明を制御
   - Art-Net対応のDMXデバイスに接続

3. **VRMキャラクター**
   - VRMファイルをインポートして使用
   - LiveLinkでモーションを同期

4. **リップシンク**
   - 音声ファイルと同期してリップシンクを実行

## 注意事項

- このプロジェクトには大量のアセットが含まれています
- 初回起動時はアセットの読み込みに時間がかかる場合があります
- プラグインのバイナリファイルは`.gitignore`で除外されています
- 大きなメディアファイル（動画など）は必要に応じて別途管理してください

## ライセンス

プロジェクトのライセンスについては、各プラグインのライセンスを確認してください：

- **VRM4U**: MIT License
- **OVRLipSync**: 各プラグインのライセンスに従います

## トラブルシューティング

### プロジェクトが開けない場合
- Unreal Engine 5.2が正しくインストールされているか確認
- プロジェクトファイルのパスに日本語が含まれていないか確認

### プラグインエラーが発生する場合
- プラグインが正しく有効になっているか確認
- プラグインのソースコードが正しくコンパイルされているか確認

### DMXが動作しない場合
- Art-Netデバイスが正しく接続されているか確認
- ネットワーク設定を確認

## 開発者向け情報

### ビルド要件
- Visual Studio 2019以降（C++開発ツール）
- Windows 10/11 64-bit

### コンパイル
プロジェクトを開くと自動的にモジュールがコンパイルされます。手動でコンパイルする場合は：

1. プロジェクトファイルを右クリック
2. 「Generate Visual Studio project files」を選択
3. Visual Studioでソリューションを開く
4. ビルドを実行

## 連絡先・サポート

問題が発生した場合は、GitHubのIssuesで報告してください。

