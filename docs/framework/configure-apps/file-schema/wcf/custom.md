---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 598b341e8b09acd11ba215e6add3adf9e44b2b81
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400467"
---
# \<custom>
Задает параметры службы пользовательского распознавателя одноранговых узлов.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<resolver>**](resolver.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<custom>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|`address`|URI, указывающий адрес конечной точки однорангового узла, на котором размещается пользовательская служба распознавателя одноранговых узлов.|  
|`resolverType`|Строка, задающая тип пользовательской службы распознавателя одноранговых узлов.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<identity>](identity.md)|Задает идентификатор пользовательских распознавателей одноранговых узлов, настроенных для данного элемента. Это элемент типа <xref:System.ServiceModel.Configuration.IdentityElement>.|  
|[\<headers>](headers-element.md)|Коллекция заголовков адреса, используемых для сообщений SOAP, обрабатываемых пользовательским распознавателем одноранговых узлов.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<resolver>](resolver.md)|Распознаватель одноранговых узлов, используемый для разрешения идентификатора сетки с IP-адресами в набор адресов одноранговых узлов, представляющих несколько узлов, входящих в сетку.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент определяет основные параметры пользовательской службы распознавателя одноранговых узлов, включая адрес конечной точки однорангового узла, на котором размещена служба, и любые специальные параметры привязки. Дополнительные сведения о создании пользовательского сопоставителя см. в разделе [Добавление пользовательского сопоставителя в приложение PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [Одноранговые распознаватели](../../../wcf/feature-details/peer-resolvers.md)
- [Добавление в приложение PeerChannel пользовательского распознавателя](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))
