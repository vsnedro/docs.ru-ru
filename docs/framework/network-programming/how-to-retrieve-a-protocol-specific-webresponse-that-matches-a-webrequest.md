---
title: Практическое руководство. Получение объекта WebResponse, соответствующего объекту WebRequest, для определенного протокола
description: Узнайте, как получить объект WebResponse, соответствующий объекту WebRequest, для определенного протокола в .NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: 920704bedce478ed5a4f7906379a634a3b2a4e31
ms.sourcegitcommit: f0fc5db7bcbf212e46933e9cf2d555bb82666141
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/17/2021
ms.locfileid: "100584346"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a>Практическое руководство. Получение объекта WebResponse, соответствующего объекту WebRequest, для определенного протокола

В этом примере показано, как получить объект WebResponse, соответствующий объекту WebRequest, для определенного протокола.  
  
## <a name="example"></a>Пример  
  
```csharp  
HttpWebRequest req = (HttpWebRequest)WebRequest.Create("http://www.contoso.com/");
HttpWebResponse resp = (HttpWebResponse)req.GetResponse();
```  
  
```vb  
Dim req As HttpWebRequest = CType(WebRequest.Create("http://www.contoso.com"), HttpWebRequest)
Dim resp As HttpWebResponse = CType(req.GetResponse(), HttpWebResponse)
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  

 Для этого примера требуются:  
  
- Ссылки на пространство имен **System.Net**.  
  
## <a name="see-also"></a>См. также

- [Запрос данных](requesting-data.md)
