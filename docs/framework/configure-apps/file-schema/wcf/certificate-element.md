---
title: Элемент <certificate>
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: 8cc0404a5896dd23cffce6f1f77b91a2f01f23d2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151094"
---
# <a name="certificate-element"></a><span data-ttu-id="c8fe7-102">Элемент \<certificate></span><span class="sxs-lookup"><span data-stu-id="c8fe7-102">\<certificate> Element</span></span>

<span data-ttu-id="c8fe7-103">Задает сертификат X.509, используемый для подписи и шифрования сообщений для клиентов одноранговых сетей.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="c8fe7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8fe7-104">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8fe7-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c8fe7-105">Attributes and Elements</span></span>  

 <span data-ttu-id="c8fe7-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8fe7-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c8fe7-107">Attributes</span></span>  
  
|<span data-ttu-id="c8fe7-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c8fe7-108">Attribute</span></span>|<span data-ttu-id="c8fe7-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c8fe7-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="c8fe7-110">Строка, содержащая значение для поиска в хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="c8fe7-111">Тип, указанный в этом атрибуте, должен отвечать требованиям заданного значения `x509FindType`.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-111">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="c8fe7-112">Значением по умолчанию является пустая строка.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="c8fe7-113">Задает расположение хранилища сертификатов Х.509, которое клиент может использовать для проверки сертификата однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-113">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="c8fe7-114">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c8fe7-115">-LocalMachine — хранилище сертификатов, назначенное локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="c8fe7-116">-CurrentUser: хранилище сертификатов, назначенное текущему пользователю.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="c8fe7-117">По умолчанию используется значение LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="c8fe7-118">Задает имя открываемого хранилища сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="c8fe7-119">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c8fe7-120">-AddressBook: хранилище сертификатов для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="c8fe7-121">-Аусрут: хранилище сертификатов для сторонних центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="c8fe7-121">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="c8fe7-122">-CertificateAuthority: хранилище сертификатов для промежуточных центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="c8fe7-122">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="c8fe7-123">— Запрещено: хранилище сертификатов для отозванных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="c8fe7-124">-My: хранилище сертификатов для личных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="c8fe7-125">— Root: хранилище сертификатов для доверенных корневых центров сертификации (CAs).</span><span class="sxs-lookup"><span data-stu-id="c8fe7-125">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="c8fe7-126">-TrustedPeople: хранилище сертификатов для непосредственно доверенных лиц и ресурсов.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-126">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="c8fe7-127">-Трустедпублишер: хранилище сертификатов для непосредственно доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-127">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="c8fe7-128">Значение по умолчанию - My.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="c8fe7-129">Определяет тип поиска сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="c8fe7-130">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c8fe7-131">-(FindByThumbprint</span><span class="sxs-lookup"><span data-stu-id="c8fe7-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="c8fe7-132">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="c8fe7-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="c8fe7-133">-Финдбисубжектдистингуишеднаме</span><span class="sxs-lookup"><span data-stu-id="c8fe7-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="c8fe7-134">-Финдбиссуернаме</span><span class="sxs-lookup"><span data-stu-id="c8fe7-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="c8fe7-135">-Финдбиссуердистингуишеднаме</span><span class="sxs-lookup"><span data-stu-id="c8fe7-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="c8fe7-136">-Финдбисериалнумбер</span><span class="sxs-lookup"><span data-stu-id="c8fe7-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="c8fe7-137">-Финдбитимевалид</span><span class="sxs-lookup"><span data-stu-id="c8fe7-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="c8fe7-138">-Финдбитименотетвалид</span><span class="sxs-lookup"><span data-stu-id="c8fe7-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="c8fe7-139">-Финдбитемплатенаме</span><span class="sxs-lookup"><span data-stu-id="c8fe7-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="c8fe7-140">-Финдбяппликатионполици</span><span class="sxs-lookup"><span data-stu-id="c8fe7-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="c8fe7-141">-Финдбицертификатеполици</span><span class="sxs-lookup"><span data-stu-id="c8fe7-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="c8fe7-142">-Финдбекстенсион</span><span class="sxs-lookup"><span data-stu-id="c8fe7-142">-   FindByExtension</span></span><br /><span data-ttu-id="c8fe7-143">-Финдбикэйусаже</span><span class="sxs-lookup"><span data-stu-id="c8fe7-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="c8fe7-144">-Финдбисубжекткэйидентифиер</span><span class="sxs-lookup"><span data-stu-id="c8fe7-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="c8fe7-145">Тип, указанный в атрибуте `findValue`, должен отвечать требованиям заданного значения `X509FindType`.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="c8fe7-146">Значение по умолчанию - FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8fe7-147">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c8fe7-147">Child Elements</span></span>  

 <span data-ttu-id="c8fe7-148">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c8fe7-149">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c8fe7-149">Parent Elements</span></span>  
  
|<span data-ttu-id="c8fe7-150">Элемент</span><span class="sxs-lookup"><span data-stu-id="c8fe7-150">Element</span></span>|<span data-ttu-id="c8fe7-151">Описание</span><span class="sxs-lookup"><span data-stu-id="c8fe7-151">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="c8fe7-152">Задает учетные данные, используемые при проверке подлинности одноранговых клиентов.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-152">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8fe7-153">Remarks</span><span class="sxs-lookup"><span data-stu-id="c8fe7-153">Remarks</span></span>  

 <span data-ttu-id="c8fe7-154">Этот элемент конфигурации содержит экземпляр X509Certificate2, используемый при проверке подлинности соседей в сетке узлов.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-154">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="c8fe7-155">Дополнительные сведения о одноранговых программах см. в разделе одноранговая [сеть](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="c8fe7-155">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8fe7-156">Пример</span><span class="sxs-lookup"><span data-stu-id="c8fe7-156">Example</span></span>  

 <span data-ttu-id="c8fe7-157">В следующем примере кода показывается, как найти сертификат, используемый в сценарии с одноранговой сетью.</span><span class="sxs-lookup"><span data-stu-id="c8fe7-157">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="c8fe7-158">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c8fe7-158">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="c8fe7-159">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="c8fe7-159">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="c8fe7-160">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="c8fe7-160">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="c8fe7-161">[Проверка подлинности сообщений для однорангового канала](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c8fe7-161">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="c8fe7-162">[Пользовательской проверка подлинности для однорангового канала](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c8fe7-162">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="c8fe7-163">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="c8fe7-163">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
