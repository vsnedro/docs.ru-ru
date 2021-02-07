---
description: 'Дополнительные сведения: хранимые процедуры CLR'
title: Хранимые процедуры CLR
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: d136d3dcb12be2f87276a410c9fa0e713b7dfd52
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723625"
---
# <a name="clr-stored-procedures"></a>Хранимые процедуры CLR

Хранимыми процедурами являются процедуры, которые нельзя использовать в скалярных выражениях. Они могут возвращать клиенту табличные результаты и сообщения, вызывать инструкции языка описания данных DDL и языка обработки данных DML, а также возвращать выходные параметры.  
  
> [!NOTE]
> Microsoft Visual Basic не поддерживает выходные параметры так, как это сделано в Microsoft Visual C#. Необходимо указать для передачи параметра по ссылке и применения \<Out()> атрибута для представления выходного параметра, как показано ниже:  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
Более подробные сведения см. в версии [SQL Server документации](/sql) по используемой версии SQL Server.
  
 **Документация по SQL Server**

1. [Хранимые процедуры CLR](/previous-versions/sql/sql-server-2008/ms131094(v=sql.100))  
  
## <a name="see-also"></a>См. также

- [Создание объектов SQL Server 2005 в управляемом коде](/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))
- [Общие сведения об ADO.NET](../ado-net-overview.md)
