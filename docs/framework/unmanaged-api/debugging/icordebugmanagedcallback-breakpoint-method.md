---
title: Метод ICorDebugManagedCallback::Breakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Breakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Breakpoint
helpviewer_keywords:
- ICorDebugManagedCallback::Breakpoint method [.NET Framework debugging]
- Breakpoint method [.NET Framework debugging]
ms.assetid: 60b279b0-a726-46d2-8c53-76986a007ebb
topic_type:
- apiref
ms.openlocfilehash: d7cf966f407572cc681f641b63791906a5c015f3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731869"
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a>Метод ICorDebugManagedCallback::Breakpoint

Уведомляет отладчик об обнаружении точки останова.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pAppDomain`  
 окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий точку останова.  
  
 `pThread`  
 окне Указатель на объект ICorDebugThread, представляющий поток, содержащий точку останова.  
  
 `pBreakpoint`  
 окне Указатель на объект Икордебугбреакпоинт, представляющий точку останова.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
