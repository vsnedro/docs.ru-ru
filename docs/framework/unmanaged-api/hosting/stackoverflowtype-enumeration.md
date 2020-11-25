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
ms.openlocfilehash: bbdc68721378e6bbb09f5e4eade08e2e6e03b097
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729919"
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`SO_ClrEngine`|Переполнение стека было вызвано подсистемой выполнения.|  
|`SO_Managed`|Переполнение стека было вызвано управляемым кодом.|  
|`SO_Other`|Переполнение стека было вызвано неуправляемым кодом.|  
  
## <a name="remarks"></a>Комментарии  

 Эти сведения передаются на узел посредством вызова метода [иактиононклревент:: oneven](iactiononclrevent-onevent-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Размещение перечислений](hosting-enumerations.md)
