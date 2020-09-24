---
title: Практическое руководство. Как возвращать наборы строк
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
ms.openlocfilehash: be03107db73ed230a87c2518e7825461afc2bc7b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155748"
---
# <a name="how-to-return-rowsets"></a>Практическое руководство. Как возвращать наборы строк

В данном примере показано возвращение набора строк из базы данных и включение входного параметра в результаты фильтрации.  
  
 При выполнении хранимой процедуры, возвращающей набор строк, используется *результирующий* класс, хранящий возвращаемые результаты из хранимой процедуры. Дополнительные сведения см. в разделе [анализ исходного кода LINQ to SQL](analyzing-linq-to-sql-source-code.md).  
  
## <a name="example"></a>Пример  

 В следующем примере представлена хранимая процедура, которая возвращает строки клиентов и использует входной параметр для возврата только тех строк, в которых "Лондон" указан как город клиентов. В примере предполагается использование перечислимого класса `CustomersByCityResult`.  
  
```sql  
CREATE PROCEDURE [dbo].[Customers By City]  
    (@param1 NVARCHAR(20))  
AS  
BEGIN  
    -- SET NOCOUNT ON added to prevent extra result sets from  
    -- interfering with SELECT statements.  
    SET NOCOUNT ON;  
    SELECT CustomerID, ContactName, CompanyName, City from Customers  
        as c where c.City=@param1  
END  
```  
  
 [!code-csharp[DLinqSprox#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#1)]
 [!code-vb[DLinqSprox#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#1)]  
  
## <a name="see-also"></a>См. также раздел

- [Хранимые процедуры](stored-procedures.md)
- [Загрузка примеров баз данных](downloading-sample-databases.md)
