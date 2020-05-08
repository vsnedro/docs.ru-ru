---
title: Метод ICorDebugController::EnumerateThreads
ms.date: 03/30/2017
api_name:
- ICorDebugController.EnumerateThreads
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type:
- apiref
ms.openlocfilehash: 4d69f13d4716b43c815148ff0fe4aa087b57c6e5
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892758"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a>Метод ICorDebugController::EnumerateThreads
Возвращает перечислитель для активных управляемых потоков в процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppThreads`  
 заполняет Указатель на адрес объекта "Икордебугсреаденум", который представляет перечислитель для всех управляемых потоков, активных в процессе.  
  
## <a name="remarks"></a>Remarks  
 Поток считается активным после отправки обратного вызова [ICorDebugManagedCallback:: CreateThread](icordebugmanagedcallback-createthread-method.md) и перед отправкой обратного вызова [ICorDebugManagedCallback:: ExitThread](icordebugmanagedcallback-exitthread-method.md) . Управляемый поток может не обязательно содержать управляемые фреймы в своем стеке. Потоки можно перечислить даже перед обратным вызовом [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) . Перечисление естественным образом будет пустым.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел
