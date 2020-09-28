# intdash SDK for Python tutorials for AWS Marketplace

こちらは、AWS Market Place向けの、intdash SDK for Python のチュートリアル集です。[intdash SDK for Python のドキュメント](https://docs.intdash.jp/sdk/python/latest/ja) を合わせて参照してください。

## チュートリアル一覧

**1_process-acquisition-data： SDKを使ってサーバーのデータを加工してみよう**
「intdashチュートリアル1」でCSVファイルを用いてアップロードした計測情報を取得し、加工します。

**2_upload-csv-data.ipynb： SDKを使って複数のCSVファイルをアップロードしてみよう**
「intdashチュートリアル1D：intdash SDKを使って大量のCSVファイルをアップロードしてみよう」のコードです。複数のCSVファイルを一括でアップロードし、計測に変換します。

**3_save-data-as-csv： スマートフォンの伝送データをCSVで保存してみよう**
「intdashチュートリアル2B：スマートフォンから送信されたデータをPCに保存してみよう」のコードです。スマートフォン からintdashにアップロードされたデータを、CSV形式で保存します。

**4_acquisition-image-data： スマートフォンの伝送データを画像ファイルとして保存してみよう**
「intdashチュートリアル2B：スマートフォンから送信されたデータをPCに保存してみよう」のコードです。スマートフォンからintdashにアップロードされた動画データを、M-JPEG形式で保存します。

**5_realtime-streaming-execution-processing： スマートフォンの伝送データをリアルタイムで加工して送信してみよう**
「intdashチュートリアル2C：スマートフォンから取得したデータをリアルタイムに加工してみよう」のコードです。スマートフォンからintdashにアップロードされたセンサーデータに、リアルタイムで信号処理を行いアップロードします。

**0_create-signal-general-sensor：信号定義の登録サンプル (※)**  
信号定義を登録するためのコードです。信号定義は、時系列データをサーバー側で物理値に変換する際に必要です。

※ サーバー側に信号定義が登録されていない場合のみ、実行してください。   

## 事前準備 

### 動作環境の準備

本チュートリアルは、ドキュメントとコードが一体になったJupyter Notebookコンテンツです。そのため、コードの実行にはJupyter Notebookの動作環境が必要です。

[anaconda](https://www.anaconda.com/)を用いてインストールすると、Jupyter Notebookと合わせてPython環境を構築できます。

すでにPython環境が手元にある方は `pip` を利用することでJupyter Notebookをインストールすることができます。

```
$ pip install jupyter
```

### intdash SDK for Pythonのインストール

以下のコマンドでインストールします。

```
$ pip install intdash
```

### クライアントの生成

認証情報（発行したエッジアカウント）を使用し、クライアントを生成します。
クライアント生成時には、認証情報として **エッジトークン**  または、**ユーザー名／パスワードの組み合わせ** を指定します。

エッジトークン

```
  import intdash

  client = intdash.Client(
	  url = "https://example.intdash.jp",
	  edge_token = "your_token",
  )
```

ユーザー名／パスワード

```
  import intdash

  client = intdash.Client(
      url = "https://hoge.intdash.jp",
      username = "your_username_here",
      password = "your_password_here",
  )
```

### 信号定義の登録

本チュートリアルでは、時系列データの取得時に、信号定義（時系列データを物理値に変換するための定義）を使用するケースがあります。詳しくは `0_create-signal-general-sensor` を参考にしてください。

#### 信号定義を使用するチュートリアル

* 3_save-data-as-csv
* 5_realtime-streaming-execution-processing

### アプリケーションの準備

本サンプルコードでは、データの伝送およびデータの可視化に、以下の製品を使用します。製品の使用方法については intdashチュートリアルを参照してください。

- データの伝送：**Visual M2M Motion**
- データの可視化：**Visual M2M Data Visualizer**
