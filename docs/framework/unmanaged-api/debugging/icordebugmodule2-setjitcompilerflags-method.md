---
description: 'Дополнительные сведения о методе: ICorDebugModule2:: SetJITCompilerFlags'
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
ms.openlocfilehash: 72139c2fefc0eab7e76e38d07558e4386b47bc34
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801076"
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
  
## <a name="remarks"></a>Remarks  

 Если `dwFlags` значение недопустимо, `SetJITCompilerFlags` метод завершится ошибкой.  
  
 `SetJITCompilerFlags`Метод может быть вызван только в обратном вызове [ICorDebugManagedCallback:: LoadModule](icordebugmanagedcallback-loadmodule-method.md) для этого модуля. Попытки вызвать его после `ICorDebugManagedCallback::LoadModule` доставки обратного вызова завершатся ошибкой.  
  
 "Изменить и продолжить" не поддерживается на платформах 64-разрядных или Win9x. Поэтому при вызове `SetJITCompilerFlags` метода для любой из этих двух платформ с флагом CORDEBUG_JIT_ENABLE_ENC, установленным в `dwFlags` , `SetJITCompilerFlags` метод и все методы, относящиеся к Edit и Continue, такие как [ICorDebugModule2:: ApplyChanges](icordebugmodule2-applychanges-method.md), завершатся ошибкой.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
