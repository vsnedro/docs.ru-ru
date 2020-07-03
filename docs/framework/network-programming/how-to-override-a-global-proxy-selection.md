---
title: Практическое руководство. Переопределение глобальных прокси-серверов
description: Следуйте инструкциям в приведенном ниже примере, чтобы переопределить выбор глобального прокси-сервера путем отправки запроса на URL-адрес. При этом выделенный фрагмент переопределяется с помощью прокси-сервера.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 91f64775e2f401be9b740fe9e4c41e1087eb9617
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502513"
---
# <a name="how-to-override-a-global-proxy-selection"></a>Практическое руководство. Переопределение глобальных прокси-серверов
В этом примере класс **WebRequest** отправляется на веб-сайт `www.contoso.com`, который переопределяет глобальные прокси-серверы прокси-сервером с именем `alternateproxy` на порту 80.  
  
## <a name="example"></a>Пример  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- Директива [`using`](../../csharp/language-reference/keywords/using-directive.md) для пространства имен **System.Net**.  
  
## <a name="see-also"></a>См. также

- [Использование протоколов приложений](using-application-protocols.md)
- [Доступ к Интернету через прокси-сервер](accessing-the-internet-through-a-proxy.md)
