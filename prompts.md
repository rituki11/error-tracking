# 🚀 AIコード生成用プロンプト集 (AI Prompt Library)

## ✅ 1️⃣ 投資データ分析ツールのコードを生成する
【目的】  
市場データを分析し、特定のセクターの資金流入を可視化する  

【要件】  
- **データ取得:** `yfinance` を使用  
- **欠損値処理:** `dropna()` または `fillna()` を実装  
- **カラムチェック:** `print(df.columns)` を事前に実行  
- **エラーハンドリング:** `try-except` を使用  
- **可視化:** `matplotlib` または `seaborn` でグラフ作成  
- **Colab環境で実行可能:** `!pip install` コマンド不要  

---

## ✅ 2️⃣ XGBoostを使った機械学習モデルを作成する
【目的】  
過去の株価リターンデータを用いて、翌日のリターンが日経平均を上回るか予測  

【要件】  
- **特徴量エンジニアリング:** `Lag` や `SMA`, `RSI` を含める  
- **データの分割:** `train_test_split` を使用  
- **ハイパーパラメータ調整:** `GridSearchCV` を使う  
- **評価指標:** `accuracy_score`, `roc_auc_score` を算出  
- **エラーハンドリング:** `except ValueError as e: print(f"Error: {e}")` を含める  
