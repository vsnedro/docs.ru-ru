---
title: MALLOC_TYPE - перечисление
ms.date: 03/30/2017
api_name:
- MALLOC_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MALLOC_TYPE
helpviewer_keywords:
- MALLOC_TYPE Enumeration
ms.assetid: c02476f9-23a2-4af7-9282-aa9c42c7429b
topic_type:
- apiref
ms.openlocfilehash: fe58a519d0feac0da49e7778247da1ef538f8b83
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730036"
---
# <a name="malloc_type-enumeration"></a>MALLOC_TYPE - перечисление

Содержит значения, указывающие характеристики выделяемой памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|Выделенная память может содержать исполняемый файл.|  
|`MALLOC_THREADSAFE`|Выделенная память является потокобезопасной. То есть доступ к памяти может осуществляться несколькими потоками без синхронизации.<br /><br /> Если этот флаг не установлен, вызовы для объекта должны быть сериализованы.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Размещение перечислений](hosting-enumerations.md)
