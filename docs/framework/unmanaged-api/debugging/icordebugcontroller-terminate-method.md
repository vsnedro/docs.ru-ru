---
title: Метод ICorDebugController::Terminate
ms.date: 03/30/2017
api_name:
- ICorDebugController.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type:
- apiref
ms.openlocfilehash: 460aeeca9d62ce91a11a24d774c8e681ed4f00ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679810"
---
# <a name="icordebugcontrollerterminate-method"></a>Метод ICorDebugController::Terminate

Завершает процесс с указанным кодом выхода.  
  
> [!NOTE]
> Этот метод является оболочкой для функции Win32 `TerminateProcess` . Таким образом, `Terminate` использует код выхода точно так же, как функция Win32 `TerminateProcess` использует ее.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `exitCode`  
 окне Числовое значение, которое является кодом выхода. Допустимые числовые значения определяются в Винбасе. h.  
  
## <a name="remarks"></a>Комментарии  

 Если процесс останавливается при `Terminate` вызове, процесс должен быть продолжен с помощью метода [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) , чтобы отладчик получал подтверждение завершения, используя обратный вызов [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) или [ICorDebugManagedCallback:: ExitAppDomain](icordebugmanagedcallback-exitappdomain-method.md) .  
  
> [!NOTE]
> Этот метод не реализуется доменом приложения. Это значит, что он не реализован на <xref:System.AppDomain> уровне.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел
