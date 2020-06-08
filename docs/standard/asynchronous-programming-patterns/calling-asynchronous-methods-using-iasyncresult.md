---
title: Вызов асинхронных методов с помощью IAsyncResult
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ending asynchronous operations
- waiting for asynchronous operations
- asynchronous method calling
- calling asynchronous methods
- asynchronous programming, calling asynchronous methods
- IAsyncResult interface, calling asynchronous methods
- stopping asynchronous operations
ms.assetid: 07fba116-045b-473c-a0b7-acdbeb49861f
ms.openlocfilehash: 88ca1b5bfbb8bfbdfef01dea8af07c5d56784c5c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289919"
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a>Вызов асинхронных методов с помощью IAsyncResult
Типы в .NET Framework и библиотеках классов сторонних разработчиков могут предоставлять методы, позволяющие приложению продолжать работу при выполнении асинхронных операций в потоках, отличных от основного потока приложения. В следующих разделах описаны и предоставлены примеры кода, которые демонстрируют разные способы вызова асинхронных методов, соответствующих шаблону проектирования <xref:System.IAsyncResult>.  
  
- [Блокировка выполнения приложения путем завершения асинхронной операции](blocking-application-execution-by-ending-an-async-operation.md).  
  
- [Блокировка выполнения приложения с помощью AsyncWaitHandle](blocking-application-execution-using-an-asyncwaithandle.md).  
  
- [Запрос состояния асинхронной операции](polling-for-the-status-of-an-asynchronous-operation.md).  
  
- [Использование делегата AsyncCallback для завершения асинхронной операции](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="see-also"></a>См. также раздел

- [Асинхронная модель на основе событий (EAP)](event-based-asynchronous-pattern-eap.md)
- [Обзор асинхронной модели, основанной на событиях](event-based-asynchronous-pattern-overview.md)
