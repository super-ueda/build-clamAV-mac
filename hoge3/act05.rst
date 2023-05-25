###########################################################
**MacユーザーのためのClamAV導入-5**
###########################################################

| このドキュメントもあくまで参考資料であり、興味がある人は
| 自分自身で手を動かし、書籍やWebで公開されている情報を
| 蒐集することを推奨するものとします。



*５ー１．PCRE2をバイナリで入手する*

| 直近の更新されているCheckをダウンロードし、解凍する。
| 　cd ~
| 　curl -LO https://github.com/PCRE2Project/pcre2/releases/download/pcre2-10.40/pcre2-10.40.tar.bz2
| 　tar zxf pcre2-10.40.tar.bz2

*５－２．Checkを構成する*

| 先の手順で解凍したフォルダに入り、自前で準備する。
| 　cd pcre2-10.40
| 　./configure --prefix=/usr/local/pcre2

*５－３．PCRE2をコンパイルしてインストールする*

| 　make && sudo make check
| 　sudo make install

