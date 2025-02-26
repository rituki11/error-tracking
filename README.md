# 🚀 エラー防止チェックリスト (Error Prevention Checklist)

## ✅ 1️⃣ カラムエラー (`KeyError`) を防ぐ
🔹 `print(df.columns)` でカラム一覧を確認する  
🔹 `if "target_column" not in df.columns:` を使ってカラムがあるかチェックする  
🔹 `df.rename(columns={"old_name": "new_name"}, inplace=True)` を活用する  

## ✅ 2️⃣ 配列サイズ (`ValueError`) をチェックする
🔹 `print(X_train.shape, y_train.shape)` でサイズを事前に確認する  
🔹 `assert X_train.shape[0] == y_train.shape[0], "データサイズが一致しません"` を追加する  

## ✅ 3️⃣ 例外処理 (`try-except`) を入れる
🔹 `try-except` を使って、エラー発生時に `print(e)` でエラーログを出す  
🔹 `except KeyError as e:` でカラムエラーをキャッチする  

---

**📌 コードを書く前に、このリストを確認してから実装しよう！** 🚀
