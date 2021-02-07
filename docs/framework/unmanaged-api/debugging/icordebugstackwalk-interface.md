---
description: 'Дополнительные сведения о: интерфейс Икордебугстакквалк'
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
ms.openlocfilehash: 27dcdfc90829a3a28d81ad28dce0cd4d1d674948
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738095"
---
# <a name="icordebugstackwalk-interface"></a>Интерфейс ICorDebugStackWalk

Обеспечивает методы для получения управляемых методов или кадров в стеке потока.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetContext](icordebugstackwalk-getcontext-method.md)|Возвращает контекст для текущего кадра в `ICorDebugStackWalk` объекте.|  
|[Метод SetContext](icordebugstackwalk-setcontext-method.md)|Задает `ICorDebugStackWalk` для текущего контекста объекта допустимый контекст для потока.|  
|[Следующий метод](icordebugstackwalk-next-method.md)|Перемещает `ICorDebugStackWalk` объект на следующий кадр.|  
|[Метод GetFrame](icordebugstackwalk-getframe-method.md)|Возвращает текущий кадр в `ICorDebugStackWalk` объекте.|  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
