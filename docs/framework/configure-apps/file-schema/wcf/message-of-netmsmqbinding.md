---
title: <message> из <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 5a4a4e8b645ee2c607988ac3031af537c93ca8c0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736758"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="d8b2f-102">\<message> из \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="d8b2f-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="d8b2f-103">Определяет параметры безопасности сообщений SOAP для данной привязки `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  

## <a name="syntax"></a><span data-ttu-id="d8b2f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8b2f-104">Syntax</span></span>

```xml
<netMsmqBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
    </security>
  </binding>
</netMsmqBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d8b2f-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d8b2f-105">Attributes and Elements</span></span>

<span data-ttu-id="d8b2f-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d8b2f-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d8b2f-107">Attributes</span></span>

|<span data-ttu-id="d8b2f-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d8b2f-108">Attribute</span></span>|<span data-ttu-id="d8b2f-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="d8b2f-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="d8b2f-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="d8b2f-110">algorithmSuite</span></span>|<span data-ttu-id="d8b2f-111">Задает алгоритмы шифрования сообщений и ключей, которые используются для обеспечения безопасности на уровне сообщений для сообщений, которые отправляются с помощью транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-111">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="d8b2f-112">Значение по умолчанию — `Aes256`.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-112">The default value is `Aes256`.</span></span> <span data-ttu-id="d8b2f-113">Это атрибут типа <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-113">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="d8b2f-114">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="d8b2f-114">clientCredentialType</span></span>|<span data-ttu-id="d8b2f-115">Задает тип учетных данных, используемых при проверке подлинности клиента для сообщений, которые отправляются с помощью транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-115">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="d8b2f-116">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d8b2f-117">-None: Это позволяет службе взаимодействовать с анонимными клиентами.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-117">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="d8b2f-118">Как для службы, так и для клиента учетные данные не требуются.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-118">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="d8b2f-119">-Windows: Это позволяет обмениваться сообщениями SOAP в контексте с проверкой подлинности учетных данных Windows.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-119">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="d8b2f-120">В этом случае всегда выполняется проверка подлинности на основе Kerberos.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-120">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="d8b2f-121">-UserName: Это позволяет службе требовать проверку подлинности клиента с помощью учетных данных имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-121">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="d8b2f-122">Учетные данные в этом случае необходимо указать с помощью `clientCredentials` **предупреждения:** Windows Communication Foundation (WCF) не поддерживает отправку дайджеста пароля или получение ключей с помощью пароля и использование таких ключей для обеспечения безопасности сообщений.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-122">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="d8b2f-123">Таким образом, WCF обеспечивает защиту Exchange при использовании учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-123">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="d8b2f-124">В данном режиме требуется, чтобы сертификат службы был указан на стороне клиента при помощи поведения `clientCredential` и при помощи `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-124">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="d8b2f-125">-Certificate: Это позволяет службе требовать проверку подлинности клиента с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-125">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="d8b2f-126">В этом случае учетные данные клиента должны быть определены с помощью поведения `clientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-126">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="d8b2f-127">Учетные данные службы в данном случае должны быть определены с помощью поведения `clientCredentials`, которому задается значение `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-127">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="d8b2f-128">-CardSpace: Это позволяет службе требовать проверку подлинности клиента с помощью CardSpace.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-128">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="d8b2f-129">Необходимо определить `serviceCertificate` в поведении `clientCredential`.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-129">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="d8b2f-130">Значение по умолчанию — `Windows`.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-130">The default value is `Windows`.</span></span> <span data-ttu-id="d8b2f-131">Это атрибут типа <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-131">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="d8b2f-132">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d8b2f-132">Child Elements</span></span>

<span data-ttu-id="d8b2f-133">Нет</span><span class="sxs-lookup"><span data-stu-id="d8b2f-133">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d8b2f-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d8b2f-134">Parent Elements</span></span>

|<span data-ttu-id="d8b2f-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="d8b2f-135">Element</span></span>|<span data-ttu-id="d8b2f-136">Описание</span><span class="sxs-lookup"><span data-stu-id="d8b2f-136">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-netmsmqbinding.md)|<span data-ttu-id="d8b2f-137">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="d8b2f-137">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="d8b2f-138">См. также</span><span class="sxs-lookup"><span data-stu-id="d8b2f-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="d8b2f-139">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="d8b2f-139">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="d8b2f-140">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="d8b2f-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d8b2f-141">Привязки</span><span class="sxs-lookup"><span data-stu-id="d8b2f-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d8b2f-142">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="d8b2f-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d8b2f-143">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="d8b2f-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
