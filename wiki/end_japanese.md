<!--
Meta Description: # SQLにおける「END」コマンド：構文と使用法 ## 概要 「END」はSQLの制御フロー構造において、条件文やループの終了を示すために使用されるキーワードです。特に、PL/SQLやT-SQLなどのストアドプロシージャやトリガーの文脈で重要な役割を果たします。 ## ドキュメント 「END」は、...
Meta Keywords: end, dbms_output, put_line, v_counter, sql
-->

# SQLにおける「END」コマンド：構文と使用法

## 概要
「END」はSQLの制御フロー構造において、条件文やループの終了を示すために使用されるキーワードです。特に、PL/SQLやT-SQLなどのストアドプロシージャやトリガーの文脈で重要な役割を果たします。

## ドキュメント
「END」は、条件文（例えば、IF文）やループ（例えば、WHILE文）の終わりを明示するために使用されます。これにより、SQLエンジンは制御フローの境界を理解し、正確にコードを実行することができます。

### 用途
- **IF文の終了**: 条件が満たされた場合に実行されるコードブロックの終わりを示します。
- **LOOP文の終了**: 繰り返し処理の終わりを示すために使用されます。
- **CASE文の終了**: 複数の条件を評価する際に、CASE文の終了を示します。

### 詳細
SQLでは、「END」は特に以下のような場合に使われます。
- **IF文**: `IF`ステートメントを使用する際、その条件文の終わりを示します。
- **CASE文**: 複数の選択肢を持つ場合に、CASE文の終わりを示します。
- **LOOP文**: ループ構造の終わりを示します。

例:
```sql
IF condition THEN
    -- 処理
END IF;
```

## 例
### IF文の例
```sql
DECLARE
    v_number NUMBER := 10;
BEGIN
    IF v_number > 5 THEN
        DBMS_OUTPUT.PUT_LINE('5より大きい');
    ELSE
        DBMS_OUTPUT.PUT_LINE('5以下');
    END IF;
END;
```

### CASE文の例
```sql
DECLARE
    v_grade CHAR(1) := 'A';
BEGIN
    CASE v_grade
        WHEN 'A' THEN
            DBMS_OUTPUT.PUT_LINE('優');
        WHEN 'B' THEN
            DBMS_OUTPUT.PUT_LINE('良');
        ELSE
            DBMS_OUTPUT.PUT_LINE('可');
    END CASE;
END;
```

### LOOP文の例
```sql
DECLARE
    v_counter NUMBER := 1;
BEGIN
    LOOP
        DBMS_OUTPUT.PUT_LINE(v_counter);
        v_counter := v_counter + 1;
        EXIT WHEN v_counter > 5;
    END LOOP;
END;
```

## 説明
「END」コマンドを使用する際の一般的な落とし穴や注意点:
- **文法エラー**: 「END」を使用した後に適切な構文を維持しないと、エラーが発生することがあります。特に、IF文やCASE文では、必ず「END IF;」や「END CASE;」とする必要があります。
- **ネスト**: 複数のIF文やLOOP文がネストされている場合、どの「END」がどのブロックに対応しているのかを明確にするために、可読性に注意を払いましょう。インデントを適切に使用すると良いです。
- **データベース依存**: SQLの実装によっては、構文や機能が異なる場合がありますので、使用しているデータベースに特有のドキュメントを確認することが大切です。

## 一文の要約
SQLにおける「END」は、IF文、CASE文、LOOP文などの制御フロー構造の終了を示すための重要なキーワードです。