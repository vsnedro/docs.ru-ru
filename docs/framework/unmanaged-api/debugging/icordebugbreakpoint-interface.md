---
title: Интерфейс ICorDebugBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
ms.openlocfilehash: 0c84a91c7da553d0c84a4995b4744576d861dcb9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730205"
---
# <a name="icordebugbreakpoint-interface"></a>Интерфейс ICorDebugBreakpoint

Представляет точку останова в функции или точку контрольного значения.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Activate](icordebugbreakpoint-activate-method.md)|Задает активное состояние этого объекта `ICorDebugBreakpoint` .|  
|[Метод IsActive](icordebugbreakpoint-isactive-method.md)|Возвращает значение, указывающее, является ли этот объект `ICorDebugBreakpoint` активным.|  
  
## <a name="remarks"></a>Комментарии  

 Точки останова не поддерживают непосредственно условные выражения. Если требуется такая функциональность, отладчик должен реализовать его поверх `ICorDebugBreakpoint` .  
  
 Интерфейс ICorDebugFunctionBreakpoint расширяется `ICorDebugBreakpoint` для поддержки точек останова в функциях.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
