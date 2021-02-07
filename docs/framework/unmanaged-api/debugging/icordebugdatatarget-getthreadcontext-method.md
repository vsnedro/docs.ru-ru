---
description: 'Дополнительные сведения о методе: ICorDebugDataTarget:: GetThreadContext'
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
ms.openlocfilehash: cf40579aa0a495af4e5e775334d177ca6f3da86f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710638"
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

 На платформах Windows `pContext` должна быть `CONTEXT` Структура (определенная в Winnt. h), подходящая для типа компьютера, указанного в методе [ICorDebugDataTarget::-Platform](icordebugdatatarget-getplatform-method.md) . `contextFlags` должны иметь те же значения, что и `ContextFlags` поле `CONTEXT` структуры. `CONTEXT`Структура зависит от конкретного процессора; дополнительные сведения см. в файле WINNT. h.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugDataTarget](icordebugdatatarget-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
