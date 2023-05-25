###########################################################
**MacユーザーのためのClamAV導入-6**
###########################################################

| このドキュメントもあくまで参考資料であり、興味がある人は
| 自分自身で手を動かし、書籍やWebで公開されている情報を
| 蒐集することを推奨するものとします。



*６ー１．LibreSSLをバイナリで入手する*

| 直近の更新されているCheckをダウンロードし、解凍する。
| 　cd ~
| 　curl -O https://ftp.openbsd.org/pub/OpenBSD/LibreSSL/libressl-3.6.1.tar.gz 
| 　tar zxf libressl-3.6.1.tar.gz

*６－２．LibreSSLを構成する*

| 先の手順で解凍したフォルダに入り、自前で準備する。
| 　cd libressl-3.6.1
| 　./configure --prefix=/usr/local/libressl

*６－３．LibreSSLをコンパイルしてインストールする*

| 　make && sudo make check
| 　sudo make install

*６－４．pathを通しておく*

| パッケージが動作するよう、pathを通しておく。
| 　export PATH="/usr/local/libressl/bin:$PATH"

*６－５．インストール情報を確認する*

| パッケージの配置場所を確認する。
| 　which openssl
| 　下記のように出力されればOK
| 　　/usr/local/libressl/bin/openssl
| パッケージのバージョンを確認する。
| 　openssl version
| 　下記のように出力されればOK
| 　　LibreSSL 3.6.1

