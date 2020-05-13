---
title: Интерфейс ICorDebugStackWalk
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
ms.openlocfilehash: 5f71dfcdffaaa683ca4f2abebaa99115ef90e0ff
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378908"
---
# <a name="icordebugstackwalk-interface"></a>Интерфейс ICorDebugStackWalk
Обеспечивает методы для получения управляемых методов или кадров в стеке потока.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetContext](icordebugstackwalk-getcontext-method.md)|Возвращает контекст для текущего кадра в `ICorDebugStackWalk` объекте.|  
|[Метод SetContext](icordebugstackwalk-setcontext-method.md)|Задает `ICorDebugStackWalk` для текущего контекста объекта допустимый контекст для потока.|  
|[Метод Next](icordebugstackwalk-next-method.md)|Перемещает `ICorDebugStackWalk` объект на следующий кадр.|  
|[Метод GetFrame](icordebugstackwalk-getframe-method.md)|Возвращает текущий кадр в `ICorDebugStackWalk` объекте.|  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
