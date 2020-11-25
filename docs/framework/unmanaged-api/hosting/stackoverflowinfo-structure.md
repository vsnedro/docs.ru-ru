---
title: Структура StackOverflowInfo
ms.date: 03/30/2017
api_name:
- StackOverflowInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowInfo
helpviewer_keywords:
- StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type:
- apiref
ms.openlocfilehash: a8a57cfcaf36949d4d10c6ec267a5f55a2aee5eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729932"
---
# <a name="stackoverflowinfo-structure"></a>Структура StackOverflowInfo

Хранит тип произошедшего переполнения и сведения об исключении, порождаемом из-за переполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`soType`|Значение перечисления [StackOverflowType](stackoverflowtype-enumeration.md) , указывающее тип переполнения.|  
|`pExceptionInfo`|Указатель на `EXCEPTION_POINTERS` объект Win32, который содержит запись исключения с независимым от компьютера описанием исключения и записью контекста с зависящим от компьютера описанием контекста процессора на момент возникновения исключения.|  
  
## <a name="remarks"></a>Комментарии  

 `StackOverflowInfo`Объект передается в метод [иактиононклревент:: oneven](iactiononclrevent-onevent-method.md) для `Event_StackOverflow` событий.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. idl  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структуры размещения](hosting-structures.md)
