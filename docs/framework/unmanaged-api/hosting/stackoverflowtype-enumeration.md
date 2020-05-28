---
title: Перечисление StackOverflowType
ms.date: 03/30/2017
api_name:
- StackOverflowType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowType
helpviewer_keywords:
- StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type:
- apiref
ms.openlocfilehash: f399d33dbe05cb5768aa45533ef30d28409e18e2
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006484"
---
# <a name="stackoverflowtype-enumeration"></a>Перечисление StackOverflowType
Содержит значения, указывающие основную причину события переполнения стека.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`SO_ClrEngine`|Переполнение стека было вызвано подсистемой выполнения.|  
|`SO_Managed`|Переполнение стека было вызвано управляемым кодом.|  
|`SO_Other`|Переполнение стека было вызвано неуправляемым кодом.|  
  
## <a name="remarks"></a>Примечания  
 Эти сведения передаются на узел посредством вызова метода [иактиононклревент:: oneven](iactiononclrevent-onevent-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Размещение перечислений](hosting-enumerations.md)
