---
description: 'Дополнительные сведения: 1131-Инвокемесодусеасинкпаттерн'
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 59d8e5e1fe7c5b038df6fce3211fd01977abc4f9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667321"
---
# <a name="1131---invokemethoduseasyncpattern"></a>1131 - InvokeMethodUseAsyncPattern

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1131|  
|Keywords|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 На шаге CacheMetadata действие InvokeMethod указывает на использование асинхронного шаблона при вызове метода.  
  
## <a name="message"></a>Сообщение  

 Метод InvokeMethod «%1»: в методе используется асинхронная модель «%2» и «%3».  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|xs:string|Отображаемое имя действия InvokeMethod.|  
|BeginMethod|xs:string|Имя метода Begin.|  
|EndMethod|xs:string|Имя метода End.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
