---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 4c6affbc24a58424158e466fb732e9a3b3d6f1ed
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157022"
---
# \<securityTokenHandlerConfiguration>

<span data-ttu-id="bbc5e-101">Предоставляет конфигурацию для коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-101">Provides configuration for the collection of token handlers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**  
  
## <a name="syntax"></a><span data-ttu-id="bbc5e-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bbc5e-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration saveBootstrapContext=xs:boolean  
          maximumClockSkew=TimeSpan>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bbc5e-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bbc5e-103">Attributes and Elements</span></span>  

 <span data-ttu-id="bbc5e-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bbc5e-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bbc5e-105">Attributes</span></span>  
  
|<span data-ttu-id="bbc5e-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bbc5e-106">Attribute</span></span>|<span data-ttu-id="bbc5e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bbc5e-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bbc5e-108">савебутстрапконтекст</span><span class="sxs-lookup"><span data-stu-id="bbc5e-108">saveBootstrapContext</span></span>|<span data-ttu-id="bbc5e-109">Указывает, следует ли включать в маркер сеанса начальные токены.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-109">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="bbc5e-110">Значение также может быть задано в коллекции обработчиков маркеров путем установки `saveBootstrapContext` атрибута для [\<identityConfiguration>](identityconfiguration.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-110">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="bbc5e-111">Значение, заданное в коллекции обработчиков маркеров, переопределяет значение, заданное для службы.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-111">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="bbc5e-112">максимумклоккскев</span><span class="sxs-lookup"><span data-stu-id="bbc5e-112">maximumClockSkew</span></span>|<span data-ttu-id="bbc5e-113">Значение типа <xref:System.TimeSpan> , указывающее максимально допустимую отклонение в часах.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-113">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="bbc5e-114">Управляет максимально разрешенным отклонением по часам при выполнении операций с учетом времени, таких как проверка срока действия сеанса входа.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-114">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="bbc5e-115">Значение по умолчанию — 5 минут, "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="bbc5e-115">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="bbc5e-116">Дополнительные сведения об указании <xref:System.TimeSpan> значений см. в разделе [значения TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="bbc5e-116">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="bbc5e-117">Максимальная разница в часах может также быть задана на уровне службы путем установки `maximumClockSkew` атрибута для [\<identityConfiguration>](identityconfiguration.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-117">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="bbc5e-118">Значение, заданное в коллекции обработчиков маркеров, переопределяет значение, заданное для службы.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-118">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bbc5e-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bbc5e-119">Child Elements</span></span>  
  
|<span data-ttu-id="bbc5e-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="bbc5e-120">Element</span></span>|<span data-ttu-id="bbc5e-121">Описание</span><span class="sxs-lookup"><span data-stu-id="bbc5e-121">Description</span></span>|  
|-------------|-----------------|  
|[\<audienceUris>](audienceuris.md)|<span data-ttu-id="bbc5e-122">Указывает набор универсальных кодов ресурса (URI), которые являются допустимыми идентификаторами этой проверяющей стороны.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-122">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="bbc5e-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-123">Optional.</span></span>|  
|[\<caches>](caches.md)|<span data-ttu-id="bbc5e-124">Регистрирует кэши, используемые для маркеров сеансов и определения воспроизведения маркеров.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-124">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="bbc5e-125">Может указываться на уровне службы или в коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-125">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="bbc5e-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-126">Optional.</span></span>|  
|[\<certificateValidation>](certificatevalidation.md)|<span data-ttu-id="bbc5e-127">Управляет параметрами, которые обработчики маркеров используют для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-127">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="bbc5e-128">Может указываться на уровне службы или в коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-128">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="bbc5e-129">Эти параметры переопределяются, если для определенного обработчика настроен собственный проверяющий элемент управления.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-129">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="bbc5e-130">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-130">Optional.</span></span>|  
|[\<issuerNameRegistry>](issuernameregistry.md)|<span data-ttu-id="bbc5e-131">Настраивает реестр имен издателя, используемый обработчиками в коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-131">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="bbc5e-132">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-132">Optional.</span></span>|  
|[\<issuerTokenResolver>](issuertokenresolver.md)|<span data-ttu-id="bbc5e-133">Регистрирует сопоставитель маркеров издателя, используемый обработчиками в коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-133">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="bbc5e-134">Сопоставитель токенов издателя используется для разрешения маркера подписывания входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-134">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="bbc5e-135">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-135">Optional.</span></span>|  
|[\<serviceTokenResolver>](servicetokenresolver.md)|<span data-ttu-id="bbc5e-136">Регистрирует сопоставитель маркеров службы, используемый обработчиками в коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-136">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="bbc5e-137">Сопоставитель токенов службы используется для разрешения маркера шифрования входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-137">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="bbc5e-138">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-138">Optional.</span></span>|  
|[\<tokenReplayDetection>](tokenreplaydetection.md)|<span data-ttu-id="bbc5e-139">Включает обнаружение воспроизведения маркеров и задает срок действия токенов.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-139">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="bbc5e-140">Может указываться на уровне службы или в коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-140">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="bbc5e-141">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-141">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bbc5e-142">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bbc5e-142">Parent Elements</span></span>  
  
|<span data-ttu-id="bbc5e-143">Элемент</span><span class="sxs-lookup"><span data-stu-id="bbc5e-143">Element</span></span>|<span data-ttu-id="bbc5e-144">Описание</span><span class="sxs-lookup"><span data-stu-id="bbc5e-144">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="bbc5e-145">Указывает коллекцию обработчиков маркеров безопасности, зарегистрированных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-145">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbc5e-146">Remarks</span><span class="sxs-lookup"><span data-stu-id="bbc5e-146">Remarks</span></span>  

 <span data-ttu-id="bbc5e-147">В этом разделе приводятся значения свойств для <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> объекта.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-147">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="bbc5e-148">Параметры, настроенные в этом разделе, переопределяют настройки, настроенные в службе.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-148">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="bbc5e-149">Некоторые из этих параметров, в свою очередь, могут быть переопределены параметрами, заданными при добавлении обработчика в коллекцию обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="bbc5e-149">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbc5e-150">Пример</span><span class="sxs-lookup"><span data-stu-id="bbc5e-150">Example</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>
      <securityTokenHandlerConfiguration>  
  
        <audienceUris>  
          <clear/>  
          <add value="http://www.example.com/myapp/" />  
        </audienceUris>  
  
        <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel">  
          <trustedIssuers>  
            <add thumbprint="97249e1a … 4c9158de" name="contoso.com" />  
          </trustedIssuers>  
        </issuerNameRegistry>  
  
        <issuerTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
        <serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```
