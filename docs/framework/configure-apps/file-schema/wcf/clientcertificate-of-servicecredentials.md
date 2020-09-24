---
title: <clientCertificate> из <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: 9df49777efc80f425cad3b353f95db523a027214
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148921"
---
# <a name="clientcertificate-of-servicecredentials"></a><span data-ttu-id="98b2b-102">\<clientCertificate> из \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="98b2b-102">\<clientCertificate> of \<serviceCredentials></span></span>

<span data-ttu-id="98b2b-103">Задает файл сертификата X.509, используемый для подписания и шифрования сообщений к клиенту от службы при дуплексном обмене данными.</span><span class="sxs-lookup"><span data-stu-id="98b2b-103">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="98b2b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98b2b-104">Syntax</span></span>  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98b2b-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="98b2b-105">Attributes and Elements</span></span>  

 <span data-ttu-id="98b2b-106">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="98b2b-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98b2b-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="98b2b-107">Attributes</span></span>  

 <span data-ttu-id="98b2b-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="98b2b-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="98b2b-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="98b2b-109">Child Elements</span></span>  
  
|<span data-ttu-id="98b2b-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="98b2b-110">Element</span></span>|<span data-ttu-id="98b2b-111">Описание</span><span class="sxs-lookup"><span data-stu-id="98b2b-111">Description</span></span>|  
|-------------|-----------------|  
|[\<authentication>](authentication-of-clientcertificate-element.md)|<span data-ttu-id="98b2b-112">Задает параметры проверки подлинности для сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="98b2b-112">Specifies authentication options for the client certificate.</span></span>|  
|[\<certificate>](certificate-of-clientcertificate-element.md)|<span data-ttu-id="98b2b-113">Задает тип сертификата для использования.</span><span class="sxs-lookup"><span data-stu-id="98b2b-113">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="98b2b-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="98b2b-114">Parent Elements</span></span>  
  
|<span data-ttu-id="98b2b-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="98b2b-115">Element</span></span>|<span data-ttu-id="98b2b-116">Описание</span><span class="sxs-lookup"><span data-stu-id="98b2b-116">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="98b2b-117">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="98b2b-117">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98b2b-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="98b2b-118">Remarks</span></span>  

 <span data-ttu-id="98b2b-119">Этот элемент используется в случаях, когда служба должна получить клиентский сертификат заранее для безопасного обмена данными с клиентом.</span><span class="sxs-lookup"><span data-stu-id="98b2b-119">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="98b2b-120">Это характерно для дуплексного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="98b2b-120">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="98b2b-121">В более распространенном варианте «запрос/отклик» клиент включает сертификат в запрос, который используется службой для шифрования и подписания отклика.</span><span class="sxs-lookup"><span data-stu-id="98b2b-121">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="98b2b-122">Тем не менее при дуплексном обмене данными служба не получает запроса от клиента, и ей, таким образом, необходим сертификат клиента заранее, чтобы обеспечить защиту сообщения, отправляемого клиенту.</span><span class="sxs-lookup"><span data-stu-id="98b2b-122">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="98b2b-123">Следовательно, необходимо получить сертификат клиента при согласовании вне диапазона и указать сертификат с помощью этого элемента.</span><span class="sxs-lookup"><span data-stu-id="98b2b-123">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="98b2b-124">Дополнительные сведения о дуплексных службах см. [в разделе инструкции. Создание дуплексного контракта](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="98b2b-124">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="98b2b-125">Заданный в этом элементе сертификат используется для шифрования сообщений к клиенту только для привязок, которые настроены с использованием режима проверки подлинности `MutualCertificateDuplex`.</span><span class="sxs-lookup"><span data-stu-id="98b2b-125">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98b2b-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="98b2b-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>
- [<span data-ttu-id="98b2b-127">Практическое руководство. Создание двухстороннего контракта</span><span class="sxs-lookup"><span data-stu-id="98b2b-127">How to: Create a Duplex Contract</span></span>](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="98b2b-128">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="98b2b-128">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="98b2b-129">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="98b2b-129">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
