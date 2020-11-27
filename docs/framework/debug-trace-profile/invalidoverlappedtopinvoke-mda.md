---
title: invalidOverlappedToPinvoke MDA
description: Ознакомьтесь с помощником по отладке управляемого кода (MDA) Инвалидоверлаппедтопинвоке в .NET, который может быть активирован при сбое или повреждении неустранимой кучи.
ms.date: 03/30/2017
helpviewer_keywords:
- overlapped pointers
- managed debugging assistants (MDAs), overlapped pointers
- invalid overlapped pointer to platform invoke
- InvalidOverlappedToPinvoke MDA
- MDAs (managed debugging assistants), overlapped pointers
- pointers, overlapped
ms.assetid: 28876047-58bd-4fed-9452-c7da346d67c0
ms.openlocfilehash: 55b10af87130bd32410508cef2bc3e4e733549c0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281329"
---
# <a name="invalidoverlappedtopinvoke-mda"></a>invalidOverlappedToPinvoke MDA

Помощник по отладке управляемого кода (MDA) `invalidOverlappedToPinvoke` активируется, когда перекрытый указатель, который не был создан в куче сбора мусора, передается конкретным функциям Win32.  
  
> [!NOTE]
> По умолчанию данный MDA активируется, только если в коде определен платформенный вызов, и отладчик сообщает о статусе JustMyCode для каждого метода. Отладчик, который не понимает JustMyCode (например, MDbg.exe без расширений), не будет активировать данный MDA. Этот MDA можно включить для таких отладчиков с помощью файла конфигурации и явно задав `justMyCode="false"` в файле .mda.config `(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`.  
  
## <a name="symptoms"></a>Симптомы  

 Сбои или необъяснимые повреждения кучи.  
  
## <a name="cause"></a>Причина:  

 Перекрытый указатель, который не был создан в куче сборки мусора, передается конкретным функциям операционной системы.  
  
 В следующей таблице приведены функции, отслеживаемые данным MDA.  
  
|Модуль|Функция|  
|------------|--------------|  
|HttpApi.dll|`HttpReceiveHttpRequest`|  
|IpHlpApi.dll|`NotifyAddrChange`|  
|kernel32.dll|`ReadFile`|  
|kernel32.dll|`ReadFileEx`|  
|kernel32.dll|`WriteFile`|  
|kernel32.dll|`WriteFileEx`|  
|kernel32.dll|`ReadDirectoryChangesW`|  
|kernel32.dll|`PostQueuedCompletionStatus`|  
|MSWSock.dll|`ConnectEx`|  
|WS2_32.dll|`WSASend`|  
|WS2_32.dll|`WSASendTo`|  
|WS2_32.dll|`WSARecv`|  
|WS2_32.dll|`WSARecvFrom`|  
|MQRT.dll|`MQReceiveMessage`|  
  
 Для этого условия велика вероятность повреждения кучи, так как делающий вызов <xref:System.AppDomain> может быть выгружен. В случае выгрузки <xref:System.AppDomain> код приложения либо освободит память для перекрытого указателя, что приведет к повреждению при завершении операции, либо произойдет утечка памяти, что приведет к проблемам в дальнейшем.  
  
## <a name="resolution"></a>Разрешение  

 Используйте объект <xref:System.Threading.Overlapped>, вызвав метод <xref:System.Threading.Overlapped.Pack%2A> для получения структуры <xref:System.Threading.NativeOverlapped>, которую можно передать в функцию. В случае выгрузки <xref:System.AppDomain> среда CLR ожидает завершения асинхронной операции, прежде чем освободить указатель.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  

 Этот помощник отладки управляемого кода не оказывал никакого влияния на среду CLR.  
  
## <a name="output"></a>Выходные данные  

 Ниже представлен пример выходных данных этого MDA.  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the Win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlapped structure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a>Конфигурация  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidOverlappedToPinvoke/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Диагностика ошибок посредством управляемых помощников по отладке](diagnosing-errors-with-managed-debugging-assistants.md)
- [Маршалинг взаимодействия](../interop/interop-marshaling.md)
