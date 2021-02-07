---
description: 'Дополнительные сведения: 1103-Воркфловактивитисуспенд'
title: 1103 - WorkflowActivitySuspend
ms.date: 03/30/2017
ms.assetid: b64e15c2-cb2c-4314-9074-ce2c6717232e
ms.openlocfilehash: 2d46c31ee86dd39216294e6b7cd3785f2361f18b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667529"
---
# <a name="1103---workflowactivitysuspend"></a>1103 - WorkflowActivitySuspend

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1103|  
|Keywords|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, что действие рабочего процесса приостановлено.  
  
## <a name="message"></a>Сообщение  

 Элемент WorkflowInstance с идентификатором «%1», действие E2E  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|xs:string|Идентификатор экземпляра рабочего процесса.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
