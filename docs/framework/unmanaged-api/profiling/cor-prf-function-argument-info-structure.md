---
title: Структура COR_PRF_FUNCTION_ARGUMENT_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type:
- apiref
ms.openlocfilehash: 5feda2ce6dc97576d0b1d4f16ca2b9dd5f3fb05e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718567"
---
# <a name="cor_prf_function_argument_info-structure"></a>Структура COR_PRF_FUNCTION_ARGUMENT_INFO

Представляет аргументы функции слева направо.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`numRanges`|Число блоков аргументов. То есть это значение равно количеству структур [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) в `ranges` массиве.|  
|`totalArgumentSize`|Общий размер всех аргументов. Иными словами, это значение является суммой длин аргументов.|  
|`ranges`|Массив `COR_PRF_FUNCTION_ARGUMENT_RANGE` структур, каждый из которых представляет один блок аргументов функции.|  
  
## <a name="remarks"></a>Комментарии  

 У функции может быть несколько аргументов. Эти аргументы могут не храниться непрерывно в памяти. У вас может быть блок из трех аргументов в одном месте, блок из двух аргументов в другом месте и последний блок одного аргумента в другом месте. Все эти аргументы используются для одной и той же функции. они просто хранятся в разных местах.  
  
 `COR_PRF_FUNCTION_ARGUMENT_INFO`Структура представляет все аргументы одной функции. Он использует массив для ссылки на все блоки аргументов функции. Таким образом, для одной функции имеется одна `COR_PRF_FUNCTION_ARGUMENT_INFO` структура, которая ссылается на несколько `COR_PRF_FUNCTION_ARGUMENT_RANGE` структур, каждая из которых указывает на один или несколько аргументов функции.  
  
 Аргументы, хранимые в регистрах, загружаются в память для построения структур.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структуры профилирования](profiling-structures.md)
