---
description: 'Дополнительные сведения: 1001-Воркфловаппликатионкомплетед'
title: 1001 - WorkflowApplicationCompleted
ms.date: 03/30/2017
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
ms.openlocfilehash: d32028bbe582f4a1e31796ed1f75e41c651e6c59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755646"
---
# <a name="1001---workflowapplicationcompleted"></a>1001 - WorkflowApplicationCompleted

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1001|  
|Keywords|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, что приложение рабочего процесса завершено в состоянии Closed.  
  
## <a name="message"></a>Сообщение  

 Элемент WorkflowInstance с идентификатором «%1» завершил работу в состоянии Closed.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|Идентификатор экземпляра для рабочего процесса.|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
