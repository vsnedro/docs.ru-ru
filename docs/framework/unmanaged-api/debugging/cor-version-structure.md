---
description: 'Дополнительные сведения: структура COR_VERSION'
title: Структура COR_VERSION
ms.date: 03/30/2017
api_name:
- COR_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_VERSION
helpviewer_keywords:
- COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type:
- apiref
ms.openlocfilehash: abdbe2a62d89db9dd673a429d81209fc42c34b73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801778"
---
# <a name="cor_version-structure"></a>Структура COR_VERSION

Содержит стандартный номер версии среды CLR, состоящий из четырех частей.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`dwMajor`|Основной номер версии.|  
|`dwMinor`|Дополнительный номер версии.|  
|`dwBuild`|Номер построения.|  
|`dwSubBuild`|Номер подсборки.|  
  
## <a name="remarks"></a>Remarks  

 Если номер версии — 1.0.3705.288, то 1 — основной номер версии, 0 — дополнительный номер версии, 3705 — номер сборки, а 288 — номер подсборки.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
