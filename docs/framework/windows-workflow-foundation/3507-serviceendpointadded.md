---
description: 'Дополнительные сведения: 3507-Сервицеендпоинтаддед'
title: 3507 - ServiceEndpointAdded
ms.date: 03/30/2017
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
ms.openlocfilehash: 7de51cb8908d3bf4b450c545c1a4c0f2bdc6a453
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631480"
---
# <a name="3507---serviceendpointadded"></a>3507 - ServiceEndpointAdded

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|3507|  
|Keywords|WFServices|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Указывает, что конечная точка службы была добавлена.  
  
## <a name="message"></a>Сообщение  

 Конечная точка службы была добавлена для адреса «%1», привязки «%2» и контракта «%3».  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Адрес|xs:string|Адрес конечной точки.|  
|Привязка|xs:string|Привязка конечной точки.|  
|Контракт|xs:string|Контракт конечной точки.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
