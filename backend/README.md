# 手順

1. API_KEY を払い出します。（API_KEY には gemini が使える権限を付与しておいてください）
2. google cloud のコンソールから functions を 2 つ作成します。それぞれ同様の設定値で下記の通り設定してください。
   1. リージョン: asia-northeast1
   2. トリガー: https（未認証の呼び出しを許可）
   3. メモリ: 512 MiB
   4. CPU: 333 millis
   5. タイムアウト: 600 秒
   6. その他デフォルト
3. 各 functions の環境変数として、キー:GEMINI_API_KEY, バリュー:手順 1 で作成した API キーをセットします。
4. それぞれの main.py と requirements.txt をコピーしデプロイします。
5. 使用するロールに、各種必要な権限を追加します。（Cloud Translation API、Gemini for Google Cloud、Vertex AI が利用できる権限を付けてください。）
6. 各種サービスが有効化されていない場合は有効化を行ってください。(利用するサービスは、Translation API、Gemini、Vertex AI Imagen です)
