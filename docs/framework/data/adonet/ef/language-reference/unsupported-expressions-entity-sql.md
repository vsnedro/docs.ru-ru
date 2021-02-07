---
description: 'Дополнительные сведения: Неподдерживаемые выражения'
title: Не поддерживаемые выражения (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: ceb57dc78f9685a79de987d15f7fd57a583b75a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673301"
---
# <a name="unsupported-expressions"></a>Неподдерживаемые выражения

В этом разделе описываются выражения Transact-SQL, которые не поддерживаются в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Дополнительные сведения см. в разделе [Entity SQL отличается от языка Transact-SQL](how-entity-sql-differs-from-transact-sql.md).

## <a name="quantified-predicates"></a>Количественные предикаты

Transact-SQL позволяет создавать конструкции следующего вида:

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] такие конструкции не поддерживает. Эквивалентные выражения могут быть написаны на языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] следующим образом:

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a>* - оператор

Transact-SQL поддерживает использование оператора * в предложении SELECT для указания того, что все столбцы должны быть прогнозируемыми. Это не поддерживается в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .

## <a name="see-also"></a>См. также

- [Общие сведения об Entity SQL](entity-sql-overview.md)
- [Отличия Entity SQL от Transact-SQL](how-entity-sql-differs-from-transact-sql.md)
