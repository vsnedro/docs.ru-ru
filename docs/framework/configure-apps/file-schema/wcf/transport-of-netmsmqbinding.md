---
title: <transport> из <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: cc47c01cccc931e81ba57ab37ad9e3accfaa693b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152935"
---
# <a name="transport-of-netmsmqbinding"></a><span data-ttu-id="da61b-102">\<transport> из \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="da61b-102">\<transport> of \<netMsmqBinding></span></span>
<span data-ttu-id="da61b-103">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="da61b-103">Defines the transport security settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="da61b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da61b-104">Syntax</span></span>  
  
```xml  
<netMsmqBinding>
  <binding>
    <security>
      <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    </security>
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da61b-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="da61b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="da61b-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="da61b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da61b-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="da61b-107">Attributes</span></span>  
  
|<span data-ttu-id="da61b-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="da61b-108">Attribute</span></span>|<span data-ttu-id="da61b-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="da61b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="da61b-110">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="da61b-110">msmqAuthenticationMode</span></span>|<span data-ttu-id="da61b-111">Задает способ проверки подлинности сообщения транспортом MSMQ.</span><span class="sxs-lookup"><span data-stu-id="da61b-111">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="da61b-112">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="da61b-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="da61b-113">-None — без проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="da61b-113">-   None: No authentication.</span></span><br /><span data-ttu-id="da61b-114">-WindowsDomain. механизм проверки подлинности использует Active Directory для получения сертификата X. 509 для идентификатора безопасности, связанного с сообщением.</span><span class="sxs-lookup"><span data-stu-id="da61b-114">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="da61b-115">Затем он используется для проверки списка управления доступом для очереди с целью удостовериться, что пользователь имеет разрешение на запись в очередь.</span><span class="sxs-lookup"><span data-stu-id="da61b-115">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="da61b-116">-Certificate: канал получает сертификат из хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="da61b-116">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="da61b-117">Значение по умолчанию — `WindowsDomain`.</span><span class="sxs-lookup"><span data-stu-id="da61b-117">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="da61b-118">Если данный атрибут имеет значение `None`, то атрибут `msmqProtectionLevel` также должен иметь значение `None`.</span><span class="sxs-lookup"><span data-stu-id="da61b-118">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="da61b-119">Это атрибут типа <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="da61b-119">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="da61b-120">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="da61b-120">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="da61b-121">Задает алгоритм, который будет использоваться для шифрования сообщений при их передаче между диспетчерами очередей сообщений.</span><span class="sxs-lookup"><span data-stu-id="da61b-121">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="da61b-122">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="da61b-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="da61b-123">- RC4Stream</span><span class="sxs-lookup"><span data-stu-id="da61b-123">-   RC4Stream</span></span><br /><span data-ttu-id="da61b-124">— AES</span><span class="sxs-lookup"><span data-stu-id="da61b-124">-   AES</span></span><br /><span data-ttu-id="da61b-125">— Значение по умолчанию — `RC4Stream` .</span><span class="sxs-lookup"><span data-stu-id="da61b-125">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="da61b-126">Это атрибут типа <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="da61b-126">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="da61b-127">msmqprotectionLevel</span><span class="sxs-lookup"><span data-stu-id="da61b-127">msmqProtectionLevel</span></span>|<span data-ttu-id="da61b-128">Задает способ обеспечения безопасности сообщений на уровне транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="da61b-128">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="da61b-129">Шифрование обеспечивает целостность сообщения, тогда как подпись и шифрование обеспечивают как целостность сообщения, так и неподдельность.</span><span class="sxs-lookup"><span data-stu-id="da61b-129">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="da61b-130">То есть сообщение действительно поступило от отправителя, а отправитель — от того, кто говорят.</span><span class="sxs-lookup"><span data-stu-id="da61b-130">That is, the message indeed came from the sender and the sender is who they say they are.</span></span> <span data-ttu-id="da61b-131">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="da61b-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="da61b-132">-None: защита отсутствует.</span><span class="sxs-lookup"><span data-stu-id="da61b-132">-   None: No protection.</span></span><br /><span data-ttu-id="da61b-133">-Sign: сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="da61b-133">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="da61b-134">-EncryptAndSign: сообщения шифруются и подписываются.</span><span class="sxs-lookup"><span data-stu-id="da61b-134">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="da61b-135">— Значение по умолчанию — `Sign` .</span><span class="sxs-lookup"><span data-stu-id="da61b-135">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="da61b-136">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="da61b-136">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="da61b-137">Указывает алгоритм хэширования, который будет использоваться при вычислении хэш-кода сообщения.</span><span class="sxs-lookup"><span data-stu-id="da61b-137">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="da61b-138">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="da61b-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="da61b-139">-MD5</span><span class="sxs-lookup"><span data-stu-id="da61b-139">-   MD5</span></span><br /><span data-ttu-id="da61b-140">-SHA1</span><span class="sxs-lookup"><span data-stu-id="da61b-140">-   SHA1</span></span><br /><span data-ttu-id="da61b-141">-SHA256</span><span class="sxs-lookup"><span data-stu-id="da61b-141">-   SHA256</span></span><br /><span data-ttu-id="da61b-142">-SHA512</span><span class="sxs-lookup"><span data-stu-id="da61b-142">-   SHA512</span></span><br /><br /> <span data-ttu-id="da61b-143">Значение по умолчанию — `SHA1`.</span><span class="sxs-lookup"><span data-stu-id="da61b-143">The default is `SHA1`.</span></span> <span data-ttu-id="da61b-144">Это атрибут типа <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="da61b-144">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="da61b-145">Из-за проблем с MD5 и SHA1 Корпорация Майкрософт рекомендует использовать SHA256 или более высокий уровень.</span><span class="sxs-lookup"><span data-stu-id="da61b-145">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da61b-146">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="da61b-146">Child Elements</span></span>  
 <span data-ttu-id="da61b-147">Нет</span><span class="sxs-lookup"><span data-stu-id="da61b-147">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da61b-148">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="da61b-148">Parent Elements</span></span>  
  
|<span data-ttu-id="da61b-149">Элемент</span><span class="sxs-lookup"><span data-stu-id="da61b-149">Element</span></span>|<span data-ttu-id="da61b-150">Описание</span><span class="sxs-lookup"><span data-stu-id="da61b-150">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netmsmqbinding.md)|<span data-ttu-id="da61b-151">Определяет параметры безопасности для поставленного в очередь транспорта.</span><span class="sxs-lookup"><span data-stu-id="da61b-151">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="da61b-152">См. также</span><span class="sxs-lookup"><span data-stu-id="da61b-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="da61b-153">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="da61b-153">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="da61b-154">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="da61b-154">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="da61b-155">Привязки</span><span class="sxs-lookup"><span data-stu-id="da61b-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="da61b-156">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="da61b-156">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="da61b-157">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="da61b-157">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
