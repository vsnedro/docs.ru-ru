---
description: 'Дополнительные сведения: Навигация (Entity SQL)'
title: NAVIGATE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
ms.openlocfilehash: 7fa39a988429fe0a658b01078d2369ad4767f4a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696507"
---
# <a name="navigate-entity-sql"></a>NAVIGATE (Entity SQL)

Производит переход по связи, установленной между сущностями.

## <a name="syntax"></a>Синтаксис

```sql
navigate(instance-expression, [relationship-type], [to-end [, from-end] ])
```

## <a name="arguments"></a>Аргументы

`instance-expression` Экземпляр сущности.

`relationship-type` Имя типа связи из CSDL-файла языка определения схемы. `relationship-type`Является полным именем \<namespace> . \<relationship type name>

`to` Конец связи.

`from` Начало связи.

## <a name="return-value"></a>Возвращаемое значение

Если количество элементов в конечной составляющей связи равно 1, то будет возвращено значение `Ref<T>`. Если же количество элементов в конечной составляющей связи равно n, то будет возвращено значение `Collection<Ref<T>>`.

## <a name="remarks"></a>Remarks

Связи — это конструкции первого класса в EDM (EDM). Связи могут устанавливаться между двумя или несколькими типами сущностей, а пользователи могут переходить по связи от одного элемента (от одной сущности) к другому. `from` и `to` являются необязательными при том условии, что нет неоднозначности в разрешении имен в пределах связи.

Оператор NAVIGATE является допустимым в пространствах O и C.

Конструкция перехода имеет следующую общую форму.

navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )

Пример:

```sql
Select o.Id, navigate(o, OrderCustomer, Customer, Order)
From LOB.Orders as o
```

Здесь OrderCustomer является значением параметра `relationship`, а Customer и Order являются элементами связи `to-end` (customer) и `from-end` (order). Если Ордеркустомер является отношением n:1, то тип результата выражения Navigate — ref \<Customer> .

Для этого выражение существует следующая упрощенная форма.

```sql
Select o.Id, navigate(o, OrderCustomer)
From LOB.Orders as o
```

Аналогично, в запросе следующей формы выражение Navigate будет создавать коллекцию<\<Order>> ссылок.

```sql
Select c.Id, navigate(c, OrderCustomer, Order, Customer)
From LOB.Customers as c
```

Выражение экземпляра должно иметь тип сущности или ссылки.

## <a name="example"></a>Пример

В следующем запросе Entity SQL оператор NAVIGATE используется для перехода по связи, заданной между типами сущностей Address и SalesOrderHeader. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.

1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).

2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :

 [!code-sql[DP EntityServices Concepts#NAVIGATE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#navigate)]

## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
- [Руководство. Переход по связям с помощью оператора Navigate](navigate-entity-sql.md)
