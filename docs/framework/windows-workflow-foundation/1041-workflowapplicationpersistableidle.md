---
description: 'Дополнительные сведения: 1041-Воркфловаппликатионперсистаблеидле'
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: eb004077a36ed3e78229df92a73972ed5feda665
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667763"
---
# <a name="1041---workflowapplicationpersistableidle"></a>1041 - WorkflowApplicationPersistableIdle

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1041|  
|Keywords|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, что приложение рабочего процесса бездействует и является сохраняемым. Приложение рабочего процесса будет бездействующим или сохраняемым.  
  
## <a name="message"></a>Сообщение  

 Идентификатор WorkflowApplication: "%1" находится в состоянии бездействия и является сохраняемым.  Будет выполнено следующее действие: %2.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|WorkflowApplicationId|xs:string|Идентификатор приложения рабочего процесса|  
|ActionTaken|xs:string|Действие, которое будет выполняться в приложении рабочего процесса.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
