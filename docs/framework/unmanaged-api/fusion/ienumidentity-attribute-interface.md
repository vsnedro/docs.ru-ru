---
description: Дополнительные сведения о IEnumIDENTITY_ATTRIBUTE интерфейсе
title: Интерфейс IEnumIDENTITY_ATTRIBUTE
ms.date: 03/30/2017
api_name:
- IEnumIDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords:
- IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type:
- apiref
ms.openlocfilehash: b621a722e35d5b31f487e8823b1627fdfe1e7888
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800153"
---
# <a name="ienumidentity_attribute-interface"></a>Интерфейс IEnumIDENTITY_ATTRIBUTE

Служит в качестве перечислителя для атрибутов объекта Code в текущей области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|Возвращает указатель интерфейса на новый объект `IEnumIDENTITY_ATTRIBUTE` , содержащий те же элементы, что и этот объект `IEnumIDENTITY_ATTRIBUTE` .|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|Записывает данные, содержащиеся в элементах этого объекта `IEnumIDENTITY_ATTRIBUTE` , в указанный буфер данных.|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|Возвращает указанное число атрибутов, начиная с текущей позиции.|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|Перемещает указатель инструкций в начало `IEnumIDENTITY_ATTRIBUTE` .|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|Перемещает указатель инструкции вперед на указанное число элементов, начиная с текущей позиции.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Изоляция. h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Fusion-интерфейсы](fusion-interfaces.md)
