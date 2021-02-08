---
description: 'Дополнительные сведения: 4210-Склексцептионкаугхт'
title: 4210 - SqlExceptionCaught
ms.date: 03/30/2017
ms.assetid: f0ce8af3-eb4c-48c8-b3d9-dd2f94b5574b
ms.openlocfilehash: 58846d02b6d1e388e3aef2bff76f51cba4990f2f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99777883"
---
# <a name="4210---sqlexceptioncaught"></a>4210 - SqlExceptionCaught

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|4210|  
|Keywords|WFInstanceStore|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, что было перехвачено исключение SQL.  
  
## <a name="message"></a>Сообщение  

 Обнаружено исключение SQL с номером %1, сообщение %2.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Номер ошибки|xs:string|Номер ошибки SQL.|  
|ExceptionMessage|xs:string|Текст сообщения из исключения SQL.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
