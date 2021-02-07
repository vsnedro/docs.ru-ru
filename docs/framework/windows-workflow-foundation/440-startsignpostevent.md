---
description: 'Дополнительные сведения: 440-StartSignpostEvent1'
title: 440 - StartSignpostEvent1
ms.date: 03/30/2017
ms.assetid: 27b551b5-ae76-49f8-bab8-6300009eb4c1
ms.openlocfilehash: 462ad54c9dd8230632d76d88f2b779eaea3b43ee
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720375"
---
# <a name="440---startsignpostevent1"></a>440 - StartSignpostEvent1

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|440|  
|Keywords|Устранение неполадок|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 В трассировке действий указывает на то, что сообщение начало пересекать границу действия при отправке или приеме.  
  
## <a name="message"></a>Сообщение  

 Граница действия.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|ExtendedData|`xs:string`|Имя действия.|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
