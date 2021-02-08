---
description: Дополнительные сведения о типах данных и функциях
title: Типы данных и функции
ms.date: 03/30/2017
ms.assetid: 683413c5-0312-4e60-8619-9a97bdc6e62a
ms.openlocfilehash: 5a718d5fd4b110d35153e4486e42cee0b8a215bd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786151"
---
# <a name="data-types-and-functions"></a>Типы данных и функции

Перечисленные в следующей таблице разделы описывают поддержку в LINQ to SQL элементов, конструкций и приведения среды CLR. Поддерживаемые элементы и конструкции доступны для использования в запросах LINQ to SQL.  
  
 Если в таблице элемент отмечен как неподдерживаемый, то LINQ to SQL не может перевести этот элемент, конструкцию или приведение типов среды CLR для выполнения на SQL Server. Их по-прежнему можно использовать в коде, но вычислять их следует или до преобразования запроса в Transact-SQL, или после получения результатов из базы данных.  
  
|Раздел|Описание|  
|-----------|-----------------|  
|[Сопоставление типов SQL-CLR](sql-clr-type-mapping.md)|Содержит таблицу с подробными сведениями о сопоставлении между типами CLR и типами SQL Server.|  
|[Базовые типы данных](basic-data-types.md)|Суммирует различия в поведении платформа .NET Framework.|  
|[Логические типы данных](boolean-data-types.md)|Суммирует различия в поведении платформа .NET Framework.|  
|[Семантика null](null-semantics.md)|Приведены ссылки на разделы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], посвященные обсуждению значений NULL и связанных с ними вопросов.|  
|[Числовые операторы и операторы сравнения](numeric-and-comparison-operators.md)|Суммирует различия в поведении платформа .NET Framework.|  
|[Операторы последовательности](sequence-operators.md)|Суммирует различия в поведении платформа .NET Framework.|  
|[Методы System.Convert](system-convert-methods.md)|Суммирует различия в поведении платформа .NET Framework.|  
|[Методы System.DateTime](system-datetime-methods.md)|Описана поддержка в LINQ to SQL элементов структуры <xref:System.DateTime?displayProperty=nameWithType>.|  
|[Методы System.DateTimeOffset](system-datetimeoffset-methods.md)|Описана поддержка в LINQ to SQL элементов структуры <xref:System.DateTimeOffset?displayProperty=nameWithType>.|  
|[Методы System.Math](system-math-methods.md)|Суммирует различия в поведении платформа .NET Framework.|  
|[Методы System.Object](system-object-methods.md)|Суммирует различия в поведении платформа .NET Framework.|  
|[Методы System.String](system-string-methods.md)|Суммирует различия в поведении платформа .NET Framework.|  
|[Методы System.TimeSpan](system-timespan-methods.md)|Описана поддержка в LINQ to SQL элементов структуры <xref:System.TimeSpan?displayProperty=nameWithType>.|  
|[Неподдерживаемые функциональные возможности](unsupported-functionality.md)|Описаны функции, которые не поддерживаются в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].|  
  
## <a name="see-also"></a>См. также

- [Несоответствия типов SQL-CLR](sql-clr-type-mismatches.md)
- [Ссылки](reference.md)
