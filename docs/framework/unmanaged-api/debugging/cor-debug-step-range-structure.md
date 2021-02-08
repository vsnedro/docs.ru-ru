---
description: 'Дополнительные сведения: структура COR_DEBUG_STEP_RANGE'
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
ms.openlocfilehash: 40462be4b165351b3265fa0833d19f18e0fa3a37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801843"
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
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StepRange](icordebugstepper-steprange-method.md)
- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
