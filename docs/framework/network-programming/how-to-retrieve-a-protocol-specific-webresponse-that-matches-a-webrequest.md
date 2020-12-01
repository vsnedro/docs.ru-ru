---
title: Практическое руководство. Получение объекта WebResponse, соответствующего объекту WebRequest, для определенного протокола
description: Узнайте, как получить объект WebResponse, соответствующий объекту WebRequest, для определенного протокола в .NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: fd163c115dcd19c05f93f4c202b043440834ba9d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266744"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a>Практическое руководство. Получение объекта WebResponse, соответствующего объекту WebRequest, для определенного протокола

В этом примере показано, как получить объект WebResponse, соответствующий объекту WebRequest, для определенного протокола.  
  
## <a name="example"></a>Пример  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  

 Для этого примера требуются:  
  
- Ссылки на пространство имен **System.Net**.  
  
## <a name="see-also"></a>См. также

- [Запрос данных](requesting-data.md)
