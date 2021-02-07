---
description: 'Дополнительные сведения о: интерфейс ICorDebugEnum'
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
ms.openlocfilehash: 20d2bb14bddcaf40802567ec78a8e318ac1db380
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694478"
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
  
## <a name="remarks"></a>Remarks  

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
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
