---
title: Метод ICorDebugFunction2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type:
- apiref
ms.openlocfilehash: 55f219b5b834f365b87440e69bfa7d2c4e519235
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696100"
---
# <a name="icordebugfunction2setjmcstatus-method"></a>Метод ICorDebugFunction2::SetJMCStatus

Помечает функцию, представленную этим ICorDebugFunction2, для Только мой код пошагового выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `bIsJustMyCode`  
 окне Установите значение, чтобы `true` пометить функцию как пользовательский код; в противном случае задайте для значение `false` .  
  
## <a name="return-values"></a>Возвращаемые значения  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|Функция была успешно помечена.|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|Функция не может быть помечена как пользовательский код, так как ее отладка невозможна.|  
  
## <a name="remarks"></a>Комментарии  

 Только мой код пошаговое средство пропускает код, не являющийся пользовательским. Пользовательский код должен быть подмножеством отлаживаемого кода.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
