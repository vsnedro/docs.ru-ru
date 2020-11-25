---
title: Структура COR_DEBUG_STEP_RANGE
ms.date: 03/30/2017
api_name:
- COR_DEBUG_STEP_RANGE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_STEP_RANGE
helpviewer_keywords:
- COR_DEBUG_STEP_RANGE structure [.NET Framework debugging]
ms.assetid: 8809d00e-beaa-4dcf-b4e8-e89d0a5406b7
topic_type:
- apiref
ms.openlocfilehash: cd85ba2e6a907ff9546614e02b4da5f45e74b924
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726643"
---
# <a name="cor_debug_step_range-structure"></a>Структура COR_DEBUG_STEP_RANGE

Содержит сведения о смещении для диапазона кода.  
  
 Эта структура используется методом [ICorDebugStepper:: степранже](icordebugstepper-steprange-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`startOffset`|Смещение начала диапазона.|  
|`endOffset`|Смещение конца диапазона.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод StepRange](icordebugstepper-steprange-method.md)
- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
