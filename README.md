# Chatwork Analysis Project: Nuro光 マニュアル作成

このプロジェクトは、Claude DesktopとMCP (Model Context Protocol) を利用して、Chatwork上の会話ログから「Nuro光の注意点マニュアル」を自動生成するためのリポジトリです。

## 前提条件
- **Claude Desktop App** がインストールされていること
- **Chatwork API Token** が取得済みであること
- **Node.js / npm** がインストールされていること（`npx` コマンドが使えること）

## セットアップ手順

### 1. MCPサーバーの設定
Claude Desktopの設定ファイル (`~/Library/Application Support/Claude/claude_desktop_config.json` などOSによって異なる) を開き、以下を追加します。

```json
{
  "mcpServers": {
    "chatwork": {
      "command": "npx",
      "args": [
        "-y",
        "@st-little/chatwork-mcp"
      ],
      "env": {
        "CHATWORK_API_TOKEN": "ここにあなたのAPIトークンを貼り付け"
      }
    }
  }
}
