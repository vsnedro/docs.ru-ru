---
title: Метод ICorDebugStackWalk::GetContext
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type:
- apiref
ms.openlocfilehash: 927f2077b4bb71177c24816774d06643ebdaa922
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711966"
---
# <a name="icordebugstackwalkgetcontext-method"></a>Метод ICorDebugStackWalk::GetContext

Возвращает контекст для текущего кадра в объекте [икордебугстакквалк](icordebugstackwalk-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `contextFlags`  
 окне Флаги, указывающие запрошенное содержимое буфера контекста (определенного в WinNT. h).  
  
 `contextBufSize`  
 окне Выделенный размер буфера контекста.  
  
 `contextSize`  
 заполняет Фактический размер контекста. Это значение должно быть меньше или равно размеру буфера контекста.  
  
 `contextBuf`  
 заполняет Буфер контекста.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Контекст для текущего кадра успешно возвращен.|  
|E_FAIL|Не удалось вернуть контекст.|  
|HRESULT_FROM_WIN32 (БУФЕР ERROR_INSUFFICIENT)|Буфер контекста слишком мал.|  
|CORDBG_E_PAST_END_OF_STACK|Указатель фрейма уже находится в конце стека; Поэтому доступ к дополнительным кадрам невозможен.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Remarks  

 Поскольку при очистке восстанавливаются только подмножество регистров, например непостоянные регистры, контекст может точно не соответствовать состоянию регистрации во время вызова.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
