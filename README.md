# 基盤岩地球化学データベース

CSVを読み込んで表示する GitHub Pages / ローカル両対応版です。

## GitHubで公開する方法

このZIPを展開し、中身をそのままGitHubリポジトリ直下にアップロードしてください。

正しい配置は以下です。

```text
index.html
data/
  samples.csv
  major_elements.csv
  trace_elements.csv
  images.csv
samples/
  HX12-03/
  ...
README.md
.nojekyll
```

GitHub Pages の設定は以下にします。

```text
Settings → Pages
Source: Deploy from a branch
Branch: main
Folder: /root
```

重要：この版は `index.html` がリポジトリ直下にある前提です。  
`Folder: /docs` ではなく、必ず `/root` を選んでください。

## データ更新

Webページを更新するときは、HTMLではなくCSVを編集してください。

```text
data/samples.csv
data/major_elements.csv
data/trace_elements.csv
data/images.csv
```

## 写真追加

写真は `samples/試料No/` に入れ、`data/images.csv` にパスを追加します。

例：

```csv
sample_id,image_type,file_path,source,caption
HX12-03,rock_photo,samples/HX12-03/HX12-03_rock_01.jpg,original,rock photo
```

## ローカルで確認する方法

Windowsでは `start_local_server.bat` をダブルクリックし、ブラウザで以下を開きます。

```text
http://localhost:8000/
```

Macでは `start_local_server.command` を実行するか、ターミナルで以下を実行します。

```bash
python3 -m http.server 8000
```

その後、ブラウザで以下を開きます。

```text
http://localhost:8000/
```

`index.html` を直接ダブルクリックするとCSV読み込みが失敗することがあります。
