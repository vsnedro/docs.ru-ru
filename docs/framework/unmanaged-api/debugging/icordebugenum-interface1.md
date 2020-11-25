---
title: Интерфейс ICorDebugEnum
ms.date: 03/30/2017
api_name:
- ICorDebugEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum
helpviewer_keywords:
- ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type:
- apiref
ms.openlocfilehash: b208444de3b427329988f27b9d252b54143b7240
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698797"
---
# <a name="icordebugenum-interface"></a>Интерфейс ICorDebugEnum

Служит абстрактным базовым интерфейсом для перечислителей, используемых приложением отладки.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Clone](icordebugenum-clone-method.md)|Создает копию данного объекта `ICorDebugEnum`.|  
|[Метод GetCount](icordebugenum-getcount-method.md)|Возвращает число элементов в перечислении.|  
|[Метод Reset](icordebugenum-reset-method.md)|Перемещает курсор в начало перечисления.|  
|[Метод Skip](icordebugenum-skip-method.md)|Перемещает курсор вперед в перечислении на указанное число элементов.|  
  
## <a name="remarks"></a>Комментарии  

 Следующие перечислители являются производными от `ICorDebugEnum` :  
  
- "Икордебугаппдомаиненум"  
  
- ICorDebugAssemblyEnum  
  
- [ICorDebugBlockingObjectEnum](icordebugblockingobjectenum-interface.md)  
  
- ICorDebugBreakpointEnum  
  
- "Икордебугчаиненум"  
  
- "Икордебугкодинум"  
  
- ICorDebugErrorInfoEnum  
  
- [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md)  
  
- ICorDebugFrameEnum  
  
- [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md)  
  
- [ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md)  
  
- [икордебугхеапенум](icordebugheapenum-interface.md)  
  
- [икордебугхеапсегментенум](icordebugheapsegmentenum-interface.md)  
  
- "Икордебугмодулинум"  
  
- "Икордебугобжектенум"  
  
- "Икордебугпроцессенум"  
  
- "Икордебугстепперенум"  
  
- "Икордебугсреаденум"  
  
- ICorDebugTypeEnum  
  
- ICorDebugValueEnum  
  
- [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
