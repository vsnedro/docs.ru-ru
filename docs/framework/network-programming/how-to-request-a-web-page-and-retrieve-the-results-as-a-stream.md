---
title: Практическое руководство. Запрос веб-страницы и получение результатов в виде потока
description: В этом примере показано, как запросить веб-страницу и получить результаты в виде потока в .NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: bd57f9af6be29c783d044e785ebb36aaa8592df2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502487"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="0af18-103">Практическое руководство. Запрос веб-страницы и получение результатов в виде потока</span><span class="sxs-lookup"><span data-stu-id="0af18-103">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>

<span data-ttu-id="0af18-104">В этом примере показано, как запросить веб-страницу и получить результаты в виде потока.</span><span class="sxs-lookup"><span data-stu-id="0af18-104">This example shows how to request a Web page and retrieve the results in a stream.</span></span>
  
## <a name="example"></a><span data-ttu-id="0af18-105">Пример</span><span class="sxs-lookup"><span data-stu-id="0af18-105">Example</span></span>

```csharp
var myClient = new WebClient();
Stream response = myClient.OpenRead("https://docs.microsoft.com/dotnet/");
// The stream data is used here.
response.Close();
```

```vb
Dim myClient As New WebClient()
Dim response As Stream = myClient.OpenRead("https://docs.microsoft.com/dotnet/")
' The stream data is used here.
response.Close()
```

## <a name="compiling-the-code"></a><span data-ttu-id="0af18-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="0af18-106">Compiling the Code</span></span>

 <span data-ttu-id="0af18-107">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="0af18-107">This example requires:</span></span>

- <span data-ttu-id="0af18-108">Ссылки на пространства имен <xref:System.IO> и <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="0af18-108">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>

## <a name="see-also"></a><span data-ttu-id="0af18-109">См. также</span><span class="sxs-lookup"><span data-stu-id="0af18-109">See also</span></span>

- [<span data-ttu-id="0af18-110">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="0af18-110">Requesting Data</span></span>](requesting-data.md)
