---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: dbf0ba565d4e3e2d65b4a81eb5d345fa90fb43c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181431"
---
# \<persistenceProvider>

Задает тип используемой реализации поставщика сохраняемости, а также время ожидания операций сохраняемости.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistenceProvider>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|persistenceOperationTimeout|Значение <xref:System.TimeSpan>, которое задает время ожидания, используемое для операций сохраняемости. Значение по умолчанию — "00:00:30".|  
|тип|Строка, указывающая тип используемой фабрики поставщика сохраняемости.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Указывает элемент поведения.|  
  
## <a name="remarks"></a>Remarks  

 Этот элемент задает поставщика сохраняемости, используемого для сериализации состояния службы WCF. Он должен использоваться вместе с атрибутом `wsHttpContextBinding`, который передает сведения о состоянии в HTTP-заголовки.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
