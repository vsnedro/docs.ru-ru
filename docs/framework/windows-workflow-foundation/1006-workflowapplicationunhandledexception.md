---
description: 'Дополнительные сведения: 1006-Воркфловаппликатионунхандледексцептион'
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: bfccd0d12c5dac4caad1e84e95f1cd096a551aa0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755594"
---
# <a name="1006---workflowapplicationunhandledexception"></a>1006 - WorkflowApplicationUnhandledException

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1006|  
|Keywords|WFRuntime|  
|Уровень|Ошибка|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, что приложение рабочего процесса обнаружило необработанное исключение.  
  
## <a name="message"></a>Сообщение  

 Элемент WorkflowInstance с идентификатором "%1" обнаружил необработанное исключение.  Исключение произошло из действия "%2", DisplayName: "%3".  Будет выполнено следующее действие: %4.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|Идентификатор экземпляра для рабочего процесса.|  
|Исключение|`xs:string`|Сведения об исключении|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
