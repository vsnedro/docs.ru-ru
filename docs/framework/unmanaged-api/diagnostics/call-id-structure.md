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
ms.openlocfilehash: 1c795ee536483a7def9c0339efae66a013898a77
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420634"
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
  
## <a name="members"></a>Участники  
  
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
  
## <a name="see-also"></a>См. также статью

- [Интерфейс INotifySink2](inotifysink2-interface.md)
- [Структуры хранилища символов диагностики](diagnostics-symbol-store-structures.md)
