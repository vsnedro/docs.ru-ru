---
description: 'Дополнительные сведения: 4205-Фаундпроцессинжеррор'
title: 4205 - FoundProcessingError
ms.date: 03/30/2017
ms.assetid: f2235a15-dd87-439e-8cb9-8b1b89a3dacf
ms.openlocfilehash: 847535af51cae8723f06d33b3b5c5c64cf3c5dd7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99676291"
---
# <a name="4205---foundprocessingerror"></a>4205 - FoundProcessingError

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|4205|  
|Keywords|WFInstanceStore|  
|Уровень|Ошибка|  
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
