---
description: 'Дополнительные сведения: <certificateValidation>'
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: a12e46487b4fb2ac8071ba1cf9bc5c6057ded060
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740071"
---
# \<certificateValidation>

Управляет параметрами, которые обработчики маркеров используют для проверки сертификатов. Эти параметры переопределяются, если для определенного обработчика настроен собственный проверяющий элемент управления.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidation>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation  
      certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
      revocationMode="NoCheck||Offline||Online"  
      trustedStoreLocation="CurrentLocation||LocalMachine" >  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|certificateValidationMode|<xref:System.ServiceModel.Security.X509CertificateValidationMode>Значение типа, указывающее режим проверки, используемый для сертификата X. 509. Значение по умолчанию — "PeerOrChainTrust". Чтобы указать настраиваемый проверяющий элемент управления, установите для этого атрибута значение "Custom" и укажите проверяющий элемент управления с помощью [\<certificateValidator>](certificatevalidator.md) элемента. Необязательный элемент.|  
|revocationMode|<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>Значение типа, указывающее режим отзыва, используемый для сертификата X. 509. Значение по умолчанию — "Online". Необязательный элемент.|  
|trustedStoreLocation|<xref:System.Security.Cryptography.X509Certificates.StoreLocation>Значение типа, указывающее хранилище сертификатов X. 509. Значение по умолчанию — LocalMachine. Необязательный элемент.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<certificateValidator>](certificatevalidator.md)|Указывает пользовательский тип для проверки сертификата. Этот тип используется только в том случае, если `certificateValidationMode` атрибут [\<certificateValidation>](certificatevalidation.md) элемента имеет значение Custom.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Задает параметры удостоверений уровня службы.|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.|  
  
## <a name="remarks"></a>Remarks  

 `<certificateValidation>`Элемент можно указать на уровне службы в `<identityConfiguration>` элементе или на уровне коллекции обработчика маркеров безопасности под `<securityTokenHandlerConfiguration>` элементом. Параметры коллекции обработчиков маркеров переопределяют указанные в службе. Некоторые обработчики маркеров позволяют указать параметры проверки сертификата в конфигурации. Параметры отдельных обработчиков маркеров переопределяют те, которые указаны как на уровне службы, так и в коллекции обработчиков маркеров безопасности.  
  
## <a name="example"></a>Пример  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
