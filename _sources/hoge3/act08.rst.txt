###########################################################
**MacユーザーのためのClamAV導入-8**
###########################################################

| このドキュメントもあくまで参考資料であり、興味がある人は
| 自分自身で手を動かし、書籍やWebで公開されている情報を
| 蒐集することを推奨するものとします。



*８ー１．ClamAV本体をバイナリで入手する*

| 直近の更新されているCheckをダウンロードし、解凍する。
| 　cd ~
| 　curl -LO https://www.clamav.net/downloads/production/clamav-1.0.0-rc2.tar.gz 
| 　tar zxf clamav-1.0.0-rc2.tar.gz

*８－２．CMakeのオプションとライブラリパスを設定し、生成・構成する*

| 先の手順で解凍したフォルダに入り、自前で準備する。
| 　cd clamav-1.0.0-rc2
| 　mkdir build
| 　cd build
| 　cmake \
| 　-D CMAKE_BUILD_TYPE=Release \
| 　-D OPTIMIZE=ON \
| 　-D BYTECODE_RUNTIME="interpreter" \
| 　-D CMAKE_INSTALL_PREFIX=/usr/local/clamXav/ \
| 　-D ENABLE_JSON_SHARED=OFF \
| 　-D ENABLE_TESTS=ON \
| 　-D LIBCHECK_ROOT_DIR=/usr/local/check \
| 　-D LIBCHECK_INCLUDE_DIR=/usr/local/check/include/ \
| 　-D LIBCHECK_LIBRARY=/usr/local/check/lib/libcheck.0.dylib \
| 　-D OPENSSL_ROOT_DIR=/usr/local/libressl/ \
| 　-D OPENSSL_CRYPTO_LIBRARY=/usr/local/libressl/lib/libcrypto.50.dylib \
| 　-D OPENSSL_SSL_LIBRARY=/usr/local/libressl/lib/libssl.53.dylib \
| 　-D PCRE2_LIBRARY=/usr/local/pcre2/lib/libpcre2-8.0.dylib \
| 　-D PCRE2_INCLUDE_DIR=/usr/local/pcre2/include/ \
| 　-D JSONC_LIBRARY=/usr/local/json-c/lib/libjson-c.5.dylib \
| 　-D JSONC_INCLUDE_DIR=/usr/local/json-c/include/json-c/ \
| 　..

*８－３．先の操作でキチンと設定できたか確認する*

| 　下記のように出力されればOK
| 　-- Configuring done
| 　-- Generating done
| 　-- Build files have been written to: /Users/xxx/clamav-1.0.0-rc2/build

*８－４．コンパイルしてテストする*

| 　make && sudo make test

*８－５．テスト結果を確認する*

| 　下記のように出力されればOK
| 　 ※ あくまでイメージなので、「tests passed」となっているかがカギ。
| 　Running tests...
| 　Test project /Users/xxx/Desktop/clamav-1.0.0-rc2/build
| 　Start 1: libclamav
| 　1/6 Test #1: libclamav ........................   Passed   15.46 sec
| 　Start 2: libclamav_rust
| 　2/6 Test #2: libclamav_rust ...................   Passed    8.89 sec
| 　Start 3: clamscan
| 　3/6 Test #3: clamscan .........................   Passed    0.13 sec
| 　Start 4: clamd
| 　4/6 Test #4: clamd ............................   Passed   12.53 sec
| 　Start 5: freshclam
| 　5/6 Test #5: freshclam ........................   Passed   27.33 sec
| 　Start 6: sigtool
| 　6/6 Test #6: sigtool ..........................   Passed    0.46 sec
| 　100% tests passed, 0 tests failed out of 6
| 　
| 　Total Test time (real) =  64.81 sec

*８－６．ClamAVをインストールする*

| 　sudo make install

