---
title: Элемент <peerAuthentication>
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 7e4f86c361dc3ade5dedf4017921516357bb9a58
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181587"
---
# <a name="peerauthentication-element"></a><span data-ttu-id="2e65a-102">Элемент \<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="2e65a-102">\<peerAuthentication> Element</span></span>

<span data-ttu-id="2e65a-103">Задает параметры проверки подлинности для одноранговых клиентов.</span><span class="sxs-lookup"><span data-stu-id="2e65a-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="2e65a-104">Дополнительные сведения о одноранговых программах см. в разделе одноранговая [сеть](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="2e65a-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="2e65a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e65a-105">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e65a-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2e65a-106">Attributes and Elements</span></span>  

 <span data-ttu-id="2e65a-107">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2e65a-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e65a-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2e65a-108">Attributes</span></span>  
  
|<span data-ttu-id="2e65a-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2e65a-109">Attribute</span></span>|<span data-ttu-id="2e65a-110">Описание</span><span class="sxs-lookup"><span data-stu-id="2e65a-110">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="2e65a-111">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="2e65a-111">Optional string.</span></span> <span data-ttu-id="2e65a-112">Тип и сборка, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="2e65a-112">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="2e65a-113">Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="2e65a-113">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="2e65a-114">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="2e65a-114">Optional enumeration.</span></span> <span data-ttu-id="2e65a-115">Задает один из трех режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="2e65a-115">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="2e65a-116">Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="2e65a-116">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="2e65a-117">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="2e65a-117">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="2e65a-118">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="2e65a-118">Optional enumeration.</span></span> <span data-ttu-id="2e65a-119">Один из режимов, используемых для проверки списков отозванных сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="2e65a-119">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="2e65a-120">Значение по умолчанию — `Online`.</span><span class="sxs-lookup"><span data-stu-id="2e65a-120">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="2e65a-121">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="2e65a-121">Optional enumeration.</span></span> <span data-ttu-id="2e65a-122">Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="2e65a-122">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="2e65a-123">Данное значение используется при согласовании сертификата службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="2e65a-123">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="2e65a-124">Проверка выполняется для хранилища **доверенных лиц** в указанном расположении магазина.</span><span class="sxs-lookup"><span data-stu-id="2e65a-124">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="2e65a-125">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="2e65a-125">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="2e65a-126">Атрибут customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="2e65a-126">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="2e65a-127">Значение</span><span class="sxs-lookup"><span data-stu-id="2e65a-127">Value</span></span>|<span data-ttu-id="2e65a-128">Описание</span><span class="sxs-lookup"><span data-stu-id="2e65a-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2e65a-129">Строка</span><span class="sxs-lookup"><span data-stu-id="2e65a-129">String</span></span>|<span data-ttu-id="2e65a-130">Задает имя типа и сборку, а также другие данные, используемые для поиска типа.</span><span class="sxs-lookup"><span data-stu-id="2e65a-130">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="2e65a-131">Требуется, как минимум, пространство имен и имя типа.</span><span class="sxs-lookup"><span data-stu-id="2e65a-131">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="2e65a-132">К дополнительным сведениям относятся: имя сборки, номер версии, язык и региональные параметры и маркер открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="2e65a-132">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="2e65a-133">Атрибут certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="2e65a-133">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="2e65a-134">Значение</span><span class="sxs-lookup"><span data-stu-id="2e65a-134">Value</span></span>|<span data-ttu-id="2e65a-135">Описание</span><span class="sxs-lookup"><span data-stu-id="2e65a-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2e65a-136">Перечисление</span><span class="sxs-lookup"><span data-stu-id="2e65a-136">Enumeration</span></span>|<span data-ttu-id="2e65a-137">Одно из следующих значений: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="2e65a-137">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="2e65a-138">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="2e65a-138">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="2e65a-139">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="2e65a-139">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="2e65a-140">Атрибут revocationMode</span><span class="sxs-lookup"><span data-stu-id="2e65a-140">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="2e65a-141">Значение</span><span class="sxs-lookup"><span data-stu-id="2e65a-141">Value</span></span>|<span data-ttu-id="2e65a-142">Описание</span><span class="sxs-lookup"><span data-stu-id="2e65a-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2e65a-143">Перечисление</span><span class="sxs-lookup"><span data-stu-id="2e65a-143">Enumeration</span></span>|<span data-ttu-id="2e65a-144">Одно из следующих значений: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="2e65a-144">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="2e65a-145">Значение по умолчанию — `Online`.</span><span class="sxs-lookup"><span data-stu-id="2e65a-145">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="2e65a-146">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="2e65a-146">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="2e65a-147">Атрибут trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="2e65a-147">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="2e65a-148">Значение</span><span class="sxs-lookup"><span data-stu-id="2e65a-148">Value</span></span>|<span data-ttu-id="2e65a-149">Описание</span><span class="sxs-lookup"><span data-stu-id="2e65a-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2e65a-150">Перечисление</span><span class="sxs-lookup"><span data-stu-id="2e65a-150">Enumeration</span></span>|<span data-ttu-id="2e65a-151">Одно из следующих значений: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="2e65a-151">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="2e65a-152">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="2e65a-152">The default is `CurrentUser`.</span></span> <span data-ttu-id="2e65a-153">Если клиентское приложение выполняется под учетной записью системы, сертификат обычно находится в расположении `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="2e65a-153">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="2e65a-154">Если клиентское приложение выполняется под учетной записью пользователя, то сертификат обычно находится в расположении `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="2e65a-154">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e65a-155">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2e65a-155">Child Elements</span></span>  

 <span data-ttu-id="2e65a-156">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2e65a-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2e65a-157">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2e65a-157">Parent Elements</span></span>  
  
|<span data-ttu-id="2e65a-158">Элемент</span><span class="sxs-lookup"><span data-stu-id="2e65a-158">Element</span></span>|<span data-ttu-id="2e65a-159">Описание</span><span class="sxs-lookup"><span data-stu-id="2e65a-159">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="2e65a-160">Задает учетные данные, используемые для проверки подлинности клиента при подключении к одноранговой службе.</span><span class="sxs-lookup"><span data-stu-id="2e65a-160">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e65a-161">Remarks</span><span class="sxs-lookup"><span data-stu-id="2e65a-161">Remarks</span></span>  

 <span data-ttu-id="2e65a-162">Элемент `<authentication>` соответствует классу <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="2e65a-162">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="2e65a-163">Этот элемент задает модуль проверки, который вызывается во время проверки подлинности «от соседа к соседу» в сетке.</span><span class="sxs-lookup"><span data-stu-id="2e65a-163">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="2e65a-164">Когда новый одноранговый узел пытается установить соединение с соседним узлом, он передает свои учетные данные в отвечающий одноранговый узел.</span><span class="sxs-lookup"><span data-stu-id="2e65a-164">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="2e65a-165">Для проверки учетных данных удаленной стороны вызывается проверяющий элемент управления отвечающего узла.</span><span class="sxs-lookup"><span data-stu-id="2e65a-165">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="2e65a-166">Как только в сетке устанавливается одноранговое соединение, оба одноранговых узла выполняют взаимную проверку подлинности. Это означает, что вызываются проверяющие элементы управления на обоих концах.</span><span class="sxs-lookup"><span data-stu-id="2e65a-166">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e65a-167">Пример</span><span class="sxs-lookup"><span data-stu-id="2e65a-167">Example</span></span>  

 <span data-ttu-id="2e65a-168">В приведенном ниже примере кода режиму проверки сертификата присваивается значение `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="2e65a-168">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <peerAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="2e65a-169">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2e65a-169">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="2e65a-170">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="2e65a-170">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="2e65a-171">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="2e65a-171">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="2e65a-172">[Проверка подлинности сообщений для однорангового канала](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="2e65a-172">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="2e65a-173">[Пользовательской проверка подлинности для однорангового канала](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="2e65a-173">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="2e65a-174">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="2e65a-174">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
