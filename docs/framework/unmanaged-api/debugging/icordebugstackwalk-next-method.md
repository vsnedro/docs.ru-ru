---
description: 'Дополнительные сведения о методе: Икордебугстакквалк:: Next'
title: Метод ICorDebugStackWalk::Next
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::Next
helpviewer_keywords:
- ICorDebugStackWalk::Next method [.NET Framework debugging]
- Next method, ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 189c36be-028c-4fba-a002-5edfb8fcd07f
topic_type:
- apiref
ms.openlocfilehash: 27a48ca40f6b43cae32511b71b73e68d88eb60c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717762"
---
# <a name="icordebugstackwalknext-method"></a>Метод ICorDebugStackWalk::Next

Перемещает объект [икордебугстакквалк](icordebugstackwalk-interface.md) в следующий кадр.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Среда выполнения успешно развернута до следующего кадра (см. примечания).|  
|E_FAIL|`ICorDebugStackWalk`Объект не может быть расширен.|  
|CORDBG_S_AT_END_OF_STACK|В результате этого очистки достигнут конец стека.|  
|CORDBG_E_PAST_END_OF_STACK|Указатель фрейма уже находится в конце стека; Поэтому доступ к дополнительным кадрам невозможен.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Remarks  

 `Next`Метод перемещает `ICorDebugStackWalk` объект в вызывающий кадр только в том случае, если среда выполнения может очистить текущий кадр. В противном случае объект переходит к следующему кадру, который среда выполнения может очистить.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugStackWalk](icordebugstackwalk-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
