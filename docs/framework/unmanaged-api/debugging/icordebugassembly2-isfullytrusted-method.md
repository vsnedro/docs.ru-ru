---
title: Метод ICorDebugAssembly2::IsFullyTrusted
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2.IsFullyTrusted
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type:
- apiref
ms.openlocfilehash: 8a2a6be0db76f5ee2c7fa67c2038e0a5c845bd0f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719714"
---
# <a name="icordebugassembly2isfullytrusted-method"></a>Метод ICorDebugAssembly2::IsFullyTrusted

Возвращает значение, указывающее, предоставлено ли сборке полное доверие системой безопасности среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pbFullyTrusted`  
 [out] `true` значение, если сборке было предоставлено полное доверие системой безопасности среды выполнения; в противном случае — `false` .  
  
## <a name="remarks"></a>Комментарии  

 Этот метод возвращает значение HRESULT CORDBG_E_NOTREADY, если политика безопасности для сборки еще не разрешена, то есть если код в сборке еще не выполнялся.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
