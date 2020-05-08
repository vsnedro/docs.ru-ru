---
title: Метод ICorDebugEval2::RudeAbort
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.RudeAbort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::RudeAbort
helpviewer_keywords:
- ICorDebugEval2::RudeAbort method [.NET Framework debugging]
- RudeAbort method, ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: 02468edf-d32b-4cb3-aaa8-3dd2abfc8b25
topic_type:
- apiref
ms.openlocfilehash: e901c65824ee8d6949c79c7778944148c0d9eb28
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976061"
---
# <a name="icordebugeval2rudeabort-method"></a>Метод ICorDebugEval2::RudeAbort
Прерывает вычисление, `ICorDebugEval2` выполняемое в данный момент.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a>Remarks  
 `RudeAbort`не освобождает никакие блокировки, которые содержит средство оценки, поэтому сеанс отладки остается в ненадежном состоянии. Вызывайте этот метод с особой осторожностью.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
