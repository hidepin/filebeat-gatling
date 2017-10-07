filebeat-gatling
============================================================

初期セットアップ手順
------------------------------------------------------------

1. filebeatをダウンロード

  ```
  curl -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-x.x.x-linux-x86_64.tar.gz
  ```

2. filebeatを展開

  ```
  tar xvf filebeat-x.x.x-linux-x86_64.tar.gz
  ```

3. filebeat-gatlingをclone

  ```
  cd filebeat-x.x.x-linux-x86_64
  git clone https://github.com/hidepin/filebeat-gatling.git
  ```

4. filebeat-gatling.ymlのパーミッションを変更

  ```
  chmod go-w filebeat-gatling/filebeat-gatling.yml
  ```

5. ingest node設定を追加

  ```
  curl -XPUT -H 'Content-Type: application/json' 'http://192.168.0.50:9200/_ingest/pipeline/gatling' -d @filebeat-gatling/gatling-pipeline.json
  ```

filebeatを実行
------------------------------------------------------------

1. filebeatを実行

  ```
  env HOSTS="'xxx.xxx.xxx.xxx:9200'" ./filebeat -c filebeat-gatling/filebeat-gatling.yml
  ```
