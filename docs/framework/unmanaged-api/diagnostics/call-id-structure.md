---
title: Структура CALL_ID
ms.date: 03/30/2017
api_name:
- CALL_ID
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- CALL_ID
helpviewer_keywords:
- CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type:
- apiref
ms.openlocfilehash: 3f41dd969e25f7a42308ff0b7b2d617344284b38
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725252"
---
# <a name="call_id-structure"></a>Структура CALL_ID

Предоставляет сведения отладчику о вызываемой функции. Дополнительные сведения см. в интерфейсе [INotifySink2](inotifysink2-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`szMachine`|Идентифицирует компьютер, выполняющий вызов.|  
|`dwPid`|Идентифицирует процессор компьютера.|  
|`pUserThread`|Идентифицирует поток, который исполняет вызов.|  
|`addrStackPointer`|Задает адрес стека вызовов.|  
|`szEntryPoint`|Задает адрес вызова.|  
|`szDestinationMachine`|Определяет компьютер, который будет выполнять вызов.|  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс INotifySink2](inotifysink2-interface.md)
- [Структуры хранилища символов диагностики](diagnostics-symbol-store-structures.md)
