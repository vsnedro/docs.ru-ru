---
title: 1023 - CompleteBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: fc5dac57-b3eb-4826-b505-c6d269e4774d
ms.openlocfilehash: cb99fd72165182788955021fbedd2aa657b3a098
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275327"
---
# <a name="1023---completebookmarkworkitem"></a>1023 - CompleteBookmarkWorkItem

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1023|  
|Keywords|WFRuntime|  
|Level|Подробный|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает на завершение BookmarkWorkItem.  
  
## <a name="message"></a>Сообщение  

 BookmarkWorkItem завершен для действия «%1», DisplayName «%2», InstanceId «%3». BookmarkName: %4, BookmarkScope: %5.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Действие|xs:string|Имя типа действия.|  
|DisplayName|xs:string|Отображаемое имя действия.|  
|InstanceId|xs:string|Идентификатор экземпляра действия.|  
|BookmarkName|xs:string|Имя закладки.|  
|BookmarkScope|xs:string|Область закладки.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
