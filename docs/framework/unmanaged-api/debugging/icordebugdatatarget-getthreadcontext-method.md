---
title: Метод ICorDebugDataTarget::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetThreadContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type:
- apiref
ms.openlocfilehash: 79708aa5a2abcb8d7465f82a8beb918484c193b9
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976555"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a>Метод ICorDebugDataTarget::GetThreadContext
Возвращает текущий контекст потока для указанного потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a>Параметры  
 `dwThreadID`  
 окне Идентификатор потока, контекст которого должен быть получен. Идентификатор определяется операционной системой.  
  
 `contextFlags`  
 окне Побитовое сочетание флагов, зависящих от платформы, которые указывают, какие части контекста должны считываться.  
  
 `contextSize`  
 [входной] Размер `pContext`.  
  
 `pContext`  
 заполняет Буфер, в котором будет храниться контекст потока.  
  
## <a name="remarks"></a>Remarks  
 На платформах Windows `pContext` должна быть `CONTEXT` структура (определенная в Winnt. h), подходящая для типа компьютера, указанного в методе [ICorDebugDataTarget::-Platform](icordebugdatatarget-getplatform-method.md) . `contextFlags`должны иметь те же значения, что `ContextFlags` и поле `CONTEXT` структуры. `CONTEXT` Структура зависит от конкретного процессора; Дополнительные сведения см. в файле WinNT. h.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugDataTarget](icordebugdatatarget-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
