---
description: 'Дополнительные сведения о: интерфейс ICorDebugThread3'
title: Интерфейс ICorDebugThread3
ms.date: 03/30/2017
api_name:
- ICorDebugThread3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3
helpviewer_keywords:
- ICorDebugThread3 interface [.NET Framework debugging]
ms.assetid: eb2860ef-06cb-4968-a6c3-6d048ecda2a4
topic_type:
- apiref
ms.openlocfilehash: 88c668f1e08d0843f26d231937c85d80e03bee6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800972"
---
# <a name="icordebugthread3-interface"></a>Интерфейс ICorDebugThread3

Предоставляет точку входа для [икордебугстакквалк](icordebugstackwalk-interface.md) и соответствующих интерфейсов.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateStackWalk](icordebugthread3-createstackwalk-method.md)|Создает объект [икордебугстакквалк](icordebugstackwalk-interface.md) для потока, стек которого нужно очистить.|  
|[Метод GetActiveInternalFrames](icordebugthread3-getactiveinternalframes-method.md)|Возвращает массив внутренних кадров (объектов[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) ) в стеке.|  
  
## <a name="remarks"></a>Remarks  

 `ICorDebugThread3` является логическим расширением для интерфейса ICorDebugThread.  
  
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
