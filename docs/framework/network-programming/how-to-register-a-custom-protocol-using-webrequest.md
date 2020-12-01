---
title: Практическое руководство. Регистрация пользовательского протокола с помощью WebRequest
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
ms.openlocfilehash: 86ad862dbff9f4a982eec27a6806bcbb6c16f3ae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255810"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a>Практическое руководство. Регистрация пользовательского протокола с помощью WebRequest

В этом примере показано, как зарегистрировать класс для конкретного протокола, который определен в другом месте. В этом примере `CustomWebRequestCreator` — пользовательский объект, который реализует метод **Create**, возвращающий объект `CustomWebRequest`. В примере кода предполагается, что вы написали код `CustomWebRequest`, который реализует пользовательский протокол.  
  
## <a name="example"></a>Пример  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  

 Для этого примера требуются:  
  
 Ссылки на пространство имен <xref:System.Net>.  
  
## <a name="see-also"></a>См. также раздел

- [Программирование подключаемых протоколов](programming-pluggable-protocols.md)
