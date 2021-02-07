---
description: 'Дополнительные сведения: 1027-Старттрансактионконтекстворкитем'
title: 1027 - StartTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
ms.openlocfilehash: e7f81a5998d948d3042b51dcdf20fbb1c88ad266
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755477"
---
# <a name="1027---starttransactioncontextworkitem"></a>1027 - StartTransactionContextWorkItem

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1027|  
|Keywords|WFRuntime|  
|Level|Подробный|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, что начинается выполнение TransactionContextWorkItem.  
  
## <a name="message"></a>Сообщение  

 Начато выполнение TransactionContextWorkItem для родительского действия «%1», DisplayName «%2», InstanceId «%3».  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Действие|xs:string|Имя типа действия.|  
|DisplayName|xs:string|Отображаемое имя действия.|  
|InstanceId|xs:string|Идентификатор экземпляра действия.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
