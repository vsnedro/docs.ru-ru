---
description: 'Дополнительные сведения о: TOP (Entity SQL)'
title: TOP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4a4a0954-82e2-4eae-bcaf-7c4552f3532d
ms.openlocfilehash: 51e4ce53cff4b47f6f57b6b856ccb09b38e639cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673444"
---
# <a name="top-entity-sql"></a>TOP (Entity SQL)

Предложение SELECT может иметь необязательное вложенное предложение TOP, которое следует за необязательным модификатором ALL/DISTINCT. Предложение TOP указывает, что в результатах запроса возвращается только набор первых строк.

## <a name="syntax"></a>Синтаксис

```sql
[ TOP (n) ]
```

## <a name="arguments"></a>Аргументы

`n` Числовое выражение, задающее количество возвращаемых строк. `n` может быть одним числовым литералом или одним параметром.

## <a name="remarks"></a>Remarks

Выражение TOP должно быть одним числовым литералом или одним параметром. При использовании постоянного литерала он должен поддерживать неявное повышение до Edm.Int64 (byte, int16, int32 и int64 или любой тип поставщика, который сопоставляется с типом, поддерживающим повышение до Edm.Int64), а его значение должно быть больше или равно нулю. В противном случае возникнет исключение. Если в качестве выражения используется параметр, то тип параметра также должен поддерживать неявное повышение до Edm.Int64, однако проверка фактического значения параметра во время компиляции проводиться не будет, поскольку значения параметров связываются в режиме позднего связывания.

Ниже приведен пример постоянного выражения TOP:

```sql
select distinct top(10) c.a1, c.a2 from T as a
```

Ниже приведен пример параметризованного выражения TOP:

```sql
select distinct top(@topParam) c.a1, c.a2 from T as a
```

Выражение TOP является недетерминированным, если запрос не отсортирован. При необходимости в детерминированном результате используйте вложенные предложения [SKIP](skip-entity-sql.md) и [LIMIT](limit-entity-sql.md) в предложении [ORDER BY](order-by-entity-sql.md) . Предложения TOP и SKIP/LIMIT являются взаимоисключающими.

## <a name="example"></a>Пример

В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] для указания верхней строки, которую следует вернуть из результата запроса, используется выражение TOP. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.

1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).

2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :

    [!code-sql[DP EntityServices Concepts#TOP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#top)]

## <a name="see-also"></a>См. также

- [SELECT](select-entity-sql.md)
- [СРАЗУ](skip-entity-sql.md)
- [Размер](limit-entity-sql.md)
- [ORDER BY](order-by-entity-sql.md)
- [Справочник по Entity SQL](entity-sql-reference.md)
