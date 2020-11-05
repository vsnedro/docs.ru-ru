---
title: Согласованная отмена потоков
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
ms.openlocfilehash: 36de18e976401dd0cde878852c064aa982b8acde
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188501"
---
# <a name="canceling-threads-cooperatively"></a><span data-ttu-id="839d9-102">Согласованная отмена потоков</span><span class="sxs-lookup"><span data-stu-id="839d9-102">Canceling threads cooperatively</span></span>

<span data-ttu-id="839d9-103">До версии .NET Framework 4 платформа .NET не предоставляла встроенных средств согласованной отмены потока после его запуска.</span><span class="sxs-lookup"><span data-stu-id="839d9-103">Prior to .NET Framework 4, .NET provided no built-in way to cancel a thread cooperatively after it was started.</span></span> <span data-ttu-id="839d9-104">Однако, начиная с .NET Framework 4, вы можете использовать <xref:System.Threading.CancellationToken?displayProperty=nameWithType> для отмены потоков точно так же, как и для отмены объектов <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> или запросов PLINQ.</span><span class="sxs-lookup"><span data-stu-id="839d9-104">However, starting with .NET Framework 4, you can use a <xref:System.Threading.CancellationToken?displayProperty=nameWithType> to cancel threads, just as you can use them to cancel <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or PLINQ queries.</span></span> <span data-ttu-id="839d9-105">Хотя класс <xref:System.Threading.Thread?displayProperty=nameWithType> не обеспечивает встроенную поддержку токенов отмены, токен можно передать процедуре потока с помощью конструктора <xref:System.Threading.Thread> , принимающего делегат <xref:System.Threading.ParameterizedThreadStart> .</span><span class="sxs-lookup"><span data-stu-id="839d9-105">Although the <xref:System.Threading.Thread?displayProperty=nameWithType> class does not offer built-in support for cancellation tokens, you can pass a token to a thread procedure by using the <xref:System.Threading.Thread> constructor that takes a <xref:System.Threading.ParameterizedThreadStart> delegate.</span></span> <span data-ttu-id="839d9-106">В следующем примере показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="839d9-106">The following example demonstrates how to do this.</span></span>  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="839d9-107">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="839d9-107">See also</span></span>

- [<span data-ttu-id="839d9-108">Использование потоков и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="839d9-108">Using Threads and Threading</span></span>](using-threads-and-threading.md)
