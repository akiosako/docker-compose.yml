# **docker-compose.ymlについて**

```
version: '3.1'
services:
  db:
    image: mysql
    command: --default-authentication-plugin=mysql_native_password
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: root
      MYSQL_DATABASE: users
      MYSQL_USER: vatic
      MYSQL_PASSWORD: francois0413
    ports:
      - 3307:3306
```            
**version**  
docker-composeで使用するバージョンを定義  
バージョンによって、ComposeFileの書き方が異なるので注意  
公式：https://docs.docker.com/compose/compose-file/

**Services(サービス)**  
Docker-Composeでは、アプリケーションを動かすための各要素をServiceと読んでる。ComposeFileにも、serviceとして、それぞれのServicesの内容をネストさせて記述  

|項目|意味|
|:-:|:-:|
|image|コンテナーを開始するイメージを指定
|restart|実行時に再起動するかどうか|  
|command|コンテナイメージによって宣言されたデフォルトのコマンド(つまり、Dockerfileの)をオーバーライド  |  
|environment|DBについての環境変数設定(パスワードなど)|  
|ports|DBのDockerImageを立ち上げる際のポート番号|  

**restart:always**  
 ポリシーは、コンテナが削除されるまで、常にコンテナを再起動します。  


