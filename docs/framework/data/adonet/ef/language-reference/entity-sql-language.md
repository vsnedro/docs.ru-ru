---
title: Язык Entity SQL
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: 2600b7626ebc5196c702f2d1e3159fd9549227f7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553386"
---
# <a name="entity-sql-language"></a>Язык Entity SQL
Entity SQL представляет собой независимый от хранилища язык запросов, аналогичный языку SQL. Entity SQL позволяет выполнять запросы к данным сущности, представленным либо в виде объектов, либо в табличной форме. Возможность использования Entity SQL необходимо рассматривать в следующих случаях:  
  
- Если запрос должен создаваться динамически во время выполнения. В этом случае следует также рассмотреть возможность использования методов построителя запросов <xref:System.Data.Objects.ObjectQuery%601> вместо создания строки запроса Entity SQL во время выполнения.  
  
- Если требуется определить запрос как часть определения модели. В модели данных поддерживается только Entity SQL. Дополнительные сведения см. в разделе [QueryView Element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl) .  
  
- Если EntityClient применяется для возврата допускающих только для чтения данных сущности в виде наборов строк с использованием <xref:System.Data.EntityClient.EntityDataReader>. Дополнительные сведения см. [в разделе Поставщик EntityClient для Entity Framework](../entityclient-provider-for-the-entity-framework.md).  
  
- Для специалиста по языкам запросов на основе SQL язык Entity SQL может оказаться самым естественным выбором.  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a>Использование Entity SQL с поставщиком EntityClient  
 Если требуется использовать Entity SQL с поставщиком EntityClient, см. дополнительные сведения в следующих разделах:  
  
 [Поставщик EntityClient для Entity Framework](../entityclient-provider-for-the-entity-framework.md)  
  
 [Практическое руководство. Сборка строки соединения EntityConnection](../how-to-build-an-entityconnection-connection-string.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего типы-примитивы](../how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего результаты типа StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего результаты RefType](../how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего сложные типы](../how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего вложенные коллекции](../how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Практическое руководство. Выполнение SQL-запроса к параметрическому объекту с использованием EntityCommand](../how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Практическое руководство. Выполнение параметризованной хранимой процедуры с использованием EntityCommand](../how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Практическое руководство. Выполнение полиморфного запроса](../how-to-execute-a-polymorphic-query.md)  
  
 [Практическое руководство. Переход по отношениям с помощью оператора Navigate](../how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a>Использование Entity SQL с запросами объектов  
 Если требуется использовать Entity SQL с запросами объектов, см. дополнительные сведения в следующих разделах:  
  
 [Практическое руководство. Выполнение запроса, возвращающего объекты типа сущностей](/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))  
  
 [Практическое руководство. Выполнение параметризованного запроса](/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))  
  
 [Практическое руководство. Навигация по отношениям с помощью свойств навигации](/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))  
  
 [Практическое руководство. Вызов пользовательских функций](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))  
  
 [Практическое руководство. Фильтрация данных](/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))  
  
 [Практическое руководство. Сортировка данных](/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))  
  
 [Практическое руководство. Группировка данных](/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))  
  
 [Практическое руководство. Агрегирование данных](/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))  
  
 [Практическое руководство. Выполнение запроса, возвращающего объекты анонимного типа](/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))  
  
 [Практическое руководство. Выполнение запроса, возвращающего коллекцию примитивных типов](/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))  
  
 [Практическое руководство. Запросы связанных объектов в EntityCollection](/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))  
  
 [Практическое руководство. Порядок объединения двух запросов](/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))  
  
 [Практическое руководство. Разбивка на страницы результатов запроса](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))  
  
## <a name="in-this-section"></a>в этом разделе  
 [Общие сведения об Entity SQL](entity-sql-overview.md)  
  
 [Справочник по Entity SQL](entity-sql-reference.md)  
  
## <a name="see-also"></a>См. также

- [ADO.NET Entity Framework](../index.md)
- [Справочник по языку](index.md)
