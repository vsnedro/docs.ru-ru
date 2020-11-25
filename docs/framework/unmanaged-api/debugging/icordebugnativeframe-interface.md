---
title: Интерфейс ICorDebugNativeFrame
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame
helpviewer_keywords:
- ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type:
- apiref
ms.openlocfilehash: 043dc0fdd5218d7bc6b80428d1eb891b3f01ee8c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695560"
---
# <a name="icordebugnativeframe-interface"></a>Интерфейс ICorDebugNativeFrame

Специализированная реализация ICorDebugFrame, используемая для кадров машинного кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CanSetIP](icordebugnativeframe-cansetip-method.md)|Возвращает значение, указывающее, может ли быть ненадежным устанавливать указатель инструкции на указанное расположение смещения в машинном коде.|  
|[Метод GetIP](icordebugnativeframe-getip-method.md)|Возвращает смещение кадра стека в машинный код.|  
|[Метод GetLocalDoubleRegisterValue](icordebugnativeframe-getlocaldoubleregistervalue-method.md)|Возвращает указатель на объект ICorDebugValue, представляющий значение аргумента или локальной переменной, хранящейся в двух регистрах памяти в машинном кадре.|  
|[Метод GetLocalMemoryRegisterValue](icordebugnativeframe-getlocalmemoryregistervalue-method.md)|Возвращает указатель на объект `ICorDebugValue` , представляющий значение локальной переменной, для которой младшие биты хранятся в указанном регистре, а старшие биты хранятся по указанному адресу памяти.|  
|[Метод GetLocalMemoryValue](icordebugnativeframe-getlocalmemoryvalue-method.md)|Возвращает указатель на объект `ICorDebugValue` , представляющий значение локальной переменной, хранящейся по указанному адресу памяти.|  
|[Метод GetLocalRegisterMemoryValue](icordebugnativeframe-getlocalregistermemoryvalue-method.md)|Возвращает указатель на объект `ICorDebugValue` , представляющий значение локальной переменной, для которой старшие биты хранятся в указанном регистре, а младшие биты хранятся по указанному адресу памяти.|  
|[Метод GetLocalRegisterValue](icordebugnativeframe-getlocalregistervalue-method.md)|Возвращает указатель на объект `ICorDebugValue` , представляющий значение аргумента или локальную переменную, хранящуюся в указанном собственном регистре.|  
|[Метод GetRegisterSet](icordebugnativeframe-getregisterset-method.md)|Возвращает указатель на объект [ICorDebugRegisterSet](icordebugregisterset-interface.md) , представляющий набор регистров для этого объекта `ICorDebugNativeFrame` .|  
|[Метод SetIP](icordebugnativeframe-setip-method.md)|Задает указатель инструкции в указанном расположении смещения в машинном коде.|  
  
## <a name="remarks"></a>Комментарии  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
