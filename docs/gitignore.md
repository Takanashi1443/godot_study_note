# Godotプロジェクトの.gitignoreの中身

## 中身

```

# ------------------------------------------------------------
# Godot
# ------------------------------------------------------------

# Godot が自動生成するインポート済みリソース
.godot/

# Godot 3系を使う場合に生成されることがある
.import/

# インポート設定のバックアップ
*.import~

# 一時ファイル
*.tmp
*.temp

# クラッシュログなど
*.log


# ------------------------------------------------------------
# Export / Build outputs
# ------------------------------------------------------------

# エクスポート先
build/
builds/
export/
exports/
dist/

# 実行ファイル・パッケージ類
*.exe
*.app
*.apk
*.aab
*.ipa
*.dmg
*.zip
*.tar
*.tar.gz
*.7z


# ------------------------------------------------------------
# Debug / Local data
# ------------------------------------------------------------

# デバッグ用データ
debug/
debug_data/

# ローカルのセーブデータやテスト用出力
user_data/
save_data/
saves/

# スクリーンショット・録画など
screenshots/
recordings/


# ------------------------------------------------------------
# IDE / Editor
# ------------------------------------------------------------

# Visual Studio Code
.vscode/*
!.vscode/extensions.json
!.vscode/settings.json
!.vscode/launch.json
!.vscode/tasks.json

# JetBrains
.idea/

# Visual Studio
.vs/

# OS
.DS_Store
Thumbs.db
desktop.ini


# ------------------------------------------------------------
# Python tools
# ------------------------------------------------------------

# フォルダ生成ツールなどをPythonで作る場合
__pycache__/
*.py[cod]
.venv/
venv/
env/

# Pythonのテスト・ビルド生成物
.pytest_cache/
dist/
build/
*.egg-info/


# ------------------------------------------------------------
# Environment / Local config
# ------------------------------------------------------------

# 個人環境の設定
.env
.env.*
*.local

# APIキーやローカル設定を含む可能性があるファイル
local_config.*
secrets.*

```

## 説明


この `.gitignore` で一番重要なのは、Godotの自動生成フォルダであるこれです。

```gitignore
.godot/
```

一方で、**`project.godot` は無視しない**でください。これはプロジェクト設定本体なので、Git管理対象にします。

また、次のようなファイルも基本的にはGitに入れます。

```text
project.godot
*.tscn
*.gd
*.tres
*.res
*.import
```

特に `*.import` は少し紛らわしいですが、Godot 4では画像や音声などのインポート設定として必要になることが多いので、基本的には管理対象でよいです。無視するのは `.godot/` の中身です。

あなたのテンプレート用なら、最初はこのくらいまで簡略化しても十分です。

```gitignore
.godot/
.import/

build/
builds/
export/
exports/

debug/
debug_data/
user_data/
save_data/
saves/

.vscode/*
!.vscode/extensions.json
!.vscode/settings.json
!.vscode/launch.json
!.vscode/tasks.json

.idea/
.vs/

.DS_Store
Thumbs.db
desktop.ini

__pycache__/
.venv/
venv/

.env
.env.*
*.local
```

最初のGodotテンプレートには、下の簡略版を入れておくのが扱いやすいと思います。
