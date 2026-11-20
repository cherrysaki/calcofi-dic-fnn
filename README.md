# CalCOFI DIC 予測（順伝播型ニューラルネット）

Kaggle コンペ [EDS 232 Ocean Chemistry Prediction for CalCOFI](https://www.kaggle.com/competitions/eds-232-ocean-chemistry-prediction-for-calcofi) で、海水の溶存無機炭素（DIC）を順伝播型ニューラルネットで予測したノートブックです。

| | Public | Private |
|---|---|---|
| RMSE | 4.07272 | 4.49282 |

## ファイル

- `実装課題①.ipynb`：学習から提出ファイル作成までのノートブック
- `submission.csv`：提出した予測

## 手法

- モデル：全結合 15 → 128 → 64 → 1、ReLU
- 入力：train / test に共通する15列を標準化
- 損失：平均絶対誤差（目的変数は学習時に標準化）
- 最適化：AdamW、ウォームアップ＋コサインアニーリング、400 エポック
- 予測：初期値を変えた 20 個のモデルの平均
- 5-fold 交差検証の RMSE：5.03

## 実行

コンペのデータ（`train.csv`、`test.csv`、`sample_submission.csv`）はこのリポジトリに含めていません。Kaggle 上で実行するか、3つのファイルをノートブックと同じフォルダに置いて実行してください。
