<!--
Meta Description: # دمج البيانات في SQL: فهم أوامر MERGE ## الملخص أمر MERGE في SQL هو تقنية متقدمة تُستخدم لدمج البيانات من جدولين أو أكثر بناءً على شروط معينة، مما يس...
Meta Keywords: source, البيانات, when, matched, merge
-->

# دمج البيانات في SQL: فهم أوامر MERGE

## الملخص
أمر MERGE في SQL هو تقنية متقدمة تُستخدم لدمج البيانات من جدولين أو أكثر بناءً على شروط معينة، مما يسمح بإجراء تحديثات وإدخالات وحذف البيانات في عملية واحدة.

## الوثائق
### الغرض
أمر MERGE يُستخدم لتسهيل عمليات الدمج بين الجداول، حيث يمكن من خلاله تحديث البيانات الموجودة وإضافة بيانات جديدة في جدول مستهدف بناءً على البيانات من جدول مصدر. هذا يُزيد من كفاءة الأداء ويقلل من التعقيد في كتابة استعلامات متعددة.

### الاستخدام
يتم استخدام أمر MERGE على النحو التالي:

```sql
MERGE INTO target_table AS target
USING source_table AS source
ON target.id = source.id
WHEN MATCHED THEN
    UPDATE SET target.column1 = source.column1, target.column2 = source.column2
WHEN NOT MATCHED THEN
    INSERT (column1, column2) VALUES (source.column1, source.column2)
WHEN NOT MATCHED BY SOURCE THEN
    DELETE;
```

### التفاصيل
- **target_table**: هو الجدول الذي تريد دمج البيانات فيه.
- **source_table**: هو الجدول الذي يحتوي على البيانات الجديدة أو المحدثة.
- **ON**: تحدد الشرط الذي يجب أن يتطابق مع البيانات في الجداول.
- **WHEN MATCHED**: يُستخدم لتحديد الإجراءات التي يجب اتخاذها عندما تتطابق البيانات.
- **WHEN NOT MATCHED**: يُستخدم للإشارة إلى ما يجب فعله عندما لا توجد مطابقة في الجدول المستهدف.
- **WHEN NOT MATCHED BY SOURCE**: يُشير إلى الإجراءات التي يجب اتخاذها عندما لا توجد مطابقة في جدول المصدر.

## الأمثلة
### مثال 1: تحديث وإدخال بيانات
```sql
MERGE INTO employees AS target
USING new_employees AS source
ON target.employee_id = source.employee_id
WHEN MATCHED THEN
    UPDATE SET target.salary = source.salary
WHEN NOT MATCHED THEN
    INSERT (employee_id, name, salary) VALUES (source.employee_id, source.name, source.salary);
```

### مثال 2: حذف بيانات غير متطابقة
```sql
MERGE INTO inventory AS target
USING latest_inventory AS source
ON target.item_id = source.item_id
WHEN MATCHED THEN
    UPDATE SET target.quantity = source.quantity
WHEN NOT MATCHED THEN
    INSERT (item_id, quantity) VALUES (source.item_id, source.quantity)
WHEN NOT MATCHED BY SOURCE THEN
    DELETE;
```

## الشرح
### الأخطاء الشائعة
1. **عدم وجود شروط مناسبة**: من الضروري التأكد من وجود شروط صحيحة في عبارة ON لتجنب نتائج غير متوقعة.
2. **عدم التعامل مع الحقول الفريدة**: يجب توخي الحذر عند دمج البيانات التي يمكن أن تحتوي على قيود فريدة، حيث قد تؤدي إلى أخطاء.
3. **فهم سلوك DELETE**: عند استخدام WHEN NOT MATCHED BY SOURCE، يجب التأكد من فهم كيفية تأثير حذف البيانات على الجداول.

### ملاحظات إضافية
- يُفضل اختبار استعلامات MERGE في بيئة تطوير قبل تنفيذها في الإنتاج.
- يمكن أن يؤثر أداء MERGE على الجداول الكبيرة، لذا يُفضل استخدامه بحذر.

## ملخص جملة واحدة
أمر MERGE في SQL يُتيح دمج البيانات بكفاءة من جدولين أو أكثر، مما يُسهّل تحديث وإدخال وحذف البيانات في خطوة واحدة.