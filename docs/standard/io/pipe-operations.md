---
title: Операции с каналами в .NET
description: 'Сведения об операциях с каналами в .NET. Каналы предоставляют средства для межпроцессного взаимодействия. Существует два типа каналов: анонимные и именованные.'
ms.date: 03/30/2017
helpviewer_keywords:
- pipes [.NET]
- pipe operations [.NET]
- interprocess communication [.NET], pipes
- I/O [.NET], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
ms.openlocfilehash: 3ec4ee61bfd3a0a82eb0a0884b89c19a9300b078
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819101"
---
# <a name="pipe-operations-in-net"></a>Операции с каналами в .NET
Каналы предоставляют средства для межпроцессного взаимодействия. Существует два типа каналов.  
  
- Анонимные каналы.  
  
     Анонимные каналы обеспечивают межпроцессное взаимодействие на локальном компьютере. Анонимные каналы требуют меньше ресурсов, чем именованные каналы, но предоставляют меньше возможностей. Анонимные каналы являются односторонними и их нельзя использовать в сети. Они поддерживают только один экземпляр сервера. Анонимные каналы подходят для взаимодействия между потоками или между родительским и дочерним процессами, поскольку в этих сценариях дескриптор канала можно легко передать дочернему процессу при его создании.  
  
     В .NET анонимные каналы реализуются с помощью классов <xref:System.IO.Pipes.AnonymousPipeServerStream> и <xref:System.IO.Pipes.AnonymousPipeClientStream>.  
  
     См. практическое руководство по [ Использование анонимных каналов для локального взаимодействия между процессами](how-to-use-anonymous-pipes-for-local-interprocess-communication.md).  
  
- Именованные каналы.  
  
     Именованные каналы обеспечивают межпроцессное взаимодействие между сервером канала и одним или несколькими клиентами канала. Именованные каналы могут быть односторонним или дуплексным. Они поддерживают связь на основе сообщений и позволяют нескольким клиентам одновременно подключаться к одному серверному процессу через канал с тем же именем. Именованные каналы также поддерживают олицетворение, при котором подключенные процессы используют на удаленных серверах собственные разрешения доступа.  
  
     В .NET именованные каналы реализуются с помощью классов <xref:System.IO.Pipes.NamedPipeServerStream> и <xref:System.IO.Pipes.NamedPipeClientStream>.  
  
     См. практическое руководство по [ Использование именованных каналов для сетевого взаимодействия между процессами](how-to-use-named-pipes-for-network-interprocess-communication.md).  
  
## <a name="see-also"></a>См. также

- [Файловый и потоковый ввод-вывод](index.md)
- [Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами](how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
- [Практическое руководство. Использование именованных каналов для сетевого взаимодействия между процессами](how-to-use-named-pipes-for-network-interprocess-communication.md)
