---
title: Метод ICorDebug::SetManagedHandler
ms.date: 03/30/2017
api_name:
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
ms.openlocfilehash: 97a4a464d3dfb7b333f44ac4206bd880fd171e16
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723419"
---
# <a name="icordebugsetmanagedhandler-method"></a>Метод ICorDebug::SetManagedHandler

Указывает объект обработчика событий для управляемых событий.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pCallback`  
 окне Указатель на объект [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) , который является объектом обработчика событий.  
  
## <a name="remarks"></a>Комментарии  

 `SetManagedHandler` должен вызываться во время создания.  
  
 Если `ICorDebugManagedCallback` реализация не содержит достаточных интерфейсов для работы с событиями отладки для отлаживаемого приложения, `SetManagedHandler` возвращает значение HRESULT E_NOINTERFACE.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebug](icordebug-interface.md)
