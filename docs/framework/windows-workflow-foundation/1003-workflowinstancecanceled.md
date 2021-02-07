---
description: 'Дополнительные сведения: 1003-Воркфловинстанцеканцелед'
title: 1003 - WorkflowInstanceCanceled
ms.date: 03/30/2017
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
ms.openlocfilehash: ef7b7c6849e96866204fe53deadce8302d18e0d8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703371"
---
# <a name="1003---workflowinstancecanceled"></a>1003 - WorkflowInstanceCanceled

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1003|  
|Keywords|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, что экземпляр рабочего процесса завершено в состоянии Canceled.  
  
## <a name="message"></a>Сообщение  

 Элемент WorkflowInstance с идентификатором «%1» завершил работу в состоянии Canceled.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|Идентификатор экземпляра для рабочего процесса.|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
