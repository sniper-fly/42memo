
## よく使うコマンド

※WSL上では sudo を前に入れないとちゃんと機能しない

docker ps　（実行中のコンテナを表示）  
docker ps -a （実行中、停止中すべてのコンテナを表示）

docker build はDockerfileからイメージを作るコマンド  
-tオプションでイメージ名を付けられる (docker build -t [image name] [Dockerfile path])  
docker run はイメージからコンテナを作る



## Dockerfileについて

FROM debian:buster  
でdockerhubで配布されてるdebian buster(version 10)をdocker pullする
（つまりdocker pull debian:busterとたぶん同じ）

DockerfileのRUNとCMDの違い  
https://qiita.com/YumaInaura/items/ce40a792da308a068310

Dockerfile 書き方  
https://www.wakuwakubank.com/posts/270-docker-build-image/  

## tips

参照　https://qiita.com/SUZUKI_Masaya/items/1fd9489e631c78e5b007  
apt search ???  
dpkg -l | grep ???  

インタプリタではapt, 自動で実行するときなどはapt-getが推奨らしい  

