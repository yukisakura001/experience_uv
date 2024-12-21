# UVのお試し

# UVを導入

## 注意

- 導入後コマンドを使用するにはPCの再起動が必要（パスを通すため）

## UVをインストール

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

## shellのオートコンプリートをオンにする？（効果不明）

```powershell
Add-Content -Path $PROFILE -Value '(& uv generate-shell-completion powershell) | Out-String | Invoke-Expression'
Add-Content -Path $PROFILE -Value '(& uvx --generate-shell-completion powershell) | Out-String | Invoke-Expression'
```

## アップグレード

```powershell
uv self update
```

## オートコンプリート追加

```powershell
uv generate-shell-completion powershell
```

- powershellのところを任意のシェルにできるっぽい

## pythonバージョンを追加

```powershell
uv python install 3.10 3.11 3.12
```

- バージョンを任意に選択できる

## 導入しているPythonバージョンを確認

```powershell
uv python list
```

# Pythonプロジェクト構築

## アプリプロジェクト作成

```
uv init --app プロジェクト名
```

## 環境の構築

```powershell
uv sync
```

## Python実行

```powershell
uv run hello.py
```

## pipコマンドの使用（あまり使わない方が良いっぽい？）

例

```
uv pip list
```

## Pythonのバージョン変更

```powershell
uv python pin 3.10
```

## 

## ライブラリのインストール

### インストール

```powershell
uv add ライブラリ
```

### アンインストール

```powershell
uv remove ライブラリ
```

### 一括インストール

```powershell
uv add -r requirements.txt 
```

### バージョン指定

```powershell
uv add "numpy==1.26.4"
```

### 開発用ライブラリに導入

```powershell
uv add jupyterlab --dev
```

### pypl以外のライブラリ導入

```powershell
 uv add https://files.pythonhosted.org/packages/f7/29/13965af254e3373bceae8fb9a0e6ea0d0e571171b80d6646932131d6439b/setuptools-69.5.1-py3-none-any.whl
```

# 疑問

- Pyinstallerはどうやって使うのか
