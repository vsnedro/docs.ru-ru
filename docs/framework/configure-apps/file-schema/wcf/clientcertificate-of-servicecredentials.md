---
description: 'Дополнительные сведения <clientCertificate> о: <serviceCredentials>'
title: <clientCertificate> из <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: c3e6378f9646ec30188e2de3d1c832f363904ad0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638825"
---
# <a name="clientcertificate-of-servicecredentials"></a>\<clientCertificate> из \<serviceCredentials>

Задает файл сертификата X.509, используемый для подписания и шифрования сообщений к клиенту от службы при дуплексном обмене данными.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCertificate>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  

 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<authentication>](authentication-of-clientcertificate-element.md)|Задает параметры проверки подлинности для сертификата клиента.|  
|[\<certificate>](certificate-of-clientcertificate-element.md)|Задает тип сертификата для использования.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.|  
  
## <a name="remarks"></a>Remarks  

 Этот элемент используется в случаях, когда служба должна получить клиентский сертификат заранее для безопасного обмена данными с клиентом. Это характерно для дуплексного обмена данными. В более распространенном варианте «запрос/отклик» клиент включает сертификат в запрос, который используется службой для шифрования и подписания отклика. Тем не менее при дуплексном обмене данными служба не получает запроса от клиента, и ей, таким образом, необходим сертификат клиента заранее, чтобы обеспечить защиту сообщения, отправляемого клиенту. Следовательно, необходимо получить сертификат клиента при согласовании вне диапазона и указать сертификат с помощью этого элемента. Дополнительные сведения о дуплексных службах см. [в разделе инструкции. Создание дуплексного контракта](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
 Заданный в этом элементе сертификат используется для шифрования сообщений к клиенту только для привязок, которые настроены с использованием режима проверки подлинности `MutualCertificateDuplex`.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>
- [Практическое руководство. Создание двухстороннего контракта](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)
- [Поведение безопасности](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md)
