---
title: Структура COR_DEBUG_IL_TO_NATIVE_MAP
ms.date: 03/30/2017
api_name:
- COR_DEBUG_IL_TO_NATIVE_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: 06f3b504-085f-4142-934a-25381fe23d4c
topic_type:
- apiref
ms.openlocfilehash: 61544d0dfe876f35fdfbe5afa945fad0620c0eb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726656"
---
# <a name="cor_debug_il_to_native_map-structure"></a>Структура COR_DEBUG_IL_TO_NATIVE_MAP

Содержит смещения, которые используются для сопоставления кода MSIL с машинным кодом.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`ilOffset`|Смещение кода MSIL.|  
|`nativeStartOffset`|Смещение начала машинного кода.|  
|`nativeEndOffset`|Смещение конца машинного кода.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf. idl, CorDebug. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод GetILToNativeMapping](../profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [Метод GetILToNativeMapping](icordebugcode-getiltonativemapping-method.md)
- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
