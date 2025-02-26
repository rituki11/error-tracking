# 🚀 **エラー管理ログ (Error Tracking Log)**  
**📌 目的:**  
このログは、過去のエラーとその解決策を記録し、AI がコードを書く際に同じエラーを繰り返さないようにするためのものです。  
コードを生成する際には、このリストを考慮し、エラーを未然に防ぐ実装を行ってください。  

---

## **🛠 1️⃣ KeyError: `'^N225_return'`**
📌 **発生日時:** 2025-02-26  
📌 **原因:**  
- `yfinance` から取得したデータのカラム名が変更されていた  
- 変更後のカラム名 (`nikkei_return`) を使わず、古いカラム (`^N225_return`) を参照していた  

📌 **解決策:**  
✅ `print(df.columns)` を実行して、カラム名を確認する  
✅ `df.rename(columns={"^N225_return": "nikkei_return"}, inplace=True)` を実装する  
✅ `if "nikkei_return" not in df.columns:` のように事前チェックを行う  

**📌 🔥 **今後の AI コード生成では、カラム変更に対応するために** 🔥**  
- `df.columns` を必ずチェックするコードを含める  
- 変数名を動的に変更する `rename()` を適用する  

---

## **🛠 2️⃣ ValueError: 配列サイズ不一致**
📌 **発生日時:** 2025-02-25  
📌 **原因:**  
- `X_train` と `y_train` のサイズが一致していなかった  
- `train_test_split()` のパラメータが正しく設定されていなかった  

📌 **解決策:**  
✅ `print(X_train.shape, y_train.shape)` でサイズを事前に確認する  
✅ `assert X_train.shape[0] == y_train.shape[0], "データサイズが一致しません"` を実装する  
✅ `train_test_split()` の `random_state=42` を明示的に指定する  

**📌 🔥 **今後の AI コード生成では、データサイズのチェックを必ず組み込む！ 🔥**  
- `assert` 文を使い、`X_train.shape[0] == y_train.shape[0]` を強制チェック  
- `train_test_split()` の `test_size` を適切に設定する  

---

## **🛠 3️⃣ AttributeError: `'DataFrame' object has no attribute 'to_frame'`**
📌 **発生日時:** 2025-02-24  
📌 **原因:**  
- `xlk` のデータ型が `DataFrame` ではなく `Series` だった  
- `to_frame()` を使おうとしたが、既に `DataFrame` だったためエラー発生  

📌 **解決策:**  
✅ `if isinstance(xlk, pd.Series): xlk = xlk.to_frame(name="XLK")` を実装  
✅ `type(xlk)` をチェックして、事前に型を確認する  

**📌 🔥 **今後の AI コード生成では、データ型のチェックを自動化する！ 🔥**  
- `isinstance()` で `Series` か `DataFrame` か判定する  
- 必要に応じて `.to_frame()` を適用する  

---

## **📌 🔥 AIへの指示：**
✅ AI はこの `error-tracking.md` の内容を考慮して、**同じエラーを起こさないようなコードを生成すること！**  
✅ **事前チェック（カラム名, データサイズ, 型チェック）を必ず含めること！**  
✅ **エラーが発生した場合の `try-except` を適切に実装すること！**  

---

📌 **🔥 AI にコードを書かせる際には、常にこのエラー管理ログを渡すこと！🔥**
