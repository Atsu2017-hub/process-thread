# process-thread
- プロセス
  - メモリ上に独立して展開される。これにより他のプロセスのデータ領域を破壊することがないがプロセス間の切り替えのオーバーヘッドが大きい。
    - コードセグメント（実行可能なコード）
    - データセグメント（グローバル変数や静的変数）
    - ヒープ（動的メモリ割り当て）
    - スタック（ローカル変数、関数パラメータ、関数呼び出し）
    - レジスタ（CPU の高速な一時的データ格納場所）
- スレッド
  - プロセスに含まれる(シングルスレッドプロセス、マルチスレッドプロセス)、プロセスをさらにプロセスに分けるイメージ。メモリを共有するのでプロセスの破壊可能性ありだが切り替えが高速。
    - ユーザ入力スレッド
    - 画面描画スレッド
    - インターネット通信スレッド
    - 画面描画に時間がかかるとき、ユーザ入力もスレッドを切り替えて受け付ける。この時画面描画の処理のプログラムカウンタ等を保存するコンテクストスイッチが行われる。
- コンテクストスイッチ
  - CPUを複数のプロセスが共有するとき、タイムスライス等でプロセスの切り替えが行われる。このとき切り替えられるプロセスの状態(Context)が保存され、次に割り当てられたときに復元する。(レジスタの値やプログラムカウンタなど)
