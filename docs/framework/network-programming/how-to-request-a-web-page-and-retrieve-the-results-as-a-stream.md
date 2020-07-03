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
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a>Практическое руководство. Запрос веб-страницы и получение результатов в виде потока

В этом примере показано, как запросить веб-страницу и получить результаты в виде потока.
  
## <a name="example"></a>Пример

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

## <a name="compiling-the-code"></a>Компиляция кода

 Для этого примера требуются:

- Ссылки на пространства имен <xref:System.IO> и <xref:System.Net>.

## <a name="see-also"></a>См. также

- [Запрос данных](requesting-data.md)
