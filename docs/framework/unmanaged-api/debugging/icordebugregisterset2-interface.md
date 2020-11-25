---
title: Интерфейс ICorDebugRegisterSet2
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2
helpviewer_keywords:
- ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type:
- apiref
ms.openlocfilehash: c04bb3a7584fcb783af929e87713dbec67ad705f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712330"
---
# <a name="icordebugregisterset2-interface"></a>Интерфейс ICorDebugRegisterSet2

Расширяет возможности интерфейса [ICorDebugRegisterSet](icordebugregisterset-interface.md) для аппаратных платформ, имеющих более 64 регистров.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetRegisters](icordebugregisterset2-getregisters-method.md)|Возвращает значение каждого регистра (на компьютере, выполняющем в данный момент код), который задается битовой маской.|  
|[Метод GetRegistersAvailable](icordebugregisterset2-getregistersavailable-method.md)|Возвращает массив байтов, предоставляющий битовую карту доступных регистров.|  
|[Метод SetRegisters](icordebugregisterset2-setregisters-method.md)|Не реализовано в .NET Framework версии 2,0.|  
  
## <a name="remarks"></a>Комментарии  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
- [Интерфейс ICorDebugRegisterSet](icordebugregisterset-interface.md)
