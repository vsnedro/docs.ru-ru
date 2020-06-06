---
title: <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: c6183a8d27d56c7199b815ccb31b06f983a51b33
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398390"
---
# \<messageSenderAuthentication>
<span data-ttu-id="15119-101">Задает параметры проверки подлинности для однорангового сертификата, используемого отправителем сообщения.</span><span class="sxs-lookup"><span data-stu-id="15119-101">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="15119-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15119-102">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15119-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="15119-103">Attributes and Elements</span></span>  
 <span data-ttu-id="15119-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="15119-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15119-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="15119-105">Attributes</span></span>  
  
|<span data-ttu-id="15119-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="15119-106">Attribute</span></span>|<span data-ttu-id="15119-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="15119-107">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="15119-108">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="15119-108">Optional enumeration.</span></span> <span data-ttu-id="15119-109">Задает один из пяти режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="15119-109">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="15119-110">Это атрибут типа <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="15119-110">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="15119-111">Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="15119-111">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="15119-112">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="15119-112">Optional string.</span></span> <span data-ttu-id="15119-113">Задает тип и сборку, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="15119-113">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="15119-114">Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="15119-114">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="15119-115">Это атрибут типа <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="15119-115">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="15119-116">Windows Communication Foundation (WCF) предоставляет средство проверки однорангового сертификата по умолчанию, которое проверяет одноранговый сертификат в хранилище доверенных лиц.</span><span class="sxs-lookup"><span data-stu-id="15119-116">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="15119-117">Он также проверяет цепочку сертификатов вплоть до действительного корня.</span><span class="sxs-lookup"><span data-stu-id="15119-117">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="15119-118">Можно реализовать пользовательский модуль проверки для задания другого поведения и использовать этот атрибут для указания на пользовательский модуль проверки.</span><span class="sxs-lookup"><span data-stu-id="15119-118">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="15119-119">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="15119-119">Optional enumeration.</span></span> <span data-ttu-id="15119-120">Задает режим отзыва сертификатов.</span><span class="sxs-lookup"><span data-stu-id="15119-120">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="15119-121">Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="15119-121">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="15119-122">Система проверяет, что одноранговый сертификат не отозван, проводя его поиск в списке отозванных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="15119-122">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="15119-123">Эта проверка выполняется либо в сети, либо в кэшированном списке отзыва.</span><span class="sxs-lookup"><span data-stu-id="15119-123">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="15119-124">Проверку отзыва сертификатов можно отключить, задав этому атрибуту значение NoCheck.</span><span class="sxs-lookup"><span data-stu-id="15119-124">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="15119-125">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="15119-125">Optional enumeration.</span></span> <span data-ttu-id="15119-126">Указывает расположение доверенного хранилища, в котором система безопасности WCF проверяет сертификат однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="15119-126">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="15119-127">Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="15119-127">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15119-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="15119-128">Child Elements</span></span>  
 <span data-ttu-id="15119-129">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="15119-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15119-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="15119-130">Parent Elements</span></span>  
  
|<span data-ttu-id="15119-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="15119-131">Element</span></span>|<span data-ttu-id="15119-132">Описание</span><span class="sxs-lookup"><span data-stu-id="15119-132">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="15119-133">Задает текущие учетные данные для однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="15119-133">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15119-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="15119-134">Remarks</span></span>  
 <span data-ttu-id="15119-135">Этот элемент должен быть настроен, если выбрана проверка подлинности сообщения.</span><span class="sxs-lookup"><span data-stu-id="15119-135">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="15119-136">Для выходных каналов каждое сообщение подписывается с помощью сертификата, предоставленного [\<certificate>](certificate-element.md) .</span><span class="sxs-lookup"><span data-stu-id="15119-136">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="15119-137">Во всех сообщениях перед доставкой приложению проверяются учетные данные сообщения с помощью модуля проверки, заданного атрибутом `customCertificateValidatorType` этого элемента.</span><span class="sxs-lookup"><span data-stu-id="15119-137">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="15119-138">Модуль проверки может принять или отклонить учетные данные.</span><span class="sxs-lookup"><span data-stu-id="15119-138">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15119-139">См. также</span><span class="sxs-lookup"><span data-stu-id="15119-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- [<span data-ttu-id="15119-140">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="15119-140">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="15119-141">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="15119-141">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="15119-142">[Проверка подлинности сообщений для однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="15119-142">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="15119-143">[Пользовательской проверка подлинности для однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="15119-143">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="15119-144">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="15119-144">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
