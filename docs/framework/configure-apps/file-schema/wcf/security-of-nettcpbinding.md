---
title: <security> из <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 286cd191-4fd5-4c4e-a223-9c71cf7fdead
ms.openlocfilehash: d39e3e5e655817aa91c5301274a860a00a6ab7ef
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169990"
---
# <a name="security-of-nettcpbinding"></a><span data-ttu-id="92345-102">\<security> из \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="92345-102">\<security> of \<netTcpBinding></span></span>

<span data-ttu-id="92345-103">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="92345-103">Defines the security settings for a binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="92345-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92345-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             protectionLevel="None/Sign/EncryptAndSign" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="92345-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="92345-105">Attributes and Elements</span></span>  

 <span data-ttu-id="92345-106">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="92345-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="92345-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="92345-107">Attributes</span></span>  
  
|<span data-ttu-id="92345-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="92345-108">Attribute</span></span>|<span data-ttu-id="92345-109">Описание</span><span class="sxs-lookup"><span data-stu-id="92345-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="92345-110">mode</span><span class="sxs-lookup"><span data-stu-id="92345-110">mode</span></span>|<span data-ttu-id="92345-111">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="92345-111">Optional.</span></span> <span data-ttu-id="92345-112">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="92345-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="92345-113">Ниже приведены допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="92345-113">Valid values are shown below.</span></span> <span data-ttu-id="92345-114">Значение по умолчанию — `Transport`.</span><span class="sxs-lookup"><span data-stu-id="92345-114">The default value is `Transport`.</span></span><br /><br /> <span data-ttu-id="92345-115">Это атрибут типа <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="92345-115">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="92345-116">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="92345-116">mode Attribute</span></span>  
  
|<span data-ttu-id="92345-117">Значение</span><span class="sxs-lookup"><span data-stu-id="92345-117">Value</span></span>|<span data-ttu-id="92345-118">Описание</span><span class="sxs-lookup"><span data-stu-id="92345-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="92345-119">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="92345-119">None</span></span>|<span data-ttu-id="92345-120">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="92345-120">Security is disabled.</span></span>|  
|<span data-ttu-id="92345-121">Транспорт</span><span class="sxs-lookup"><span data-stu-id="92345-121">Transport</span></span>|<span data-ttu-id="92345-122">Безопасность транспорта обеспечивается с помощью TLS через TCP или SPNego.</span><span class="sxs-lookup"><span data-stu-id="92345-122">Transport security is provided using TLS over TCP or SPNego.</span></span> <span data-ttu-id="92345-123">Может потребоваться настроить службу с использованием SSL-сертификатов.</span><span class="sxs-lookup"><span data-stu-id="92345-123">The service may need to be configured with SSL certificates.</span></span> <span data-ttu-id="92345-124">Этот режим позволяет контролировать уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="92345-124">It is possible to control the protection level with this mode.</span></span>|  
|<span data-ttu-id="92345-125">Сообщение</span><span class="sxs-lookup"><span data-stu-id="92345-125">Message</span></span>|<span data-ttu-id="92345-126">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="92345-126">Security is provided using SOAP message security.</span></span> <span data-ttu-id="92345-127">По умолчанию текст сообщений SOAP шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="92345-127">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="92345-128">Этот режим предоставляет множество функций, таких как сведения о доступности учетных данных службы для клиентов за пределами диапазона, об используемом наборе алгоритмов и об уровне защиты, применяемом к тексту сообщения.</span><span class="sxs-lookup"><span data-stu-id="92345-128">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body.</span></span> <span data-ttu-id="92345-129">Проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="92345-129">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="92345-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="92345-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="92345-131">Безопасность транспорта связана с безопасностью сообщения.</span><span class="sxs-lookup"><span data-stu-id="92345-131">Transport security is coupled with message security.</span></span> <span data-ttu-id="92345-132">Безопасность транспорта обеспечивается протоколом TLS через TCP, или SPNego, и гарантирует целостность, конфиденциальность и проверку подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="92345-132">Transport security is provided by TLS over TCP, or SPNego, and ensures integrity, confidentiality, and server authentication.</span></span> <span data-ttu-id="92345-133">Безопасность сообщений SOAP представляет проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="92345-133">SOAP message security provides client authentication.</span></span> <span data-ttu-id="92345-134">По умолчанию проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="92345-134">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="92345-135">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="92345-135">Child Elements</span></span>  
  
|<span data-ttu-id="92345-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="92345-136">Element</span></span>|<span data-ttu-id="92345-137">Описание</span><span class="sxs-lookup"><span data-stu-id="92345-137">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-nettcpbinding.md)|<span data-ttu-id="92345-138">Определяет параметры безопасности для данного транспорта.</span><span class="sxs-lookup"><span data-stu-id="92345-138">Defines the security settings for the transport.</span></span> <span data-ttu-id="92345-139">Это элемент типа <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="92345-139">This element is of type <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span></span>|  
|[\<message>](message-element-of-nettcpbinding.md)|<span data-ttu-id="92345-140">Определяет параметры безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="92345-140">Defines the security settings for the message.</span></span> <span data-ttu-id="92345-141">Это элемент типа <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span><span class="sxs-lookup"><span data-stu-id="92345-141">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="92345-142">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="92345-142">Parent Elements</span></span>  
  
|<span data-ttu-id="92345-143">Элемент</span><span class="sxs-lookup"><span data-stu-id="92345-143">Element</span></span>|<span data-ttu-id="92345-144">Описание</span><span class="sxs-lookup"><span data-stu-id="92345-144">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="92345-145">binding</span><span class="sxs-lookup"><span data-stu-id="92345-145">binding</span></span>|<span data-ttu-id="92345-146">Элемент Binding объекта [\<netTcpBinding>](nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="92345-146">The binding element of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92345-147">Remarks</span><span class="sxs-lookup"><span data-stu-id="92345-147">Remarks</span></span>  

 <span data-ttu-id="92345-148">Каждая из стандартных привязок предоставляет параметры для управления требованиями безопасности перемещения.</span><span class="sxs-lookup"><span data-stu-id="92345-148">Each of the standard bindings provides parameters for controlling the transfer security requirements.</span></span> <span data-ttu-id="92345-149">Эти параметры, как правило, включают режим безопасности, определяющий, используется ли безопасность уровня сообщения или уровня транспорта, а также выбор типа учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="92345-149">These parameters typically include the security mode that specified whether message-level or transport-level security is used and the choice of client credential type.</span></span> <span data-ttu-id="92345-150">На основании предоставленного выбора параметров создается стек каналов с соответствующей безопасностью.</span><span class="sxs-lookup"><span data-stu-id="92345-150">Based on the choice of options these parameters present, a channel stack is constructed with appropriate security.</span></span>  
  
 <span data-ttu-id="92345-151">Предоставляемые системой привязки, поставляемые Windows Communication Foundation (WCF), представляют собой набор, отвечающий требованиям наиболее распространенных сценариев.</span><span class="sxs-lookup"><span data-stu-id="92345-151">The system-provided bindings supplied by Windows Communication Foundation (WCF) are a set designed to meet some of the most common scenario requirements.</span></span> <span data-ttu-id="92345-152">Каждая из этих привязок позволяет задавать требования безопасности для некоторых конкретных целевых сценариев.</span><span class="sxs-lookup"><span data-stu-id="92345-152">Each of these bindings allows the specification of security requirements for some specific targeted scenarios.</span></span>  
  
 <span data-ttu-id="92345-153">Элемент конфигурации предоставляет спецификации безопасности для `netTcpBinding`.</span><span class="sxs-lookup"><span data-stu-id="92345-153">This configuration element provides the security specifications for `netTcpBinding`.</span></span> <span data-ttu-id="92345-154">Это безопасная, надежная и оптимизированная привязка, пригодная для обмена данными между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="92345-154">This is a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="92345-155">По умолчанию она создает стек связи среды выполнения, поддерживающий протокол TCP для доставки сообщений и безопасность Windows для безопасности сообщений и проверки подлинности, WS-ReliableMessaging для надежности, а также кодирование двоичных сообщений.</span><span class="sxs-lookup"><span data-stu-id="92345-155">By default it generates a runtime communication stack supporting TCP for message delivery and Windows Security for message security and authentication, WS-ReliableMessaging for reliability, and binary message encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92345-156">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="92345-156">See also</span></span>

- <xref:System.ServiceModel.NetTcpSecurity>
- <xref:System.ServiceModel.NetTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="92345-157">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="92345-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="92345-158">Привязки</span><span class="sxs-lookup"><span data-stu-id="92345-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="92345-159">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="92345-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="92345-160">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="92345-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
