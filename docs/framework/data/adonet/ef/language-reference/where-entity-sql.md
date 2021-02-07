---
description: 'Дополнительные сведения о: WHERE (Entity SQL)'
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: e094a93927f6ac77aef772654f1d8d4fcf999cbd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712874"
---
# <a name="where-entity-sql"></a>WHERE (Entity SQL)

Предложение WHERE применяется непосредственно после предложения [from](from-entity-sql.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a>Аргументы  

 `expression`  
 Тип Boolean.  
  
## <a name="remarks"></a>Remarks  

 В предложении WHERE есть та же семантика, которая описана для Transact-SQL. Она ограничивает набор объектов, полученный выражением запроса, выбирая из исходной коллекции только те элементы, которые соответствуют условию.  
  
```sql  
select c from cs as c where e  
```  
  
 Выражение `e` должно иметь тип Boolean.  
  
 Предложение WHERE применяется непосредственно после предложения FROM, до выполнения любого группирования, упорядочения или проекции. Все имена элементов, определенные в предложении FROM, доступны в выражении предложения WHERE.  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
- [Выражения запросов](query-expressions-entity-sql.md)
