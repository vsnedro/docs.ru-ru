---
title: Практическое руководство. Включение в WebRequest использования прокси-сервера для связи с Интернетом
description: Сведения о создании в .NET Framework экземпляра глобального прокси-сервера, который позволяет любому WebRequest использовать прокси-сервер для связи с Интернетом.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 0fc33cea3f5a7fe4669b110e53e71afdb9561c23
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502539"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a>Практическое руководство. Включение в WebRequest использования прокси-сервера для связи с Интернетом

В этом примере создается экземпляр глобального прокси-сервера, который позволяет любому <xref:System.Net.WebRequest> использовать прокси-сервер для связи с Интернетом. В этом примере предполагается, что сервер имеет имя `webproxy` и подключается к стандартному HTTP-порту 80.

## <a name="example"></a>Пример

```csharp
var proxyObject = new WebProxy("http://webproxy:80/");
GlobalProxySelection.Select = proxyObject;
```

```vb
Dim proxyObject As New WebProxy("http://webproxy:80/")
GlobalProxySelection.Select = proxyObject
```

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

- [Директива C# `using`](../../csharp/language-reference/keywords/using-directive.md) для пространства имен **System.Net**.
- [Инструкция Visual Basic `Imports`](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для пространств имен **System.Net**.

## <a name="see-also"></a>См. также

- [Использование протоколов приложений](using-application-protocols.md)
- [Доступ к Интернету через прокси-сервер](accessing-the-internet-through-a-proxy.md)
