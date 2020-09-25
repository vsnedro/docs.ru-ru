---
title: REF CURSOR в Oracle
ms.date: 03/30/2017
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
ms.openlocfilehash: cbf330ba381a825c2d16038c01d7bdc52bc8f482
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180885"
---
# <a name="oracle-ref-cursors"></a>REF CURSOR в Oracle

Поставщик данных .NET Framework для Oracle поддерживает тип данных Oracle **ref Cursor** . При использовании поставщика данных для работы с данными типа REF CURSOR Oracle необходимо учитывать следующие особенности его функционирования.  
  
> [!NOTE]
> По некоторым особенностям функционирования он отличается от поставщика Microsoft OLE DB для Oracle (MSDAORA).  
  
- По соображениям производительности поставщик данных для Oracle не привязывает типы данных **ссылочных курсоров** автоматически, как если бы они явно не заданы.  
  
- Указанный поставщик данных не поддерживает никаких escape-последовательностей ODBC, включая escape-последовательность {resultset}, используемую для задания параметров REF CURSOR.  
  
- Для выполнения хранимой процедуры, возвращающей ссылки REF CURSOR, необходимо определить параметры в <xref:System.Data.OracleClient.OracleParameterCollection> с помощью <xref:System.Data.OracleClient.OracleType> **курсора** и <xref:System.Data.OracleClient.OracleParameter.Direction%2A> **выходных данных**. Этот поставщик данных поддерживает привязку данных типа REF CURSOR только в качестве выходных параметров. Этот поставщик не поддерживает данные типа REF CURSOR как входные параметры.  
  
- Получение модуля <xref:System.Data.OracleClient.OracleDataReader> из значения параметра не поддерживается. Значения имеют тип <xref:System.DBNull> после выполнения команды.  
  
- Единственным значением перечисления **CommandBehavior** , которое работает с КЛЮЧЕВЫМи курсорами (например, при вызове <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> ), является **клосеконнектион**; все остальные игнорируются.  
  
- Порядок ССЫЛОЧных КУРСОРов в **OracleDataReader** зависит от порядка параметров в **OracleParameterCollection**. Свойство <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> не учитывается.  
  
- **Табличный** тип данных PL/SQL не поддерживается. Но данные типа REF CURSOR являются более эффективными. Если необходимо использовать **табличный** тип данных, используйте поставщик данных OLE DB .NET с MSDAORA.  
  
## <a name="in-this-section"></a>в этом разделе  

 [Примеры REF CURSOR](ref-cursor-examples.md)  
 Содержит три примера, которые демонстрируют использование данных типа REF CURSOR.  
  
 [Параметры REF CURSOR в объекте OracleDataReader](ref-cursor-parameters-in-an-oracledatareader.md)  
 Демонстрирует выполнение хранимой процедуры PL/SQL, возвращающей параметр REF CURSOR, и считывание значения в виде **OracleDataReader**.  
  
 [Извлечение данных нескольких REF CURSOR с использованием OracleDataReader](retrieving-data-from-multiple-ref-cursors.md)  
 Демонстрирует выполнение хранимой процедуры PL/SQL, возвращающей два параметра REF CURSOR, и считывание значений с помощью **OracleDataReader**.  
  
 [Заполнение набора данных с помощью одного или нескольких параметров REF CURSOR](filling-a-dataset-using-one-or-more-ref-cursors.md)  
 Показывает, как выполнить хранимую процедуру PL/SQL, которая возвращает два параметра REF CURSOR и заполняет <xref:System.Data.DataSet> возвращаемыми строками.  
  
## <a name="see-also"></a>См. также раздел

- [Oracle и ADO.NET](oracle-and-adonet.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
