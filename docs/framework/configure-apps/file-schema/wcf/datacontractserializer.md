---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 0e4cbc50c25d4fa1f67f283f2b52d4b174428cd3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153928"
---
# <a name="datacontractserializer"></a>dataContractSerializer

Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Элемент|Описание|  
|-------------|-----------------|  
|ignoreExtensionDataObject|Логическое значение, указывающее, должны ли пропускаться данные, предоставляемые конечной точкой, при их сериализации или десериализации.|  
|maxItemsInObjectGraph|Целое число, указывающее максимальное количество элементов для сериализации или десериализации.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Задает поведение конечной точки.|  
  
## <a name="remarks"></a>Remarks  

 Дополнительные сведения об известных типах см. в документации по <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
> [!CAUTION]
> Элемент поведения `<dataContractSerializer>` (если он присутствует) должен всегда находиться в файле конфигурации перед элементом поведения `<enableWebScript>`. В противном случае результирующее поведение является неопределенным.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [Известные типы контрактов данных](../../../wcf/feature-details/data-contract-known-types.md)
- [Передача данных и сериализация](../../../wcf/feature-details/data-transfer-and-serialization.md)
