---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 50fc7194823fb0c5c426fb54ffd50b17c3714ed9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251759"
---
# \<trustedIssuers>
<span data-ttu-id="3d6f8-101">Настраивает список сертификатов доверенных издателей, используемых в реестре имен поставщиков на основе конфигурации ( <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> ).</span><span class="sxs-lookup"><span data-stu-id="3d6f8-101">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerNameRegistry>**](issuernameregistry.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trustedIssuers>**  
  
## <a name="syntax"></a><span data-ttu-id="3d6f8-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d6f8-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry>  
          <trustedIssuers>  
            <add thumbprint=xs:string name=xs:string>  
            <clear>  
            <remove thumbprint=xs:string>  
          </trustedIssuers>  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d6f8-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3d6f8-103">Attributes and Elements</span></span>  
 <span data-ttu-id="3d6f8-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d6f8-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3d6f8-105">Attributes</span></span>  
 <span data-ttu-id="3d6f8-106">Нет</span><span class="sxs-lookup"><span data-stu-id="3d6f8-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3d6f8-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3d6f8-107">Child Elements</span></span>  
  
|<span data-ttu-id="3d6f8-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="3d6f8-108">Element</span></span>|<span data-ttu-id="3d6f8-109">Описание</span><span class="sxs-lookup"><span data-stu-id="3d6f8-109">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="3d6f8-110">Добавляет сертификат в коллекцию доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-110">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="3d6f8-111">Сертификат указывается с помощью `thumbprint` атрибута.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-111">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="3d6f8-112">Этот атрибут является обязательным и должен содержать форму отпечатка сертификата в кодировке ASN. 1.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-112">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="3d6f8-113">`name`Атрибут является необязательным и может использоваться для указания понятного имени сертификата.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-113">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="3d6f8-114">Удаляет все сертификаты из коллекции доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-114">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="3d6f8-115">Удаляет сертификат из коллекции доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-115">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="3d6f8-116">Сертификат указывается с помощью `thumbprint` атрибута.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-116">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="3d6f8-117">Атрибут обязателен.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-117">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3d6f8-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3d6f8-118">Parent Elements</span></span>  
  
|<span data-ttu-id="3d6f8-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="3d6f8-119">Element</span></span>|<span data-ttu-id="3d6f8-120">Описание</span><span class="sxs-lookup"><span data-stu-id="3d6f8-120">Description</span></span>|  
|-------------|-----------------|  
|[\<issuerNameRegistry>](issuernameregistry.md)|<span data-ttu-id="3d6f8-121">Настраивает реестр имен издателя.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-121">Configures the issuer name registry.</span></span> <span data-ttu-id="3d6f8-122">**Важно.**  `type`Атрибут `<issuerNameRegistry>` элемента должен ссылаться на <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класс, `<trustedIssuers>` чтобы элемент был допустимым.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-122">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d6f8-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="3d6f8-123">Remarks</span></span>  
 <span data-ttu-id="3d6f8-124">Windows Identity Foundation (WIF) предоставляет единую реализацию класса из <xref:System.IdentityModel.Tokens.IssuerNameRegistry> Box, <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-124">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="3d6f8-125">В реестре имени издателя конфигурации хранится список доверенных издателей, которые загружаются из конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-125">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="3d6f8-126">Список всех имен издателей связывается с сертификатом X. 509, который необходим для проверки подписи маркеров, созданных издателем.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-126">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="3d6f8-127">Список сертификатов доверенных издателей указывается в `<trustedIssuers>` элементе.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-127">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="3d6f8-128">Каждый элемент в списке связывает назначенное имя издателя с сертификатом X. 509, который необходим для проверки подписи маркеров, созданных этим издателем.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-128">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="3d6f8-129">Доверенные сертификаты указываются с помощью формы отпечатка сертификата в кодировке ASN. 1 и добавляются в коллекцию с помощью `<add>` элемента.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-129">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="3d6f8-130">Можно удалить или удалить издателей (сертификаты) из списка с помощью `<clear>` `<remove>` элементов и.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-130">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="3d6f8-131">`type`Атрибут `<issuerNameRegistry>` элемента должен ссылаться на <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класс, `<trustedIssuers>` чтобы элемент был допустимым.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-131">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d6f8-132">Пример</span><span class="sxs-lookup"><span data-stu-id="3d6f8-132">Example</span></span>  
 <span data-ttu-id="3d6f8-133">В следующем коде XML показано, как указать реестр имен поставщиков на основе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-133">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3d6f8-134">См. также</span><span class="sxs-lookup"><span data-stu-id="3d6f8-134">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
