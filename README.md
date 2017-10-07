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

filebeatを実行
------------------------------------------------------------

1. filebeatを実行

  ```
  cd filebeast-gatling
  env HOSTS="'xxx.xxx.xxx.xxx:9200'" ./filebeat -c filebeat-gatling/filebeat-gatling.yml
  ```
