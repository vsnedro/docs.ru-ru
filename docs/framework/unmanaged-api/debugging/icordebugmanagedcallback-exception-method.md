---
title: Метод ICorDebugManagedCallback::Exception
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Exception
helpviewer_keywords:
- Exception method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::Exception method [.NET Framework debugging]
ms.assetid: ab18a509-dff3-4930-b585-bd15e0414176
topic_type:
- apiref
ms.openlocfilehash: 05fed13a556cbcc3b8362e41d73c2b659b1e5eeb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731791"
---
# <a name="icordebugmanagedcallbackexception-method"></a>Метод ICorDebugManagedCallback::Exception

Уведомляет отладчик о появлении исключения из управляемого кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pAppDomain`  
 окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, в котором было создано исключение.  
  
 `pThread`  
 окне Указатель на объект ICorDebugThread, представляющий поток, в котором было создано исключение.  
  
 `unhandled`  
 окне Если это значение равно `false` , исключение еще не было обработано приложением; в противном случае исключение не обрабатывается, и процесс завершится.  
  
## <a name="remarks"></a>Комментарии  

 Конкретное исключение можно получить из объекта потока.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
