---
description: 'Дополнительные сведения: <dispatcherSynchronization>'
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 93664dec3648ed58df7e3e5c0760f1694c60ba7e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749610"
---
# \<dispatcherSynchronization>
  
Указывает поведение конечной точки, которое позволяет службе отправлять ответы в асинхронном режиме.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dispatcherSynchronization>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a>Тип  
  
`Type`  
  
## <a name="attributes-and-elements"></a>Элементы и атрибуты  
  
В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты

| Атрибут               | Описание       |
| ----------------------- | ----------------- |
| asynchronousSendEnabled | Логическое значение, указывающее, включено ли поведение, которое позволяет отправлять ответы в асинхронном режиме. |
| `maxPendingReceives`    | Целочисленное значение, которое указывает число возможных получений по одному каналу.<br /><br /> Это значение должно настраиваться только после правильной настройки поведения регулирования службы. |

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

| Элемент | Описание |  
| ------- | ----------- |  
| [\<behavior>](behavior-of-endpointbehaviors.md)|Задает поведение конечной точки. |

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
