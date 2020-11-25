---
title: Структура COR_ACTIVE_FUNCTION
ms.date: 03/30/2017
api_name:
- COR_ACTIVE_FUNCTION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ACTIVE_FUNCTION
helpviewer_keywords:
- COR_ACTIVE_FUNCTION structure [.NET Framework debugging]
ms.assetid: ed86185f-2152-459c-961f-10c06d62e83f
topic_type:
- apiref
ms.openlocfilehash: c50ba530d78296ebb956329b2f34b4f1e5cae94c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727423"
---
# <a name="cor_active_function-structure"></a>Структура COR_ACTIVE_FUNCTION

Содержит сведения о функциях, которые в данный момент активны в кадрах потока. Эта структура используется методом [ICorDebugThread2:: GetActiveFunctions](icordebugthread2-getactivefunctions-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`pAppDomain`|Указатель на владельца домена приложения для `ilOffset` поля.|  
|`pModule`|Указатель на владельца `ilOffset` поля.|  
|`pFunction`|Указатель на владельца функции `ilOffset` поля.|  
|`ilOffset`|Смещение кадра на языке MSIL.|  
|`flags`|Зарезервировано для будущего расширения.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
