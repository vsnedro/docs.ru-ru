---
title: Интерфейс IReferenceIdentity
ms.date: 03/30/2017
api_name:
- IReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceIdentity
helpviewer_keywords:
- IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type:
- apiref
ms.openlocfilehash: 867c09caa3bd3aed50de21c2ef91a02782830be2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704556"
---
# <a name="ireferenceidentity-interface"></a>Интерфейс IReferenceIdentity

Представляет ссылку на уникальную сигнатуру объекта кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|Возвращает указатель интерфейса на новый `IReferenceIdentity` экземпляр, идентичный этому `IReferenceIdentity` , за исключением изменения указанного атрибута.|  
|`IReferenceIdentity::EnumAttributes`|Возвращает указатель интерфейса на `IEnumIDENTITY_ATTRIBUTE` экземпляр, содержащий атрибуты, связанные с этим `IReferenceIdentity` .|  
|`IReferenceIdentity::GetAttribute`|Возвращает значение атрибута в указанном пространстве имен с указанным именем.|  
|`IReferenceIdentity::SetAttribute`|Задает для атрибута, имеющего указанное пространство имен и указанное имя, указанное значение.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Изоляция. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Fusion-интерфейсы](fusion-interfaces.md)
- [Интерфейс IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md)
