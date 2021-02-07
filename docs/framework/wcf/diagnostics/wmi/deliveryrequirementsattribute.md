---
description: 'Дополнительные сведения о: атрибут DeliveryRequirementsAttribute'
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: ee27ada1c1fb447de3d7a108a4a285ca106e4e8e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757505"
---
# <a name="deliveryrequirementsattribute"></a>DeliveryRequirementsAttribute

DeliveryRequirementsAttribute  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс DeliveryRequirementsAttribute не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс DeliveryRequirementsAttribute имеет следующие свойства.  
  
### <a name="queueddeliveryrequirements"></a>QueuedDeliveryRequirements  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Указывает, поддерживает ли привязка для службы контракты.  
  
### <a name="requireordereddelivery"></a>RequireOrderedDelivery  

 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, поддерживает ли привязка упорядоченные сообщения.  
  
### <a name="targetcontract"></a>TargetContract  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Контракт, к которому оно применимо.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
