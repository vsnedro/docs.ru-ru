---
description: 'Дополнительные сведения: семантика со значением NULL'
title: Семантика NULL
ms.date: 03/30/2017
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
ms.openlocfilehash: 2326cd20a225f31693260aa038477f1f6090d02f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695584"
---
# <a name="null-semantics"></a>Семантика NULL

В следующей таблице приведены ссылки на различные части [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] документации `null` , где `Nothing` обсуждаются проблемы (в Visual Basic).  
  
|Раздел|Описание|  
|-----------|-----------------|  
|[Несоответствия типов SQL-CLR](sql-clr-type-mismatches.md)|В подразделе "семантика со значением NULL" этого раздела описывается логическое значение SQL Boolean и два состояния среды CLR <xref:System.Boolean> , литерал `Nothing` (Visual Basic) и `null` (C#), а также другие аналогичные проблемы.|  
|[Трансляция стандартных операторов запросов](standard-query-operator-translation.md)|В подразделе "Семантика со значениями NULL" данного раздела описывается семантика сравнений со значением NULL в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].|  
|[Методы System.String](system-string-methods.md)|В подразделе "Отличия от платформы .NET" данного раздела описывается, каким образом значение 0, возвращенное методом <xref:System.String.LastIndexOf%2A> , может означать, что строка равна значению NULL либо найденная позиция равна 0.|  
|[Вычисление суммы значений в числовой последовательности](compute-the-sum-of-values-in-a-numeric-sequence.md)|Описывает, как <xref:System.Linq.Enumerable.Sum%2A> оператор вычисляет значение `null` ( `Nothing` в Visual Basic) вместо 0 для последовательности, содержащей только значения NULL или для пустой последовательности.|  
  
## <a name="see-also"></a>См. также

- [Типы данных и функции](data-types-and-functions.md)
