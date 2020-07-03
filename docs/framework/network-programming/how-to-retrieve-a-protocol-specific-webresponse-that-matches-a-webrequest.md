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
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="c29c6-103">Практическое руководство. Получение объекта WebResponse, соответствующего объекту WebRequest, для определенного протокола</span><span class="sxs-lookup"><span data-stu-id="c29c6-103">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>
<span data-ttu-id="c29c6-104">В этом примере показано, как получить объект WebResponse, соответствующий объекту WebRequest, для определенного протокола.</span><span class="sxs-lookup"><span data-stu-id="c29c6-104">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c29c6-105">Пример</span><span class="sxs-lookup"><span data-stu-id="c29c6-105">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c29c6-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="c29c6-106">Compiling the Code</span></span>  
 <span data-ttu-id="c29c6-107">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="c29c6-107">This example requires:</span></span>  
  
- <span data-ttu-id="c29c6-108">Ссылки на пространство имен **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="c29c6-108">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c29c6-109">См. также</span><span class="sxs-lookup"><span data-stu-id="c29c6-109">See also</span></span>

- [<span data-ttu-id="c29c6-110">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="c29c6-110">Requesting Data</span></span>](requesting-data.md)
