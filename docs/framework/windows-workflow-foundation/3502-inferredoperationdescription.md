---
description: 'Дополнительные сведения: 3502-Инферредоператиондескриптион'
title: 3502 - InferredOperationDescription
ms.date: 03/30/2017
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
ms.openlocfilehash: 5068a3553484b38242951ef985886190f8027035
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631493"
---
# <a name="3502---inferredoperationdescription"></a>3502 - InferredOperationDescription

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|3502|  
|Keywords|WFServices|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Указывает, что описание операции OperationDescription выведено из WorkflowService.  
  
## <a name="message"></a>Сообщение  

 Описание OperationDescription с параметром Name=«%1» в контракте «%2» было выведено из WorkflowService. IsOneWay=%3.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|OperationName|xs:string|Имя операции.|  
|ContractName|xs:string|Имя контракта.|  
|IsOneWay|xs:string|Логическое значение True или False, указывающее, является ли контракт односторонним.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
