---
title: 4205 - FoundProcessingError
ms.date: 03/30/2017
ms.assetid: f2235a15-dd87-439e-8cb9-8b1b89a3dacf
ms.openlocfilehash: 2931d3723a04d7970197c9ebd79dc65ea43d67a7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251247"
---
# <a name="4205---foundprocessingerror"></a>4205 - FoundProcessingError

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|4205|  
|Keywords|WFInstanceStore|  
|Level|Ошибка|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает на сбой команды поставщика SQL.  
  
## <a name="message"></a>Сообщение  

 Не удалось выполнить команду: %1  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|ExceptionMessage|xs:string|Текст сообщения из исключения SQL.|  
|Исключение|xs:string|Сведения об исключении|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
