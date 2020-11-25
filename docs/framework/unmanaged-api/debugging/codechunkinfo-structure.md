---
title: Структура CodeChunkInfo
ms.date: 03/30/2017
api_name:
- CodeChunkInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CodeChunkInfo
helpviewer_keywords:
- CodeChunkInfo structure [.NET Framework debugging]
ms.assetid: 0f482454-8517-48de-ba7a-d7aedab13bb5
topic_type:
- apiref
ms.openlocfilehash: 11197246662a93f6a8b57c6e61e49505a9999d00
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727436"
---
# <a name="codechunkinfo-structure"></a>Структура CodeChunkInfo

Представляет одинарный блок кода в памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`startAddr`|`CORDB_ADDRESS`Значение, указывающее начальный адрес фрагмента.|  
|`length`|Размер блока в байтах.|  
  
## <a name="remarks"></a>Комментарии  

 Единственный фрагмент кода — это область машинного кода, которая является частью объекта кода, например функции.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод GetCodeChunks](icordebugcode2-getcodechunks-method.md)
- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
