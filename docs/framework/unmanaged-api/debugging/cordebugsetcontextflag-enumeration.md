---
description: Дополнительные сведения о перечислении Кордебугсетконтекстфлаг
title: Перечисление CorDebugSetContextFlag
ms.date: 03/30/2017
api_name:
- CorDebugSetContextFlag
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugSetContextFlag
helpviewer_keywords:
- CorDebugSetContextFlag enumeration [.NET Framework debugging]
ms.assetid: b30280bb-fe75-44ed-8589-bcff081fae44
topic_type:
- apiref
ms.openlocfilehash: 625f24e516ff462cf3d0e628dfff6c08793807ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801557"
---
# <a name="cordebugsetcontextflag-enumeration"></a>Перечисление CorDebugSetContextFlag

Указывает происхождение контекста: взят из активного (или листового) кадра в стеке или был вычислен в результате освобождения другого кадра.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|SET_CONTEXT_FLAG_ACTIVE_FRAME|Контекст является активным контекстом потока.|  
|SET_CONTEXT_FLAG_UNWIND_FRAME|Контекст был вычислен путем очистки от другого кадра.|  
  
## <a name="remarks"></a>Remarks  

 `CorDebugSetContextFlag` предоставляет значения, используемые методом [икордебугстакквалк:: SetContext](icordebugstackwalk-setcontext-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](debugging-enumerations.md)
- [Отладка](index.md)
