---
title: <transport> из <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: 996b3655b0698595256c9a7197f705d46e6e9fcf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169821"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="5c8d2-102">\<transport> из \<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="5c8d2-102">\<transport> of \<netHttpBinding></span></span>

<span data-ttu-id="5c8d2-103">Определяет свойства, которые управляют параметрами проверки подлинности для транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="5c8d2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c8d2-104">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c8d2-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5c8d2-105">Attributes and Elements</span></span>  

 <span data-ttu-id="5c8d2-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c8d2-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5c8d2-107">Attributes</span></span>  
  
|<span data-ttu-id="5c8d2-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5c8d2-108">Attribute</span></span>|<span data-ttu-id="5c8d2-109">Описание</span><span class="sxs-lookup"><span data-stu-id="5c8d2-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5c8d2-110">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="5c8d2-110">clientCredentialType</span></span>|<span data-ttu-id="5c8d2-111">— Указывает тип учетных данных, используемых при проверке подлинности клиента с помощью проверки подлинности HTTP.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-111">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="5c8d2-112">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-112">The default is `None`.</span></span> <span data-ttu-id="5c8d2-113">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-113">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="5c8d2-114">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="5c8d2-114">proxyCredentialType</span></span>|<span data-ttu-id="5c8d2-115">— Указывает тип учетных данных, используемых при выполнении проверки подлинности клиента в домене с использованием прокси-сервера через HTTP.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-115">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="5c8d2-116">Этот атрибут применим, только если атрибут `mode` родительского элемента `security` имеет значение `Transport` или `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-116">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="5c8d2-117">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-117">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="5c8d2-118">realm</span><span class="sxs-lookup"><span data-stu-id="5c8d2-118">realm</span></span>|<span data-ttu-id="5c8d2-119">Строка, указывающая область, используемую схемой проверки подлинности HTTP для обычной проверки подлинности или дайджест-проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-119">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="5c8d2-120">Значением по умолчанию является пустая строка.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-120">The default is an empty string.</span></span>|  
|<span data-ttu-id="5c8d2-121">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="5c8d2-121">policyEnforcement</span></span>|<span data-ttu-id="5c8d2-122">Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-122">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="5c8d2-123">1. Never — политика никогда не применяется (Расширенная защита отключена).</span><span class="sxs-lookup"><span data-stu-id="5c8d2-123">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="5c8d2-124">2. WhenSupported — политика применяется, только если клиент поддерживает расширенную защиту.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-124">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="5c8d2-125">3. всегда — политика всегда применяется принудительно.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-125">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="5c8d2-126">Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-126">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="5c8d2-127">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="5c8d2-127">protectionScenario</span></span>|<span data-ttu-id="5c8d2-128">Это перечисление указывает сценарий защиты, регламентированный политикой.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-128">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="5c8d2-129">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="5c8d2-129">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="5c8d2-130">Значение</span><span class="sxs-lookup"><span data-stu-id="5c8d2-130">Value</span></span>|<span data-ttu-id="5c8d2-131">Описание</span><span class="sxs-lookup"><span data-stu-id="5c8d2-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5c8d2-132">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="5c8d2-132">None</span></span>|<span data-ttu-id="5c8d2-133">Во время передачи сообщения не защищены.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-133">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="5c8d2-134">Basic</span><span class="sxs-lookup"><span data-stu-id="5c8d2-134">Basic</span></span>|<span data-ttu-id="5c8d2-135">Задает обычную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-135">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="5c8d2-136">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="5c8d2-136">Digest</span></span>|<span data-ttu-id="5c8d2-137">Задает дайджест-проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-137">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="5c8d2-138">Ntlm</span><span class="sxs-lookup"><span data-stu-id="5c8d2-138">Ntlm</span></span>|<span data-ttu-id="5c8d2-139">Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-139">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="5c8d2-140">Windows</span><span class="sxs-lookup"><span data-stu-id="5c8d2-140">Windows</span></span>|<span data-ttu-id="5c8d2-141">Задает встроенную проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-141">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="5c8d2-142">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="5c8d2-142">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="5c8d2-143">Значение</span><span class="sxs-lookup"><span data-stu-id="5c8d2-143">Value</span></span>|<span data-ttu-id="5c8d2-144">Описание</span><span class="sxs-lookup"><span data-stu-id="5c8d2-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5c8d2-145">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="5c8d2-145">None</span></span>|<span data-ttu-id="5c8d2-146">— Сообщения не защищаются во время перемещения.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-146">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="5c8d2-147">Basic</span><span class="sxs-lookup"><span data-stu-id="5c8d2-147">Basic</span></span>|<span data-ttu-id="5c8d2-148">Задает обычную проверку подлинности, как определено документом RFC 2617, который посвящен проверке подлинности HTTP, обычной проверке и дайджест-проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-148">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="5c8d2-149">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="5c8d2-149">Digest</span></span>|<span data-ttu-id="5c8d2-150">Задает дайджест-проверку подлинности, как определено документом RFC 2617, который посвящен проверке подлинности HTTP, обычной проверке и дайджест-проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-150">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="5c8d2-151">Ntlm</span><span class="sxs-lookup"><span data-stu-id="5c8d2-151">Ntlm</span></span>|<span data-ttu-id="5c8d2-152">Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-152">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="5c8d2-153">Windows</span><span class="sxs-lookup"><span data-stu-id="5c8d2-153">Windows</span></span>|<span data-ttu-id="5c8d2-154">Задает встроенную проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-154">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="5c8d2-155">Сертификат</span><span class="sxs-lookup"><span data-stu-id="5c8d2-155">Certificate</span></span>|<span data-ttu-id="5c8d2-156">Выполняет проверку подлинности клиента с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-156">Performs client authentication using a certificate.</span></span> <span data-ttu-id="5c8d2-157">Такая возможность действует, только если атрибут `Mode` родительского элемента `security` имеет значение Transport, и не действует, если этот атрибут имеет значение TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-157">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c8d2-158">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5c8d2-158">Child Elements</span></span>  

 <span data-ttu-id="5c8d2-159">Нет</span><span class="sxs-lookup"><span data-stu-id="5c8d2-159">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5c8d2-160">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5c8d2-160">Parent Elements</span></span>  
  
|<span data-ttu-id="5c8d2-161">Элемент</span><span class="sxs-lookup"><span data-stu-id="5c8d2-161">Element</span></span>|<span data-ttu-id="5c8d2-162">Описание</span><span class="sxs-lookup"><span data-stu-id="5c8d2-162">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nethttpbinding.md)|<span data-ttu-id="5c8d2-163">Определяет возможности безопасности для [\<netHttpBinding>](nethttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="5c8d2-163">Defines the security capabilities for the [\<netHttpBinding>](nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5c8d2-164">Пример</span><span class="sxs-lookup"><span data-stu-id="5c8d2-164">Example</span></span>  

 <span data-ttu-id="5c8d2-165">В следующем примере демонстрируется использование безопасности транспорта SSL с использованием основной привязки.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-165">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="5c8d2-166">По умолчанию основная привязка поддерживает взаимодействие по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="5c8d2-166">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
      <!-- Configure basicHttpBinding with Transport security -->
      <!-- mode and clientCredentialType set to None. -->
      <binding name="Binding1">
        <security mode="Transport">
          <transport clientCredentialType="None"
                     proxyCredentialType="None">
            <extendedProtectionPolicy policyEnforcement="WhenSupported"
                                      protectionScenario="TransportSelected">
              <customServiceNames>
              </customServiceNames>
            </extendedProtectionPolicy>
          </transport>
        </security>
      </binding>
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="5c8d2-167">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5c8d2-167">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="5c8d2-168">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="5c8d2-168">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5c8d2-169">Привязки</span><span class="sxs-lookup"><span data-stu-id="5c8d2-169">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5c8d2-170">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="5c8d2-170">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5c8d2-171">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="5c8d2-171">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
