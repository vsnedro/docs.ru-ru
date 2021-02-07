---
description: 'Дополнительные сведения о: интерфейс Икордебугбреакпоинт'
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
ms.openlocfilehash: 63917512cceeccedea37acdf2ba7ab3b849d9fad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711808"
---
# <a name="icordebugbreakpoint-interface"></a>Интерфейс ICorDebugBreakpoint

Представляет точку останова в функции или точку контрольного значения.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Activate](icordebugbreakpoint-activate-method.md)|Задает активное состояние этого объекта `ICorDebugBreakpoint` .|  
|[Метод IsActive](icordebugbreakpoint-isactive-method.md)|Возвращает значение, указывающее, является ли этот объект `ICorDebugBreakpoint` активным.|  
  
## <a name="remarks"></a>Remarks  

 Точки останова не поддерживают непосредственно условные выражения. Если требуется такая функциональность, отладчик должен реализовать его поверх `ICorDebugBreakpoint` .  
  
 Интерфейс ICorDebugFunctionBreakpoint расширяется `ICorDebugBreakpoint` для поддержки точек останова в функциях.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
