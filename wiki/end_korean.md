<!--
Meta Description: # SQL의 END 명령어: 사용법과 예시 ## 개요 SQL에서 `END` 명령어는 다양한 제어 흐름 구조에서 사용되며, 주로 `CASE` 문, `BEGIN...END` 블록과 같은 구문에서 코드 블록의 종료를 나타냅니다. 이 명령어는 SQL 스크립트의 가독성을 높이고...
Meta Keywords: end, sql, case, begin, 명령어는
-->

# SQL의 END 명령어: 사용법과 예시

## 개요
SQL에서 `END` 명령어는 다양한 제어 흐름 구조에서 사용되며, 주로 `CASE` 문, `BEGIN...END` 블록과 같은 구문에서 코드 블록의 종료를 나타냅니다. 이 명령어는 SQL 스크립트의 가독성을 높이고, 특정 논리적 구조를 명확히 하기 위해 필수적입니다.

## 문서화
### 목적
`END` 명령어는 SQL의 여러 구조에서 블록의 끝을 정의하는 데 사용됩니다. 이를 통해 SQL 서버는 해당 블록이 종료되었음을 인지하고, 이후의 SQL 문을 올바르게 해석할 수 있습니다.

### 사용법
- **CASE 문에서의 사용**: `CASE` 문은 조건에 따라 다른 결과를 반환할 수 있는 구조로, 각 조건의 종료를 `END`로 표시합니다.
- **BEGIN...END 블록에서의 사용**: 여러 SQL 문을 그룹화하여 트랜잭션을 정의하거나 프로시저를 작성할 때 사용됩니다.

### 세부정보
- `END`는 SQL 문법의 일부로 필수적인 요소이며, 적절한 구문 구조를 유지하는 데 중요합니다.
- SQL에서 `END`는 대소문자를 구분하지 않으므로 `end`, `End`와 같이 작성하더라도 동일한 의미를 가집니다.

## 예시
### CASE 문 예시
```sql
SELECT 
    CASE 
        WHEN score >= 90 THEN 'A'
        WHEN score >= 80 THEN 'B'
        WHEN score >= 70 THEN 'C'
        ELSE 'F'
    END AS grade
FROM students;
```

### BEGIN...END 블록 예시
```sql
BEGIN
    DECLARE @total INT;
    SET @total = (SELECT SUM(amount) FROM transactions);
    PRINT @total;
END;
```

## 설명
`END` 명령어를 사용하는 데 있어 몇 가지 주의할 점이 있습니다:
- `END`가 필요하지 않은 곳에 사용하면 문법 오류가 발생할 수 있습니다.
- `BEGIN`과 `END` 블록 내의 SQL 문장들이 올바른 순서로 작성되어야 하며, 그 구조에 따라 `END`의 위치도 달라질 수 있습니다.
- `CASE` 문에서는 각 조건을 닫기 위해 반드시 `END`를 사용해야 하며, 이를 누락할 경우 오류가 발생합니다.

## 한 줄 요약
SQL에서 `END` 명령어는 제어 흐름 구조의 종료를 정의하는 필수 요소입니다.