---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 716d960e2d5f896976c22a60d419d9b165b36178
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202465"
---
# \<webHttp>

Данный элемент задает <xref:System.ServiceModel.Description.WebHttpBehavior> на конечной точке в конфигурации. Такое поведение при использовании в сочетании со [\<webHttpBinding>](webhttpbinding.md) стандартной привязкой позволяет использовать модель веб-программирования для службы Windows Communication Foundation (WCF).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttp>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|automaticFormatSelectionEnabled|Если это свойство имеет значение `true`, то инфраструктура WCF определяет лучший формат для использования. Автоматический выбор формата отключен по умолчанию в целях обратной совместимости. Автоматический выбор формата можно включить программно или через конфигурацию.|  
|defaultBodyStyle|Задает стиль по умолчанию для текста возвращаемых сообщений. Дополнительные сведения см. в разделе <xref:System.ServiceModel.Web.WebMessageBodyStyle> и [веб-форматирование WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).|  
|defaultOutgoingResponseFormat|Определяет формат ответа по умолчанию для исходящих сообщений. Дополнительные сведения см. в разделе [веб-форматирование WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).|  
|faultExceptionEnabled|Возвращает или задает флаг, указывающий, будет ли создаваться исключение FaultException при возникновении внутренней ошибки сервера (код состояния HTTP: 500).|  
|helpEnabled|Возвращает или задает значение, определяющее, будет ли включена страница справки.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Задает набор поведений конечной точки.|  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [Интеграция с AJAX и поддержка JSON](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttpBinding>](webhttpbinding.md)
