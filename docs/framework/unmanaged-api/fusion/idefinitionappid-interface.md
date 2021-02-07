---
description: 'Дополнительные сведения о: интерфейс IDefinitionAppId'
title: Интерфейс IDefinitionAppId
ms.date: 03/30/2017
api_name:
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
ms.openlocfilehash: 3c68044e7e747521e190fad404e89d6d0a994611
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760671"
---
# <a name="idefinitionappid-interface"></a>Интерфейс IDefinitionAppId

Представляет уникальный идентификатор для кода, определяющего приложение в текущей области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|Возвращает отформатированную строку, которая представляет код в этом `IDefinitionAppId` объекте.|  
|`IDefinitionAppId::put_Codebase`|Задает код этого `IDefinitionAppId` объекта в указанном форматированном строковом значении.|  
|`IDefinitionAppId::EnumAppPath`|Возвращает указатель интерфейса на объект [иенумдефинитионидентити](ienumdefinitionidentity-interface.md) , содержащий сборки в текущем пути приложения.|  
|`IDefinitionAppId::SetAppPath`|Задает путь приложения для сборки в текущей области к значению, на которое ссылается указанный объект [идефинитионидентити](idefinitionidentity-interface.md) .|  
|`IDefinitionAppId::get_SubscriptionId`|Возвращает указатель на строковое представление идентификатора маркера для подписки на этот `IDefinitionAppId` объект.|  
|`IDefinitionAppId::put_SubscriptionId`|Устанавливает идентификатор маркера для подписки на этот `IDefinitionAppId` объект в указанном строковом значении.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Изоляция. h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Fusion-интерфейсы](fusion-interfaces.md)
