<!--
Meta Description: # SQLのMERGE文: 効率的なデータの挿入・更新・削除手法 ## 概要 SQLのMERGE文は、データベースにおけるデータの挿入、更新、削除を一つのコマンドで効率的に行うための機能です。特に、ターゲットテーブルとソースデータを比較し、条件に応じて異なる操作を実行する際に役立ちます。 ## ドキ...
Meta Keywords: source, target, when, matched, then
-->

# SQLのMERGE文: 効率的なデータの挿入・更新・削除手法

## 概要
SQLのMERGE文は、データベースにおけるデータの挿入、更新、削除を一つのコマンドで効率的に行うための機能です。特に、ターゲットテーブルとソースデータを比較し、条件に応じて異なる操作を実行する際に役立ちます。

## ドキュメント
### 目的
MERGE文は、複数のデータ操作を一度に実行することで、パフォーマンスを向上させ、トランザクションの複雑さを軽減します。これにより、データの一貫性を保ちながら、処理を効率化できます。

### 使用法
MERGE文は、以下の基本構文で構成されています。

```sql
MERGE INTO target_table AS target
USING source_table AS source
ON target.key_column = source.key_column
WHEN MATCHED THEN
    UPDATE SET target.column1 = source.column1, target.column2 = source.column2
WHEN NOT MATCHED THEN
    INSERT (column1, column2) VALUES (source.column1, source.column2)
WHEN NOT MATCHED BY SOURCE THEN
    DELETE;
```

### 詳細
- **ターゲットテーブル**: データを更新または削除するテーブル。
- **ソーステーブル**: 挿入または更新するデータを提供するテーブル。
- **ON句**: ターゲットとソースを関連付ける条件を指定します。
- **WHEN MATCHED**: 対象の行が存在する場合の処理（更新）。
- **WHEN NOT MATCHED**: 対象の行が存在しない場合の処理（挿入）。
- **WHEN NOT MATCHED BY SOURCE**: ソースに存在しない行を削除する処理。

## 例
### 基本的な使用例

#### 更新と挿入
```sql
MERGE INTO employees AS target
USING new_employees AS source
ON target.employee_id = source.employee_id
WHEN MATCHED THEN
    UPDATE SET target.salary = source.salary
WHEN NOT MATCHED THEN
    INSERT (employee_id, name, salary) VALUES (source.employee_id, source.name, source.salary);
```

#### 削除
```sql
MERGE INTO employees AS target
USING new_employees AS source
ON target.employee_id = source.employee_id
WHEN NOT MATCHED BY SOURCE THEN
    DELETE;
```

## 説明
### 一般的な落とし穴
1. **条件の不一致**: `ON`句で指定した条件が誤っていると、意図しない行が更新または削除される可能性があります。
2. **トランザクションの影響**: MERGE文はトランザクションとして扱われるため、大量のデータを扱う際には、パフォーマンスに影響が出ることがあります。
3. **NULL値の取り扱い**: NULL値が含まれる場合、比較が期待通りに動作しないことがありますので注意が必要です。

### 追加の注意点
- 使用するデータベースシステムによって、MERGE文の実装や機能に若干の違いがあるため、事前にドキュメントを確認することをお勧めします。

## 一文要約
SQLのMERGE文は、ターゲットテーブルとソースデータを比較し、条件に応じてデータの挿入、更新、削除を効率的に行える強力なコマンドです。