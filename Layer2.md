## Layer2

### L2
- Optimism
- Arbitrum
- zkSync
- Polygon

### L2に行く前に
- [x] L2でのコントラクトアドレスがある（＝自動で作られる）
- [x] エクスプローラが整備され、財務情報として参照できる
- [x] スナップショットでL1と時間ズレ（ブロックズレ）の数量アンマッチが発生しない
- [ ] 流動性がある
- [ ] 投票でL1, L2で合計してカウントできる
- [ ] DappトークンのアロケーションがL2でできるか
- [ ] NewトークンへのマイグレーションをL1, L2とも行うかは未検討

### 手順
1. L2コントラクトを作成
2. ブリッジのトークンリストに登録（プルダウンに表示される）

### Optimism
1. L2コントラクト作成
  - EtherscanでWrite Contractするだけ。パーミッションレス。
  - https://community.optimism.io/docs/guides/token-dev/#
2. Optimismトークンリスト
  - ロゴ、jsonを用意してPR
  - kovanテストトークン

### Arbitrum
1. L2コントラクト作成
  - Arbitrumブリッジを使用してブリッジすると自動でデプロイされる。パーミッションレス。
  - https://developer.offchainlabs.com/docs/bridging_assets
2. Arbitrumトークンリスト
  - CMCにリストする

### zkSync

