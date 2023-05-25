###########################################################
**MacユーザーのためのClamAV導入-4**
###########################################################

| このドキュメントもあくまで参考資料であり、興味がある人は
| 自分自身で手を動かし、書籍やWebで公開されている情報を
| 蒐集することを推奨するものとします。



*４ー１．Libcheck/Checkをバイナリで入手する*

| 直近の更新されているCheckをダウンロードし、解凍する。
| 　cd ~
| 　curl -LO https://github.com/libcheck/check/releases/download/0.15.2/check-0.15.2.tar.gz
| 　tar zxf check-0.15.2.tar.gz

*４－２．Checkを構成する*

| 先の手順で解凍したフォルダに入り、自前で準備する。
| 　cd check-0.15.2
| 　./configure --prefix=/usr/local/check

*４－３．Checkをコンパイルしてインストールする*

| 　make && sudo make check
| 　sudo make install

*４－４．pathを通しておく*

| パッケージが動作するよう、pathを通しておく。
| 　export PATH="/usr/local/check/bin:$PATH"
