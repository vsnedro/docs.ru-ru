---
description: 'Дополнительные сведения о методе: Икордебугстакквалк:: NOFRAMES'
title: Метод ICorDebugStackWalk::GetFrame
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetFrame
helpviewer_keywords:
- GetFrame method [.NET Framework debugging]
- ICorDebugStackWalk::GetFrame method [.NET Framework debugging]
ms.assetid: 4083b505-5b59-44fb-8c5d-129db6a96c10
topic_type:
- apiref
ms.openlocfilehash: b00ddb6a475aff4263a922f5a20b866cd0e1b2ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794745"
---
# <a name="icordebugstackwalkgetframe-method"></a>Метод ICorDebugStackWalk::GetFrame

Возвращает текущий кадр в объекте [икордебугстакквалк](icordebugstackwalk-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a>Параметры  

 `pFrame`  
 окне Указатель на адрес созданного объекта Frame, представляющий текущий кадр в стеке.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Среда выполнения успешно вернула текущий кадр.|  
|E_FAIL|Текущий кадр не был возвращен.|  
|S_FALSE|Текущий кадр является машинным кадром стека.|  
|E_INVALIDARG|Параметр `pFrame` имеет значение null.|  
|CORDBG_E_PAST_END_OF_STACK|Указатель фрейма уже находится в конце стека; Поэтому доступ к дополнительным кадрам невозможен.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Remarks  

 `ICorDebugStackWalk` Возвращает только фактические кадры стека. Используйте метод [ICorDebugThread3:: жетактивеинтерналфрамес](icordebugthread3-getactiveinternalframes-method.md) для возврата внутренних кадров. (Внутренние кадры — это структуры данных, помещаемые в стек средой выполнения для хранения временных данных.)  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugStackWalk](icordebugstackwalk-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
