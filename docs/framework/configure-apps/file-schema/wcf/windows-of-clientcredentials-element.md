---
title: <windows> элемента <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: 115e1822659c04ee37a7364f7b25616b52dc5efe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177830"
---
# <a name="windows-of-clientcredentials-element"></a>\<windows> элемента \<clientCredentials>

Определяет параметры учетных данных Windows, которые используются для представления клиента.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windows>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|Задает параметры олицетворения, сообщаемые клиентом серверу. Режим олицетворения, выбираемый клиентом, не задается принудительно для сервера. Допустимые значения.<br /><br /> -Identification: сервер может получить удостоверение и привилегии клиента, но не может олицетворять клиента.<br />— Олицетворение. сервер может олицетворять контекст безопасности клиента в локальной системе.<br />-Делегирование. сервер может олицетворять контекст безопасности клиента в удаленных системах.<br />— Анонимно: сервер не может олицетворять или опознать клиента.<br />-None: уровень олицетворения не назначен.<br /><br /> Значение по умолчанию - Identification. Это атрибут типа <xref:System.Security.Principal.TokenImpersonationLevel>.|  
|`allowNtlm`|Если установить для данного свойства значение `true`, то проверка подлинности может понижаться до NTLM в том случае, если проверка Kerberos недоступна.<br /><br /> Если задать для этого свойства значение `false` Windows Communication Foundation (WCF), лучше будет создавать исключение, если используется NTLM. Обратите внимание, что установка для данного свойства значения `false` не предотвращает отправки учетных данных NTLM по сети.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.|  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [Обеспечение безопасности клиентов](../../../wcf/securing-clients.md)
- [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md)
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
