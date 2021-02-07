---
description: 'Дополнительные сведения о: <httpDigest> element'
title: Элемент <httpDigest>
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 2b11edcaab88ff3a2b437b1e886997e08b8c9fee
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749666"
---
# <a name="httpdigest-element"></a>Элемент \<httpDigest>

Задает учетные данные, используемые для дайджест-проверки подлинности клиента при подключении к службе.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpDigest>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<httpDigest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`impersonationLevel`|Задает параметры олицетворения, сообщаемые клиентом серверу. Режим олицетворения, выбираемый клиентом, не задается принудительно для сервера. Допустимые значения.<br /><br /> -Identification: сервер может получить удостоверение и привилегии клиента, но не может олицетворять клиента.<br />— Олицетворение. сервер может олицетворять контекст безопасности клиента в локальной системе.<br />-Делегирование. сервер может олицетворять контекст безопасности клиента в удаленных системах.<br />— Анонимно: сервер не может олицетворять или опознать клиента.<br />-None: уровень олицетворения не назначен.<br /><br /> Значение по умолчанию - Identification. Это атрибут типа <xref:System.Security.Principal.TokenImpersonationLevel>.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 None  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.|  
  
## <a name="remarks"></a>Remarks  

 Хэш-кода — это хэш, определяемый с помощью алгоритма и набора входных данных. Структура проверки подлинности и проверяемый объект согласуют алгоритм и обмениваются данными, используемыми в качестве входных. Клиент может вычислить хэш и отправить его службе. Служба также вычисляет хэш и сравнивает значения. Совпадение значений подтверждает подлинность клиента.  
  
 Эта функция должна быть включена с помощью Active Directory в Windows и службах IIS. Дополнительные сведения см. [в статье дайджест-проверка подлинности в IIS 6,0](/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [Поведение безопасности](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Обеспечение безопасности клиентов](../../../wcf/securing-clients.md)
- [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md)
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
