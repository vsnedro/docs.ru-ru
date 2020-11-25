---
title: Интерфейс IReferenceAppId
ms.date: 03/30/2017
api_name:
- IReferenceAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceAppId
helpviewer_keywords:
- IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type:
- apiref
ms.openlocfilehash: 9aa7173d81d84d9080d90b0890769ffeaee6a738
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728619"
---
# <a name="ireferenceappid-interface"></a>Интерфейс IReferenceAppId

Представляет ссылку на уникальный идентификатор приложения в текущей области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Возвращает указатель на строковое представление идентификатора кода для приложения, на которое ссылается this `IReferenceAppId` .|  
|`IReferenceAppId::put_CodeBase`|Задает идентификатор кода для приложения, на которое ссылается this `IReferenceAppId` .|  
|`IReferenceAppId::EnumAppPath`|Возвращает указатель интерфейса на `IEnumReferenceIdentity` экземпляр `IReferenceIdentity` , содержащий экземпляры, представляющие члены этого объекта `IReferenceAppId` .|  
|`IReferenceAppId::get_SubscriptionId`|Возвращает указатель на строковое представление идентификатора маркера для подписки на этот объект `IReferenceAppId` .|  
|`IReferenceAppId::put_SubscriptionId`|Задает для идентификатора маркера подписки это `IReferenceAppId` значение в указанном строковом значении.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Изоляция. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Fusion-интерфейсы](fusion-interfaces.md)
- [Интерфейс IEnumReferenceIdentity](ienumreferenceidentity-interface.md)
- [Интерфейс IReferenceIdentity](ireferenceidentity-interface.md)
