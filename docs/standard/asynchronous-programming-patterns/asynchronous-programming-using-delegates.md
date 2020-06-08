---
title: Асинхронное программирование с использованием делегатов
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- BeginInvoke method
- asynchronous programming, delegates
- asynchronous delegates
- calling synchronous methods in asynchronous manner
- EndInvoke method
- calling asynchronous methods
- delegates [.NET Framework], asynchronous
- synchronous calling in asynchronous manner
ms.assetid: 38a345ca-6963-4436-9608-5c9defef9c64
ms.openlocfilehash: 82e0a57c3d8e180456aed48886e38ca466db16c8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289971"
---
# <a name="asynchronous-programming-using-delegates"></a>Асинхронное программирование с использованием делегатов
Делегаты позволяют вызывать синхронные методы асинхронно. При синхронном вызове делегата метод `Invoke` вызывает целевой метод непосредственно в текущем потоке. При вызове метода `BeginInvoke` среда CLR помещает запрос в очередь и сразу же передает управление вызывающему объекту. Целевой метод вызывается асинхронно в потоке из пула потоков. Исходный поток, отправивший этот запрос, продолжает выполняться параллельно с целевым методом. Если при вызове метода `BeginInvoke` был указан метод обратного вызова, то метод обратного вызова вызывается после завершения целевого метода. В методе обратного вызова метод `EndInvoke` получает возвращаемое значение и любые параметры ввода/вывода или только выходные параметры. Если при вызове `BeginInvoke` не указан метод обратного вызова, `EndInvoke` можно вызвать из потока, который вызвал `BeginInvoke`.  
  
> [!IMPORTANT]
> Компиляторы должны формировать классы делегатов с методами `Invoke`, `BeginInvoke`, и `EndInvoke` с использованием сигнатуры делегата, задаваемой пользователем. Методы `BeginInvoke` и `EndInvoke` должны быть объявлены как собственные. Поскольку эти методы помечены как собственные, среда CLR автоматически обеспечивает реализацию во время загрузки класса. Загрузчик проверяет, что эти методы не переопределены.  
  
## <a name="in-this-section"></a>Содержание  
 [Асинхронный вызов синхронных методов](calling-synchronous-methods-asynchronously.md)  
 Обсуждается использование делегатов для асинхронного вызова обычных методов, и приводятся примеры кода, демонстрирующие четыре способа ожидания возврата асинхронного вызова.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Асинхронная модель на основе событий (EAP)](event-based-asynchronous-pattern-eap.md)  
 Описывается асинхронное программирование в .NET Framework.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Delegate>
