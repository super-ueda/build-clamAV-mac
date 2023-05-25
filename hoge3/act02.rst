
================================================================
**BrewでClamAV導入**
================================================================

※ Brewをインストールしていない場合には前の操作へ戻る。

ClamAVをインストールする。
================================================================

.. code-block:: bash

    brew install clamav

ClamAVの最新の定義ファイルを取得する。
================================================================

.. code-block:: bash
    
    #ディレクトリを移動する。
    cd /opt/homebrew/etc/clamav

    #ClamAVnの設定ファイルをコピー
    cp clamd.conf.sample ./clamd.conf
    cp freshclam.conf.sample ./freshclam.conf

    #8行め辺りにある Exampleの先頭に#をつけてコメントアウトする。
    vi freshclam.conf