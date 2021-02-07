---
description: 'Дополнительные сведения о методе: ICorDebugEval2:: RudeAbort'
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
ms.openlocfilehash: 2835fd635da007b5ee3f0e642b77f3954945f168
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693516"
---
# <a name="icordebugeval2rudeabort-method"></a>Метод ICorDebugEval2::RudeAbort

Прерывает вычисление, выполняемое `ICorDebugEval2` в данный момент.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a>Remarks  

 `RudeAbort` не освобождает никакие блокировки, которые содержит средство оценки, поэтому сеанс отладки остается в ненадежном состоянии. Вызывайте этот метод с особой осторожностью.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
