# 🚀 エラー管理ログ (Error Tracking Log)

## **1️⃣ KeyError: '^N225_return'**
📌 **発生日時:** 2025-02-26  
📌 **原因:** yfinanceのデータのカラム名が変更されていた  
📌 **解決策:**  
- 事前に `print(df.columns)` でカラム名を確認
- `df.rename(columns={"^N225_return": "nikkei_return"}, inplace=True)`

---

## **2️⃣ ValueError: 配列サイズ不一致**
📌 **発生日時:** 2025-02-25  
📌 **原因:** `X_train` と `y_train` のサイズが一致していない  
📌 **解決策:**  
- `print(X_train.shape, y_train.shape)` でサイズを確認
- `X_train, y_train = X_train[:len(y_train)], y_train` に修正

---

**🛠 エラーが発生したら、ここに記録しよう！**
