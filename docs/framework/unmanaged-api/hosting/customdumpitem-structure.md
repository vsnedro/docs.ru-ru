---
description: 'Дополнительные сведения о: структура Кустомдумпитем'
title: Структура CustomDumpItem
ms.date: 03/30/2017
api_name:
- CustomDumpItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CustomDumpItem
helpviewer_keywords:
- CustomDumpItem structure [.NET Framework hosting]
ms.assetid: fd9085ff-7beb-4c38-97f0-037cd8ba4f65
topic_type:
- apiref
ms.openlocfilehash: 9bd7b2bb59675bc01e24dc6e6d0ce524f3d35466
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716904"
---
# <a name="customdumpitem-structure"></a>Структура CustomDumpItem

Описывает элемент, добавляемый в пользовательский дамп в отчетах об ошибках.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`itemKind`|Значение [екустомдумпитемкинд](ecustomdumpitemkind-enumeration.md) , указывающее тип добавляемого элемента.|  
|`pReserved`|В настоящий момент не используется. Все элементы, добавляемые в объединение, не должны быть больше размера указателя. Если `struct` требуется, необходимо выделить его отдельно и указать на него.|  
  
## <a name="remarks"></a>Remarks  

 [Iclrerrorreportingmanagergetbucketparametersforcurrentexception:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) принимает параметр типа `CustomDumpItem` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. idl  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры размещения](hosting-structures.md)
