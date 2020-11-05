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
# <a name="canceling-threads-cooperatively"></a>Согласованная отмена потоков

До версии .NET Framework 4 платформа .NET не предоставляла встроенных средств согласованной отмены потока после его запуска. Однако, начиная с .NET Framework 4, вы можете использовать <xref:System.Threading.CancellationToken?displayProperty=nameWithType> для отмены потоков точно так же, как и для отмены объектов <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> или запросов PLINQ. Хотя класс <xref:System.Threading.Thread?displayProperty=nameWithType> не обеспечивает встроенную поддержку токенов отмены, токен можно передать процедуре потока с помощью конструктора <xref:System.Threading.Thread> , принимающего делегат <xref:System.Threading.ParameterizedThreadStart> . В следующем примере показано, как это сделать.  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a>См. также раздел

- [Использование потоков и работа с потоками](using-threads-and-threading.md)
