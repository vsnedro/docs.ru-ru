---
title: <peerAuthentication>
ms.date: 03/30/2017
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
ms.openlocfilehash: a88a3c0bbbd36d2372520f70b3c5692757b35ade
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181561"
---
# \<peerAuthentication>

<span data-ttu-id="a234b-101">Задает параметры проверки подлинности для сертификата однорангового узла, используемого одноранговым узлом.</span><span class="sxs-lookup"><span data-stu-id="a234b-101">Specifies authentication settings for a peer certificate used by a peer node.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="a234b-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a234b-102">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a234b-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a234b-103">Attributes and Elements</span></span>  

 <span data-ttu-id="a234b-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a234b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a234b-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a234b-105">Attributes</span></span>  
  
|<span data-ttu-id="a234b-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a234b-106">Attribute</span></span>|<span data-ttu-id="a234b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a234b-107">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="a234b-108">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="a234b-108">Optional enumeration.</span></span> <span data-ttu-id="a234b-109">Задает один из трех режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="a234b-109">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="a234b-110">Это атрибут типа <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="a234b-110">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="a234b-111">Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="a234b-111">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="a234b-112">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="a234b-112">Optional string.</span></span> <span data-ttu-id="a234b-113">Задает тип и сборку, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="a234b-113">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="a234b-114">Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="a234b-114">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="a234b-115">Это атрибут типа <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="a234b-115">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="a234b-116">Windows Communication Foundation (WCF) предоставляет средство проверки однорангового сертификата по умолчанию, которое проверяет одноранговый сертификат в хранилище доверенных лиц.</span><span class="sxs-lookup"><span data-stu-id="a234b-116">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="a234b-117">Он также проверяет цепочку сертификатов вплоть до действительного корня.</span><span class="sxs-lookup"><span data-stu-id="a234b-117">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="a234b-118">Можно реализовать пользовательский модуль проверки для задания другого поведения и использовать этот атрибут для указания на пользовательский модуль проверки.</span><span class="sxs-lookup"><span data-stu-id="a234b-118">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="a234b-119">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="a234b-119">Optional enumeration.</span></span> <span data-ttu-id="a234b-120">Задает режим отзыва сертификатов.</span><span class="sxs-lookup"><span data-stu-id="a234b-120">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="a234b-121">Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="a234b-121">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="a234b-122">Система проверяет, что одноранговый сертификат не отозван, проводя его поиск в списке отозванных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="a234b-122">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="a234b-123">Эта проверка выполняется либо в сети, либо в кэшированном списке отзыва.</span><span class="sxs-lookup"><span data-stu-id="a234b-123">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="a234b-124">Проверку отзыва сертификатов можно отключить, задав этому атрибуту значение NoCheck.</span><span class="sxs-lookup"><span data-stu-id="a234b-124">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="a234b-125">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="a234b-125">Optional enumeration.</span></span> <span data-ttu-id="a234b-126">Указывает расположение доверенного хранилища, в котором система безопасности WCF проверяет сертификат однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="a234b-126">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="a234b-127">Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="a234b-127">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a234b-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a234b-128">Child Elements</span></span>  

 <span data-ttu-id="a234b-129">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a234b-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a234b-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a234b-130">Parent Elements</span></span>  
  
|<span data-ttu-id="a234b-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="a234b-131">Element</span></span>|<span data-ttu-id="a234b-132">Описание</span><span class="sxs-lookup"><span data-stu-id="a234b-132">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="a234b-133">Задает текущие учетные данные для однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="a234b-133">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a234b-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="a234b-134">Remarks</span></span>  

 <span data-ttu-id="a234b-135">Элемент `<authentication>` соответствует классу <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="a234b-135">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="a234b-136">Этот элемент задает модуль проверки, который вызывается во время проверки подлинности «от соседа к соседу» в сетке.</span><span class="sxs-lookup"><span data-stu-id="a234b-136">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="a234b-137">Когда новый одноранговый узел пытается установить соединение с соседним узлом, он передает свои учетные данные в отвечающий одноранговый узел.</span><span class="sxs-lookup"><span data-stu-id="a234b-137">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="a234b-138">Для проверки учетных данных удаленной стороны вызывается проверяющий элемент управления отвечающего узла.</span><span class="sxs-lookup"><span data-stu-id="a234b-138">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="a234b-139">Как только в сетке устанавливается одноранговое соединение, оба одноранговых узла выполняют взаимную проверку подлинности. Это означает, что вызываются проверяющие элементы управления на обоих концах.</span><span class="sxs-lookup"><span data-stu-id="a234b-139">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a234b-140">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a234b-140">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="a234b-141">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="a234b-141">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="a234b-142">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="a234b-142">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="a234b-143">[Проверка подлинности сообщений для однорангового канала](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="a234b-143">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="a234b-144">[Пользовательской проверка подлинности для однорангового канала](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="a234b-144">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="a234b-145">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="a234b-145">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
