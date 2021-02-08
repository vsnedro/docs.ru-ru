---
description: 'Дополнительные сведения: <servicePrincipalName>'
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: 494368f1f47f10aac8009e47a9219966c87e5eda
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786698"
---
# \<servicePrincipalName>

Указывает идентификацию службы по имени субъекта-службы (SPN).  
  
Дополнительные сведения о настройке имени субъекта-службы см. в статье [удостоверение службы и проверка подлинности](../../../wcf/feature-details/service-identity-and-authentication.md).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePrincipalName>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|value|Имя, по которому клиент однозначно определяет экземпляр службы. Если на компьютерах в лесу установлено несколько экземпляров службы, то каждый экземпляр должен иметь свое имя участника-службы. Каждый экземпляр службы может иметь несколько имен участников-служб при наличии нескольких имен, которые могут использоваться клиентами для проверки подлинности.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<identity>](identity.md)|Задает удостоверение службы, подлинность которой должна быть проверена клиентом.|  
  
## <a name="remarks"></a>Remarks  

 Клиент Secure Windows Communication Foundation (WCF), который подключается к конечной точке с этим удостоверением, использует имя субъекта-службы при выполнении проверки подлинности SSPI с конечной точкой.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [Идентификация и проверка подлинности службы](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
