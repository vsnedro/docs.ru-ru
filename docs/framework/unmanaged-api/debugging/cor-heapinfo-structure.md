---
description: 'Дополнительные сведения: структура COR_HEAPINFO'
title: Структура COR_HEAPINFO
ms.date: 03/30/2017
api_name:
- COR_HEAPINFO
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPINFO
helpviewer_keywords:
- COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type:
- apiref
ms.openlocfilehash: 0841739172b3eaf807813af28e0b20fbb54608b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712319"
---
# <a name="cor_heapinfo-structure"></a>Структура COR_HEAPINFO

Содержит общие сведения о куче для сборки мусора и указывает, является ли она перечислимой.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;
    DWORD pointerSize;
    DWORD numHeaps;  
    BOOL concurrent;
    CorDebugGCType gcType;
} COR_HEAPINFO;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`areGCStructuresValid`|`true` значение, если структуры сборки мусора являются допустимыми и можно перечислить в куче. в противном случае — `false` .|  
|`pointerSize`|Размер указателей в байтах в целевой архитектуре.|  
|`numHeaps`|Количество куч логической сборки мусора в процессе.|  
|`concurrent`|`TRUE` Если включена одновременная (фоновая) сборка мусора; в противном случае — `FALSE` .|  
|`gcType`|Член перечисления [CorDebugGCType](cordebuggctype-enumeration.md) , указывающий, работает ли сборщик мусора на рабочей станции или сервере.|  
  
## <a name="remarks"></a>Remarks  

 Экземпляр `COR_HEAPINFO` структуры возвращается путем вызова метода [метод ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) .  
  
 Перед перечислением объектов в куче сборки мусора необходимо всегда проверять `areGCStructuresValid` поле, чтобы убедиться в том, что куча находится в перечислимом состоянии. Дополнительные сведения см. в описании метода [метод ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
