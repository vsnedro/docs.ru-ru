---
title: Метод ICorDebugManagedCallback2::FunctionRemapComplete
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapComplete
helpviewer_keywords:
- FunctionRemapComplete method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapComplete method [.NET Framework debugging]
ms.assetid: 5396c4c3-4ec3-4e3a-a38d-d65b21f0a2fc
topic_type:
- apiref
ms.openlocfilehash: 7eb7fb55a5077d2914eb85a67ca62163a1aa8cc0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704608"
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a>Метод ICorDebugManagedCallback2::FunctionRemapComplete

Уведомляет отладчик о том, что выполнение кода переключено на новую версию измененной функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pAppDomain`  
 окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий измененную функцию.  
  
 `pThread`  
 окне Указатель на объект ICorDebugThread, представляющий поток, в котором была обнаружена точка останова сопоставления.  
  
 `pFunction`  
 окне Указатель на объект ICorDebugFunction, представляющий версию функции, выполняемой в данный момент в потоке.  
  
## <a name="remarks"></a>Комментарии  

 Этот обратный вызов дает возможность отладчику повторно создавать все ранее существовавшие пошаговые шаги.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
