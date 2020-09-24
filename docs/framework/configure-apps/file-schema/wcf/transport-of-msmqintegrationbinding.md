---
title: <transport> из <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
ms.openlocfilehash: 03e6236d1e89f16a460860f5dffff19b7bed8a0a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169834"
---
# <a name="transport-of-msmqintegrationbinding"></a><span data-ttu-id="972ad-102">\<transport> из \<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="972ad-102">\<transport> of \<msmqIntegrationBinding></span></span>

<span data-ttu-id="972ad-103">Определяет параметры безопасности для транспорта интеграции очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="972ad-103">Defines the security settings for the Message Queuing integration transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="972ad-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="972ad-104">Syntax</span></span>  
  
```xml  
<security>
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="972ad-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="972ad-105">Attributes and Elements</span></span>  

 <span data-ttu-id="972ad-106">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="972ad-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="972ad-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="972ad-107">Attributes</span></span>  
  
|<span data-ttu-id="972ad-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="972ad-108">Attribute</span></span>|<span data-ttu-id="972ad-109">Описание</span><span class="sxs-lookup"><span data-stu-id="972ad-109">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="972ad-110">Задает способ проверки подлинности сообщения транспортом MSMQ.</span><span class="sxs-lookup"><span data-stu-id="972ad-110">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="972ad-111">Если задано значение `None`, атрибуту `msmqProtectionLevel` также должно быть присвоено значение `None`.</span><span class="sxs-lookup"><span data-stu-id="972ad-111">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="972ad-112">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="972ad-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="972ad-113">-None — без проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="972ad-113">-   None: No authentication.</span></span><br /><span data-ttu-id="972ad-114">-WindowsDomain. механизм проверки подлинности использует Active Directory для получения сертификата X. 509 для идентификатора безопасности, связанного с сообщением.</span><span class="sxs-lookup"><span data-stu-id="972ad-114">-   WindowsDomain: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="972ad-115">Затем это используется для проверки ACL очереди, чтобы убедиться в наличии у пользователя разрешений для записи в очередь.</span><span class="sxs-lookup"><span data-stu-id="972ad-115">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="972ad-116">-Certificate: канал получает сертификат из хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="972ad-116">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="972ad-117">Значение по умолчанию - WindowsDomain.</span><span class="sxs-lookup"><span data-stu-id="972ad-117">The default value is WindowsDomain.</span></span> <span data-ttu-id="972ad-118">Это атрибут типа <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="972ad-118">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="972ad-119">Задает алгоритм, который будет использоваться для шифрования сообщений при их передаче между диспетчерами очередей сообщений.</span><span class="sxs-lookup"><span data-stu-id="972ad-119">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="972ad-120">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="972ad-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="972ad-121">- RC4Stream</span><span class="sxs-lookup"><span data-stu-id="972ad-121">-   RC4Stream</span></span><br /><span data-ttu-id="972ad-122">— AES</span><span class="sxs-lookup"><span data-stu-id="972ad-122">-   AES</span></span><br /><br /> <span data-ttu-id="972ad-123">Значение по умолчанию - RC4Stream.</span><span class="sxs-lookup"><span data-stu-id="972ad-123">The default value is RC4Stream.</span></span> <span data-ttu-id="972ad-124">Это атрибут типа <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="972ad-124">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="972ad-125">Задает способ обеспечения безопасности сообщения на уровне транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="972ad-125">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="972ad-126">Шифрование гарантирует целостность сообщений, а EncryptAndSign обеспечивает как целостность сообщений, так и неподдельность. то есть сообщение действительно поступает от отправителя, а отправитель — от того, кто говорят.</span><span class="sxs-lookup"><span data-stu-id="972ad-126">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who they say they are.</span></span><br /><br /> <span data-ttu-id="972ad-127">Допустимые значения включают следующие:</span><span class="sxs-lookup"><span data-stu-id="972ad-127">-   Valid values include the following:</span></span><br /><span data-ttu-id="972ad-128">-None: защита отсутствует.</span><span class="sxs-lookup"><span data-stu-id="972ad-128">-   None: No protection.</span></span><br /><span data-ttu-id="972ad-129">-Sign: сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="972ad-129">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="972ad-130">-EncryptAndSign: сообщения шифруются и подписываются.</span><span class="sxs-lookup"><span data-stu-id="972ad-130">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="972ad-131">Значение по умолчанию - Sign.</span><span class="sxs-lookup"><span data-stu-id="972ad-131">The default value is Sign.</span></span> <span data-ttu-id="972ad-132">Это атрибут типа ProtectionLevel.</span><span class="sxs-lookup"><span data-stu-id="972ad-132">This attribute is of type ProtectionLevel.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="972ad-133">— Указывает алгоритм, используемый при вычислении дайджеста как части сигнатур.</span><span class="sxs-lookup"><span data-stu-id="972ad-133">-   Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="972ad-134">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="972ad-134">Valid values include the following:</span></span><br /><span data-ttu-id="972ad-135">-MD5</span><span class="sxs-lookup"><span data-stu-id="972ad-135">-   MD5</span></span><br /><span data-ttu-id="972ad-136">-SHA1</span><span class="sxs-lookup"><span data-stu-id="972ad-136">-   SHA1</span></span><br /><span data-ttu-id="972ad-137">-SHA256</span><span class="sxs-lookup"><span data-stu-id="972ad-137">-   SHA256</span></span><br /><span data-ttu-id="972ad-138">-SHA512</span><span class="sxs-lookup"><span data-stu-id="972ad-138">-   SHA512</span></span><br /><br /> <span data-ttu-id="972ad-139">Значение по умолчанию - SHA1.</span><span class="sxs-lookup"><span data-stu-id="972ad-139">The default value is SHA1.</span></span> <span data-ttu-id="972ad-140">Это атрибут типа <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="972ad-140">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="972ad-141">Из-за проблем с MD5 и SHA1 Корпорация Майкрософт рекомендует использовать SHA256 или более высокий уровень.</span><span class="sxs-lookup"><span data-stu-id="972ad-141">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="972ad-142">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="972ad-142">Child Elements</span></span>  

 <span data-ttu-id="972ad-143">Нет</span><span class="sxs-lookup"><span data-stu-id="972ad-143">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="972ad-144">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="972ad-144">Parent Elements</span></span>  
  
|<span data-ttu-id="972ad-145">Элемент</span><span class="sxs-lookup"><span data-stu-id="972ad-145">Element</span></span>|<span data-ttu-id="972ad-146">Описание</span><span class="sxs-lookup"><span data-stu-id="972ad-146">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-basichttpbinding.md)|<span data-ttu-id="972ad-147">Определяет параметры безопасности для привязки MSMQ.</span><span class="sxs-lookup"><span data-stu-id="972ad-147">Defines the security settings for a MSMQ binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="972ad-148">Remarks</span><span class="sxs-lookup"><span data-stu-id="972ad-148">Remarks</span></span>  

 <span data-ttu-id="972ad-149">Данный элемент инкапсулирует параметры безопасности для транспорта интеграции очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="972ad-149">This element encapsulates the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="972ad-150">Данные параметры одинаковы для интеграции очереди сообщений и использующих очереди транспортов.</span><span class="sxs-lookup"><span data-stu-id="972ad-150">The settings are the same for both the Message Queuing integration and queued transports.</span></span> <span data-ttu-id="972ad-151">Это позволяет задать режим проверки подлинности, алгоритм шифрования, алгоритм SHA и уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="972ad-151">It enables you to set the Authentication Mode, Encryption Algorithm, Secure Hash Algorithm, and Protection Level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="972ad-152">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="972ad-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="972ad-153">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="972ad-153">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="972ad-154">Привязки</span><span class="sxs-lookup"><span data-stu-id="972ad-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="972ad-155">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="972ad-155">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="972ad-156">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="972ad-156">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
