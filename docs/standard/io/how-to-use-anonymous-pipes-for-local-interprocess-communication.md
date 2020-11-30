---
title: Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами
description: Узнайте, как использовать анонимные каналы для локального взаимодействия между процессами на локальном компьютере в .NET. Анонимные каналы требуют меньше ресурсов, чем именованные.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- anonymous pipes [.NET]
- parent-child communication [.NET]
- pipes [.NET]
- one-way communication [.NET]
- local computer communication [.NET], pipes
ms.assetid: e7773c77-c646-4a01-8a96-a003d59fc4c9
ms.openlocfilehash: 389451d1c6c313ac4a10652c7aa614a5e4e7bf1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734560"
---
# <a name="how-to-use-anonymous-pipes-for-local-interprocess-communication"></a>Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами

Анонимные каналы обеспечивают межпроцессное взаимодействие на локальном компьютере. Они предоставляют меньше возможностей, чем именованные каналы, но требуют меньше ресурсов. С помощью анонимных каналов вы можете легко организовать межпроцессное взаимодействие на локальном компьютере. Анонимные каналы не подходят для обмена данными по сети.  
  
 Для реализации анонимных каналов используются классы <xref:System.IO.Pipes.AnonymousPipeServerStream> и <xref:System.IO.Pipes.AnonymousPipeClientStream>.  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как отправить строку из родительского процесса в дочерний процесс через анонимные каналы. В этом примере создается объект <xref:System.IO.Pipes.AnonymousPipeServerStream> в родительском процессе, в котором параметру <xref:System.IO.Pipes.PipeDirection> задано значение <xref:System.IO.Pipes.PipeDirection.Out>. Затем родительский процесс создает дочерний процесс, используя дескриптор клиента для создания объекта <xref:System.IO.Pipes.AnonymousPipeClientStream>. В дочернем процессе <xref:System.IO.Pipes.PipeDirection> имеет значение <xref:System.IO.Pipes.PipeDirection.In>.  
  
 Теперь родительский процесс отправляет предоставленную пользователем строку в дочерний процесс. Эта строка выводится в консоль дочернего процесса.  
  
 Ниже представлен серверный процесс для этого примера.  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/vb/program.vb#01)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]
  
## <a name="example"></a>Пример  

 Ниже представлен клиентский процесс для этого примера. Серверный процесс запускает клиентский процесс и передает ему дескриптор клиента. Полученному исполняемому файлу в коде клиентского процесса следует присвоить имя `pipeClient.exe` и сохранить его в том же каталоге, где расположен исполняемый файл серверного процесса, прежде чем запускать серверный процесс.  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/vb/program.vb#01)]  
  
## <a name="see-also"></a>См. также

- [Каналы](pipe-operations.md)
- [Практическое руководство. Использование именованных каналов для сетевого взаимодействия между процессами](how-to-use-named-pipes-for-network-interprocess-communication.md)
