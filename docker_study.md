
## よく使うコマンド

※WSL上では sudo を前に入れないとちゃんと機能しない

docker ps　（実行中のコンテナを表示）  
docker ps -a （実行中、停止中すべてのコンテナを表示）

docker build はDockerfileからイメージを作るコマンド  
-tオプションでイメージ名を付けられる (docker build -t [image name] [Dockerfile path])  
docker run はイメージからコンテナを作る  

tオプションについて  
https://keymaso.com/programemory/docker/run-option-d/

docker run コマンドのあれこれ  
https://qiita.com/shimo_yama/items/d0c42394689132fcb4b6  

docker run --name [任意のコンテナ名]  

docker run -p [host ip]:[container ip]



## 使うpackage
```bash
apt-get install mariadb-server  
(apt-get install default-mysql-server)  
apt-get install nginx
apt-get install php
```



## Dockerfileについて

FROM debian:buster  
でdockerhubで配布されてるdebian buster(version 10)をdocker pullする
（つまりdocker pull debian:busterとたぶん同じ）

DockerfileのRUNとCMDの違い  
https://qiita.com/YumaInaura/items/ce40a792da308a068310

Dockerfile 書き方  
https://www.wakuwakubank.com/posts/270-docker-build-image/  

スライド解説  
https://www.slideshare.net/zembutsu/explaining-best-practices-for-writing-dockerfiles  

## tips

参照　https://qiita.com/SUZUKI_Masaya/items/1fd9489e631c78e5b007  
apt search [package name]  
dpkg -l | grep [package name]  

インタプリタではapt, 自動で実行するときなどはapt-getが推奨らしい  
https://tech-blog.cloud-config.jp/2019-09-09-dockerfile-apt-apt-get-source-tips/  

https://note.com/syamashi/n/nd296e3e46dab  
yamashiさんのメモ  

https://qiita.com/quwa/items/3a23c9dbe510e3e0f58e
ctrl + r , ctrl + sでコマンド検索

docker attach と docker execの違いについて  
https://qiita.com/RyoMa_0923/items/9b5d2c4a97205692a560  

vmとdockerの違いについて  
https://www.sbbit.jp/article/cont1/27963  
https://qiita.com/r-tominaga/items/8ac588d603802572185f  

metapackageとは？　ー＞　パッケージの依存関係のみを記したパッケージ。それ自体に中身はないらしい。  
https://wiki.ubuntulinux.jp/MetaPackages

