---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: e3e65820fa4dc341371d4f67689a288cd3f63951
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152571"
---
# \<securityTokenHandlerConfiguration>
<span data-ttu-id="6c346-101">Предоставляет конфигурацию для коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="6c346-101">Provides configuration for the collection of token handlers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**  
  
## <a name="syntax"></a><span data-ttu-id="6c346-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c346-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c346-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6c346-103">Attributes and Elements</span></span>  
 <span data-ttu-id="6c346-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6c346-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c346-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6c346-105">Attributes</span></span>  
  
|<span data-ttu-id="6c346-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6c346-106">Attribute</span></span>|<span data-ttu-id="6c346-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="6c346-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6c346-108">савебутстрапконтекст</span><span class="sxs-lookup"><span data-stu-id="6c346-108">saveBootstrapContext</span></span>|<span data-ttu-id="6c346-109">Указывает, следует ли включать в маркер сеанса начальные токены.</span><span class="sxs-lookup"><span data-stu-id="6c346-109">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="6c346-110">Значение также может быть задано в коллекции обработчиков маркеров путем установки `saveBootstrapContext` атрибута для [\<identityConfiguration>](identityconfiguration.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="6c346-110">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="6c346-111">Значение, заданное в коллекции обработчиков маркеров, переопределяет значение, заданное для службы.</span><span class="sxs-lookup"><span data-stu-id="6c346-111">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="6c346-112">максимумклоккскев</span><span class="sxs-lookup"><span data-stu-id="6c346-112">maximumClockSkew</span></span>|<span data-ttu-id="6c346-113">Значение типа <xref:System.TimeSpan> , указывающее максимально допустимую отклонение в часах.</span><span class="sxs-lookup"><span data-stu-id="6c346-113">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="6c346-114">Управляет максимально разрешенным отклонением по часам при выполнении операций с учетом времени, таких как проверка срока действия сеанса входа.</span><span class="sxs-lookup"><span data-stu-id="6c346-114">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="6c346-115">Значение по умолчанию — 5 минут, "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="6c346-115">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="6c346-116">Дополнительные сведения об указании <xref:System.TimeSpan> значений см. в разделе [значения TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="6c346-116">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="6c346-117">Максимальная разница в часах может также быть задана на уровне службы путем установки `maximumClockSkew` атрибута для [\<identityConfiguration>](identityconfiguration.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="6c346-117">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="6c346-118">Значение, заданное в коллекции обработчиков маркеров, переопределяет значение, заданное для службы.</span><span class="sxs-lookup"><span data-stu-id="6c346-118">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c346-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6c346-119">Child Elements</span></span>  
  
|<span data-ttu-id="6c346-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="6c346-120">Element</span></span>|<span data-ttu-id="6c346-121">Описание</span><span class="sxs-lookup"><span data-stu-id="6c346-121">Description</span></span>|  
|-------------|-----------------|  
|[\<audienceUris>](audienceuris.md)|<span data-ttu-id="6c346-122">Указывает набор универсальных кодов ресурса (URI), которые являются допустимыми идентификаторами этой проверяющей стороны.</span><span class="sxs-lookup"><span data-stu-id="6c346-122">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="6c346-123">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="6c346-123">Optional.</span></span>|  
|[\<caches>](caches.md)|<span data-ttu-id="6c346-124">Регистрирует кэши, используемые для маркеров сеансов и определения воспроизведения маркеров.</span><span class="sxs-lookup"><span data-stu-id="6c346-124">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="6c346-125">Может указываться на уровне службы или в коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="6c346-125">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="6c346-126">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="6c346-126">Optional.</span></span>|  
|[\<certificateValidation>](certificatevalidation.md)|<span data-ttu-id="6c346-127">Управляет параметрами, которые обработчики маркеров используют для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="6c346-127">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="6c346-128">Может указываться на уровне службы или в коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="6c346-128">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="6c346-129">Эти параметры переопределяются, если для определенного обработчика настроен собственный проверяющий элемент управления.</span><span class="sxs-lookup"><span data-stu-id="6c346-129">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="6c346-130">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="6c346-130">Optional.</span></span>|  
|[\<issuerNameRegistry>](issuernameregistry.md)|<span data-ttu-id="6c346-131">Настраивает реестр имен издателя, используемый обработчиками в коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="6c346-131">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="6c346-132">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="6c346-132">Optional.</span></span>|  
|[\<issuerTokenResolver>](issuertokenresolver.md)|<span data-ttu-id="6c346-133">Регистрирует сопоставитель маркеров издателя, используемый обработчиками в коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="6c346-133">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="6c346-134">Сопоставитель токенов издателя используется для разрешения маркера подписывания входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="6c346-134">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="6c346-135">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="6c346-135">Optional.</span></span>|  
|[\<serviceTokenResolver>](servicetokenresolver.md)|<span data-ttu-id="6c346-136">Регистрирует сопоставитель маркеров службы, используемый обработчиками в коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="6c346-136">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="6c346-137">Сопоставитель токенов службы используется для разрешения маркера шифрования входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="6c346-137">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="6c346-138">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="6c346-138">Optional.</span></span>|  
|[\<tokenReplayDetection>](tokenreplaydetection.md)|<span data-ttu-id="6c346-139">Включает обнаружение воспроизведения маркеров и задает срок действия токенов.</span><span class="sxs-lookup"><span data-stu-id="6c346-139">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="6c346-140">Может указываться на уровне службы или в коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="6c346-140">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="6c346-141">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="6c346-141">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6c346-142">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6c346-142">Parent Elements</span></span>  
  
|<span data-ttu-id="6c346-143">Элемент</span><span class="sxs-lookup"><span data-stu-id="6c346-143">Element</span></span>|<span data-ttu-id="6c346-144">Описание</span><span class="sxs-lookup"><span data-stu-id="6c346-144">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="6c346-145">Указывает коллекцию обработчиков маркеров безопасности, зарегистрированных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="6c346-145">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c346-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="6c346-146">Remarks</span></span>  
 <span data-ttu-id="6c346-147">В этом разделе приводятся значения свойств для <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> объекта.</span><span class="sxs-lookup"><span data-stu-id="6c346-147">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="6c346-148">Параметры, настроенные в этом разделе, переопределяют настройки, настроенные в службе.</span><span class="sxs-lookup"><span data-stu-id="6c346-148">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="6c346-149">Некоторые из этих параметров, в свою очередь, могут быть переопределены параметрами, заданными при добавлении обработчика в коллекцию обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="6c346-149">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c346-150">Пример</span><span class="sxs-lookup"><span data-stu-id="6c346-150">Example</span></span>  
  
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
