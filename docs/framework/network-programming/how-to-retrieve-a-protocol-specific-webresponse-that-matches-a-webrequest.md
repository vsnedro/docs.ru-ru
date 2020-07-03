---
title: Практическое руководство. Получение объекта WebResponse, соответствующего объекту WebRequest, для определенного протокола
description: Узнайте, как получить объект WebResponse, соответствующий объекту WebRequest, для определенного протокола в .NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: 15b1912a7bd951df7f3c14eb96251c2bdf237b4f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502461"
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
