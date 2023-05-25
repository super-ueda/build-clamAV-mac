###########################################################
**MacユーザーのためのClamAV導入-3**
###########################################################

| このドキュメントもあくまで参考資料であり、興味がある人は
| 自分自身で手を動かし、書籍やWebで公開されている情報を
| 蒐集することを推奨するものとします。



*３ー１．pkg-configをバイナリで入手する*

| 直近の更新されているpkg-configをダウンロードし、解凍する。
| 　cd ~
| 　curl -O https://pkg-config.freedesktop.org/releases/pkg-config-0.29.2.tar.gz
| 　tar zxf pkg-config-0.29.2.tar.gz

*３－２．pkg-configを構成する*

| 先の手順で解凍したフォルダに入り、自前で準備する。
| 　cd pkg-config-0.29.2
| 　export LDFLAGS="-framework CoreFoundation" 
| 　./configure --with-internal-glib --prefix=/usr/local/pkgconfig

*３－３．pkg-configをコンパイルしてインストールする*

| 　make && sudo make check
| 　sudo make install

*３－４．pathを通しておく*

| パッケージが動作するよう、pathを通しておく。
| 　export PATH="/usr/local/keyconfig/bin:$PATH"
