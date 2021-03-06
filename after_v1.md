## v1.xとv2.0
- v1.0ではサイトを制作するにあたり最低限必要なコンテンツを収集。
- v1.xでページ追加、要素追加など、コンテンツを補強。英訳も。
- v2.0でデザイン刷新する。

### v1.x
- 英語翻訳（最優先、タスクに出す）
- 過去ブログの移植（ライター募集のキッカケに）
- FAQページをまとめる。（ライター募集の）
- Githubステージング環境を入れ替え（protoを廃止し、本番環境をupstreamに）
    - WebsiteとBlogのブランチを分けるかも。Stagingを作成した。（後でGitbookに反映）
    - BlogはPRマージ自動化する？webhookで。
- プロダクトページ（プロジェクトマイルストーン）
- Teamページ（ロールメンバー）
- 募集ページ作成
- v1のトップページのCSSをいじりたい人✋
- アナリティクスページの追加（並行の別テーマとして下記にスピンオフ）

### v2.0
- テーマファイルの見直し
    - 多言語サポートを強化
- デザイン
    - コンセプトとデザイン　パララックスか、ニューモーフィズムか、フラットか、何を主張したいのか
    - カラーパレット：紅、白、黒、＋差し色をいくつか
    - モチーフ（パレットを主体に、クリプト：幾何学、グラデを入れるか、和の要素：数寄屋造りを入れるか）
    - 新デザインに合わせた素材作り
- より簡単に投稿できるツールを模索
    - For ライター、デザイナー、財務担当、ウェブ制作者、翻訳者
    - サブモジュール化の検討
    - mirrorは何か使える？調べてない。
- Docsの統合
    - Gitbook, docsaurus, HackMD, mdboook 系か Docslab, DigiDocs 系か
    - 選定にあたっては、Githubストレージ、Netlifyビルドのリミットを気にすること
- インフラの検討
    - 分散型サービスの適用可能性、パフォーマンス、コストを調査
    - Fleek, IPFS, Storj
    - eth, hnsドメイン
    - ブランドアセットなどのファイル置き場。ヘッドレスCMSやChainsafeなど

## 📈📈アナリティクス📈📈

## アナリティクス#1 ガバナンス🙋
DAOの永続的な活動にとって、ガバナンストークンの大きな偏りはコミュニティの意思決定を歪め、コミュニティおよびトレジャリーを占有する危険がある。また、一時的なトークンの買い占め（Vote Buying）も同様に、意思決定と価格変動のリスクがある。それらのリスクが内在しないかどうかを、**常にコミュニティが監視でき、分析するため、ガバナンストークンの保有状況と変動状況を一目で見られるツール**を用意したい。コミュニティを外部から評価するにおいても有用であると思われる。

1. TXJPアロケーション
    - 配布済みと未配布
    - 配布済みのうち、コミュニティトレジャリー、流動性プールの内数、個人保有
2. 時価総額
    - 総発行数、Circulating Supplyを法定通貨立て表示
3. TXJPホルダー分布 ✨
    - 総ホルダー数と変動率
    - トップ15の保有ランキング、保有数の変動率⬆︎⬇︎◯％　※期間をまずは1週間で。
    - 同時に、流動性プールでの価格変動を横に並べて表示すると効果的かも。対ETH？。
    - アップデートで、ランク変動、大量保有（◯％上昇）、大量ウォレット移動を通知する機能も。
    - ランキングのうち、トレジャリーと流動性プールを色分けしたい。1.の色と合わせて。
    - 生のTXJPと、Fuseプールのfトークン保有数とを合算しなければならない。
    - FuseプールのClaimableは含めない。
    - 複数ウォレットに分けて保有する人物のウォレット間TXまで紐づけられるかは調査。

備考
- Coingecko、Etherscan、Uniswap等でそれら1つ1つの情報は得られるが、全て人力で見に行くのは不便であり誰もしなくなる。それら情報を集め、コミュニティが監視するダッシュボードに集める。
- Dune Analyticsはお金がかかるのと、UIのカスタマイズが難しい。うまく使えそうなところは使う。
- DAO Analyticsサービスが発達したら連携するのも視野に。
- ディストリビューションは分かりやすく保有比率の変動が発生する。Round2, 3, 4での移り変わりをライターがBefore Afterで差異をまとめる。分析できれば分析も。
- 変動率や推移グラフを精緻にするには、ヒストリカルデータを溜め込み、一定時間間隔で再計算させるためのインフラが必要になる。精緻化はアップデートで行い、リソース使用率のみ取得しておく。
- サービス品質的に、リアルタイムな変動検知はここではしない。例えば、TXJP価格釣り上げを検知することはしない。


## アナリティクス#2 トレジャリー💰
DAOの永続的な活動にとって、運営に毎月必要となる資金を長期的に準備できる状況をキープする必要がある。いわゆるトレジャリーマネジメントであり、トレジャリーの収支とランウェイを常時確認し、必要に応じてトレジャリー管理方針を見直していく。月次財務レポートではその詳細を報告しているが、一般の知識では把握が難しい。**コミュニティメンバーが意思決定をするにあたりトレジャリーの状況を把握するため、収入、支出、PL、ランウェイの推移と変動率をシンプルに可視化するサイト**を用意したい。

1. コミュニティ資産状況
    - 手元資金（ウォレット）
    - 総資産（ウォレット、アセット）
2. トレジャリー収支
    - 収入（ファンド運用益がこれに当たる）
    - 支出（TXをカテゴライズ）　※Fuseプールのディストリビューションも支出でよい？
    - PL
    - ランウェイ
3. コミュニティファンドの運用状況
    - どこに投資しているかをアセット種別で。
    - それぞれのAPY、トータルのAPY
    - 一定期間ごとのリターンと変動率
4. TXJP Buy＆Pool状況
    - 毎月の数量、金額
    - 累積もあるとインパクトが出せそう

備考
- 上記の大半のデータはZapperで取得が可能。defigeek.eth を見ればウォレットとアセットの種別が分かる。これをサマライズし全体収支と変動推移をグラフ化。DAOの運営持続性を確かめられるようにするのが目的である。
- Zapperでは、LP FeeのAPY表示はあり、CRV, CVX, AVAXなどのトークンリワードは金額のみの表示になっている。
- 財務部との協力で行いたい。データの計算方法によって月次レポートの数値と差異が出るのを避けることと、データの一部は財務レポートにも活用できるようにしたい。
- ストラテジストとの連携も行う。ファンド運用の目標リターン率とマッチしているか、ヘルスファクターの推移がどうなっているか、など、ほしい情報と一致させる。


## アナリティクス#3 投票
ガバナンスが有効に機能しているかどうか、有効票、浮動票の割合と傾向を見る。
- 投票率、投票数
- DeepDAOにお任せでもよいかも。

備考
- 疑問。あるウォレットで投票した後に、別のウォレットに移して二重に三重に再投票はできてしまうのだろうか。投票後にFuseプールに入れて、fトークンに換えて投票するのも然り。

### 💻環境
- UIとテーマは出来合いのBootstrapのものを買う。
- Javascript、npm、yarn、SASS
- 集計、データ集積はAWS
- レンダリングをどうするかは試しながら。


## DAOリサーチ
DAOは全てのコミュニティメンバーが主人公である。1人1人がより活発にアクションを起こし、意見や投票を簡単に行い、コミュニティの総意に反映するための環境づくりとして、情報、選択肢、ツールを広く集めたい。DeFi、NFTと比べると、DAOは地味であり、どのようなサービスがあり、どんな開発が進行中かをコミュニティ参加者はよく知らない。大抵、フォーラムとSnapshotしか知らない。まずは設計や方針の準備段階として、情報を集め、伝え、意見や議論を呼ぶことを目的としたい。より広く伝わるようシンプルで読みやすいドキュメント、「試してみた」のような疑似体験を得られるコンテンツを求める。

- DAOフレームワークを作っていくための調査
    - DAOツール（マルチシグ、コミュニケーションツール、フォーラム、投票ツール＝Snapshot）との連携サービス
    - DAO開発コミュニティ
    - DAOに使えそうなツールを色々試す
    - NFT、SNSゲートウェイの活用案
    - DAO2DAOのチャレンジ例
- 投票の重み付けとそれを実現するツール
    - Conviction Voting
    - Vote Buyingに対する各コミュニティの取り組み
- 通知機能
    - プロポーザル提出、投票開始終了
    - EPNSがメインネットリリースしたらテンプレートを使うのでもよい。


## トークンリスティング
大手のトークンリストにTXJPを掲載し、TXJPの露出、信憑性、ユーティリティを高める。DEXでコントラクトアドレスを入力したときに「危険です」と言われたり、「？」アイコンが表示されることで、市場参加者の投資機会を逸することを軽減する。また、リスティングすることにより、さらに他のDappsの審査を通りやすくしてWeb3エコシステムへの参加・採用を広げる。

- Coingecko
- CoinMarketCap
- Zapper
- Zerion
- DeBank
- Defi Pulse
- DefiLlama
- その他DEXのホワイトリスト、トークンリスト
