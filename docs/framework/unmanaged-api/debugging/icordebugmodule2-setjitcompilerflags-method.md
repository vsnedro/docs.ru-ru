---
title: Метод ICorDebugModule2::SetJITCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type:
- apiref
ms.openlocfilehash: 11ff430c426c93f1c2a5c0582495e089a33995fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709808"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a>Метод ICorDebugModule2::SetJITCompilerFlags

Задает флаги, управляющие JIT-компиляцией этого ICorDebugModule2.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwFlags`  
 окне Побитовое сочетание значений перечисления [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) .  
  
## <a name="remarks"></a>Комментарии  

 Если `dwFlags` значение недопустимо, `SetJITCompilerFlags` метод завершится ошибкой.  
  
 `SetJITCompilerFlags`Метод может быть вызван только в обратном вызове [ICorDebugManagedCallback:: LoadModule](icordebugmanagedcallback-loadmodule-method.md) для этого модуля. Попытки вызвать его после `ICorDebugManagedCallback::LoadModule` доставки обратного вызова завершатся ошибкой.  
  
 "Изменить и продолжить" не поддерживается на платформах 64-разрядных или Win9x. Поэтому при вызове `SetJITCompilerFlags` метода для любой из этих двух платформ с флагом CORDEBUG_JIT_ENABLE_ENC, установленным в `dwFlags` , `SetJITCompilerFlags` метод и все методы, относящиеся к Edit и Continue, такие как [ICorDebugModule2:: ApplyChanges](icordebugmodule2-applychanges-method.md), завершатся ошибкой.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
