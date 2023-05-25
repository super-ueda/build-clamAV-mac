###########################################################
**MacユーザーのためのClamAV導入-7**
###########################################################

| このドキュメントもあくまで参考資料であり、興味がある人は
| 自分自身で手を動かし、書籍やWebで公開されている情報を
| 蒐集することを推奨するものとします。

※JSON-Cとは、C言語に実装されたJSON

*７ー１．JSON-Cをバイナリで入手する*

| 直近の更新されているCheckをダウンロードし、解凍する。
| 　cd ~
| 　curl -LO https://s3.amazonaws.com/json-c_releases/releases/json-c-0.16.tar.gz 
| 　tar zxf json-c-0.16.tar.gz

*７－２．JSON-Cを構成し、生成する*

| 先の手順で解凍したフォルダに入り、自前で準備する。
| 　cd json-c-0.16
| 　mkdir build
| 　cd build
| 　cmake -D CMAKE_INSTALL_PREFIX=/usr/local/json-c ..

*７－３．JSON-Cをコンパイルしてインストールする*

| 　make && sudo make test
| 　sudo make install

*７－４．シンボリックリンクを作る*

| パッケージが動作するよう、シンボリックリンクを作っておく。
| 　sudo ln -s /usr/local/json-c/lib/libjson-c.5.dylib /usr/local/lib/


