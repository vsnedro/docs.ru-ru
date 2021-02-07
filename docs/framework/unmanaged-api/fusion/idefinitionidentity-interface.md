---
description: 'Дополнительные сведения о: интерфейс Идефинитионидентити'
title: Интерфейс IDefinitionIdentity
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
ms.openlocfilehash: 3471879cc822b655b786dd9d8234950cb4b99c1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760658"
---
# <a name="idefinitionidentity-interface"></a>Интерфейс IDefinitionIdentity

Представляет уникальную сигнатуру кода, определяющего приложение в текущей области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|Получает указатель интерфейса на новый `IDefinitionIdentity` объект, идентичный этому объекту `IDefinitionIdentity` , за исключением изменений указанного атрибута.|  
|`IDefinitionIdentity::EnumAttributes`|Возвращает указатель интерфейса на объект [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) , содержащий атрибуты, связанные с этим объектом `IDefinitionIdentity` .|  
|`IDefinitionIdentity::GetAttribute`|Возвращает значение атрибута с указанным именем в указанном пространстве имен.|  
|`IDefinitionIdentity::SetAttribute`|Задает для атрибута с указанным именем в указанном пространстве имен указанное значение.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Изоляция. h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Fusion-интерфейсы](fusion-interfaces.md)
