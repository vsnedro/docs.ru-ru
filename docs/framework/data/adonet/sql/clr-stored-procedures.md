---
title: Хранимые процедуры CLR
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: aa14c96ed226ac80a9613d3e229f35dbf5085f3b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173618"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="335fa-102">Хранимые процедуры CLR</span><span class="sxs-lookup"><span data-stu-id="335fa-102">CLR Stored Procedures</span></span>

<span data-ttu-id="335fa-103">Хранимыми процедурами являются процедуры, которые нельзя использовать в скалярных выражениях.</span><span class="sxs-lookup"><span data-stu-id="335fa-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="335fa-104">Они могут возвращать клиенту табличные результаты и сообщения, вызывать инструкции языка описания данных DDL и языка обработки данных DML, а также возвращать выходные параметры.</span><span class="sxs-lookup"><span data-stu-id="335fa-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="335fa-105">Microsoft Visual Basic не поддерживает выходные параметры так, как это сделано в Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="335fa-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="335fa-106">Необходимо указать для передачи параметра по ссылке и применения \<Out()> атрибута для представления выходного параметра, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="335fa-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
<span data-ttu-id="335fa-107">Более подробные сведения см. в версии [SQL Server документации](/sql) по используемой версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="335fa-107">For more detailed information, see the version of [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="335fa-108">**Документация по SQL Server**</span><span class="sxs-lookup"><span data-stu-id="335fa-108">**SQL Server documentation**</span></span>

1. <span data-ttu-id="335fa-109">[Хранимые процедуры CLR](/previous-versions/sql/sql-server-2008/ms131094(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="335fa-109">[CLR Stored Procedures](/previous-versions/sql/sql-server-2008/ms131094(v=sql.100))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="335fa-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="335fa-110">See also</span></span>

- <span data-ttu-id="335fa-111">[Создание объектов SQL Server 2005 в управляемом коде](/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="335fa-111">[Creating SQL Server 2005 Objects In Managed Code](/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span></span>
- [<span data-ttu-id="335fa-112">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="335fa-112">ADO.NET Overview</span></span>](../ado-net-overview.md)
