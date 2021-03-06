# ページのトラブルシューティング

## ページヒットトラッキングが動作しない

ページのヒットはトラッキングピクセルによって追跡されています。これは単純にページソースコード内の1ピクセルのGIF画像です。ページがブラウザで閲覧された場合、ブラウザは画像をロードしようとします。この画像のロードリクエストが、Mautic がページヒットアクションを追跡するために実際に必要としているものです。

トラッキングが機能しない場合は次の項目を確認してください。
1. ログインしているMautic管理者はトラッキングしません。これにより、Mautic管理者がページを編集中にそのページを確認しても統計が歪めれらません。そのため、トラッキングのテストをする際はMauticからログアウトするかブラウザのシークレットウインドウを使用するようにしてください。
2. トラッキングピクセルは，追跡したいページの一部ではありません。 Mautic は，そのソースコードにトラッキングピクセルを持っているページのみを追跡することができます。
3. トラッキングピクセルが正しく構成されていません。ブラウザの開発ツールでこれを確認することができます。 開発ツール（F12キーを押して起動できます）を開き，追跡したいページで見ながら，[ネットワーク]タブに移動し，ページをリロードしてください。あなたが行われたすべての要求が表示されます。イメージだけにそれらの要求をフィルタリングし，mtracking.gif イメージを見つけます。それはステータス 200 でしょうか？　200 以外の場合は，Mautic　インスタンスへのパスが正しくない可能性があります。

[詳しくはトラッキングピクセルを参照ください](./../contacts/contact_monitoring.html)
