---
description: 'Дополнительные сведения о: структура Стакковерфловинфо'
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
ms.openlocfilehash: cca65e4293c05b89ebefc3c6dd36a6b8898eb15f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679398"
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
  
## <a name="remarks"></a>Remarks  

 `StackOverflowInfo`Объект передается в метод [иактиононклревент:: oneven](iactiononclrevent-onevent-method.md) для `Event_StackOverflow` событий.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. idl  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры размещения](hosting-structures.md)
