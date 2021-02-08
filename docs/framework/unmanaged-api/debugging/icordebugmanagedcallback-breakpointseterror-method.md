---
description: 'Дополнительные сведения о методе: ICorDebugManagedCallback:: Бреакпоинтсетеррор'
title: Метод ICorDebugManagedCallback::BreakpointSetError
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.BreakpointSetError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::BreakpointSetError
helpviewer_keywords:
- BreakpointSetError method [.NET Framework debugging]
- ICorDebugManagedCallback::BreakpointSetError method [.NET Framework debugging]
ms.assetid: f2b773a4-c4d0-429c-9717-51d6e2ed86af
topic_type:
- apiref
ms.openlocfilehash: cf78b4dc06a71b6ac0eb4f653a00c1b3c6ae464b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791092"
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a>Метод ICorDebugManagedCallback::BreakpointSetError

Уведомляет отладчик о том, что среде CLR не удалось точно привязать точку останова, установленную до JIT-компиляции функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pAppDomain`  
 окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, который содержит несвязанную точку останова.  
  
 `pThread`  
 окне Указатель на объект ICorDebugThread, представляющий поток, содержащий несвязанную точку останова.  
  
 `pBreakpoint`  
 окне Указатель на объект Икордебугбреакпоинт, представляющий несвязанную точку останова.  
  
 `dwError`  
 окне Целое число, указывающее на ошибку.  
  
## <a name="remarks"></a>Remarks  

 Заданная точка останова никогда не будет достигнута. Отладчик должен деактивироваться и повторно привязывать его.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
