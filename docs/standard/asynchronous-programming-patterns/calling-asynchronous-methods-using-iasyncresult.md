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
# <a name="calling-asynchronous-methods-using-iasyncresult"></a><span data-ttu-id="69bbf-102">Вызов асинхронных методов с помощью IAsyncResult</span><span class="sxs-lookup"><span data-stu-id="69bbf-102">Calling Asynchronous Methods Using IAsyncResult</span></span>
<span data-ttu-id="69bbf-103">Типы в .NET Framework и библиотеках классов сторонних разработчиков могут предоставлять методы, позволяющие приложению продолжать работу при выполнении асинхронных операций в потоках, отличных от основного потока приложения.</span><span class="sxs-lookup"><span data-stu-id="69bbf-103">Types in the .NET Framework and third-party class libraries can provide methods that allow an application to continue executing while performing asynchronous operations in threads other than the main application thread.</span></span> <span data-ttu-id="69bbf-104">В следующих разделах описаны и предоставлены примеры кода, которые демонстрируют разные способы вызова асинхронных методов, соответствующих шаблону проектирования <xref:System.IAsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="69bbf-104">The following sections describe and provide code examples that demonstrate the different ways you can call asynchronous methods that use the <xref:System.IAsyncResult> design pattern.</span></span>  
  
- <span data-ttu-id="69bbf-105">[Блокировка выполнения приложения путем завершения асинхронной операции](blocking-application-execution-by-ending-an-async-operation.md).</span><span class="sxs-lookup"><span data-stu-id="69bbf-105">[Blocking Application Execution by Ending an Async Operation](blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
- <span data-ttu-id="69bbf-106">[Блокировка выполнения приложения с помощью AsyncWaitHandle](blocking-application-execution-using-an-asyncwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="69bbf-106">[Blocking Application Execution Using an AsyncWaitHandle](blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
- <span data-ttu-id="69bbf-107">[Запрос состояния асинхронной операции](polling-for-the-status-of-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="69bbf-107">[Polling for the Status of an Asynchronous Operation](polling-for-the-status-of-an-asynchronous-operation.md).</span></span>  
  
- <span data-ttu-id="69bbf-108">[Использование делегата AsyncCallback для завершения асинхронной операции](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="69bbf-108">[Using an AsyncCallback Delegate to End an Asynchronous Operation](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69bbf-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="69bbf-109">See also</span></span>

- [<span data-ttu-id="69bbf-110">Асинхронная модель на основе событий (EAP)</span><span class="sxs-lookup"><span data-stu-id="69bbf-110">Event-based Asynchronous Pattern (EAP)</span></span>](event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="69bbf-111">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="69bbf-111">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)
