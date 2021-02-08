---
description: 'Дополнительные сведения: как использовать функции Scalar-Valued User-Defined'
title: Практическое руководство. Как применять определяемые пользователем скалярные функции
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
ms.openlocfilehash: e606dd3f840b8f082928217c6118b48d8d4a2e5c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785814"
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a>Практическое руководство. Как применять определяемые пользователем скалярные функции

Для сопоставления клиентского метода, определенного в классе, с пользовательской функцией используется атрибут <xref:System.Data.Linq.Mapping.FunctionAttribute>. Обратите внимание, что тело метода создает выражение, перехватывающее назначение вызова метода, и передает это выражение в <xref:System.Data.Linq.DataContext> для преобразования и выполнения.  
  
> [!NOTE]
> Прямое выполнение возможно только при вызове функции вне запроса. Дополнительные сведения см. [в разделе инструкции. вызов User-Defined функций встроенной функции](how-to-call-user-defined-functions-inline.md).  
  
## <a name="example"></a>Пример  

 В следующем коде SQL представлена скалярная пользовательская функция `ReverseCustName()`.  
  
```sql  
CREATE FUNCTION ReverseCustName(@string varchar(100))  
RETURNS varchar(100)  
AS  
BEGIN  
    DECLARE @custName varchar(100)  
    -- Implementation left as exercise for users.  
    RETURN @custName  
END  
```  
  
 Для этого кода следует отобразить клиентский метод, подобный следующему.  
  
 [!code-csharp[DLinqUDFS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#3)]
 [!code-vb[DLinqUDFS#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#3)]  
  
## <a name="see-also"></a>См. также

- [Определяемые пользователем функции](user-defined-functions.md)
