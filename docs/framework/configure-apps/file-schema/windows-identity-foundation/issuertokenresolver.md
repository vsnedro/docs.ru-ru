---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 946ae8601e1e4563becd0b346b6c792724405a45
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165043"
---
# \<issuerTokenResolver>

<span data-ttu-id="237c2-101">Регистрирует сопоставитель маркеров издателя, используемый обработчиками в коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="237c2-101">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="237c2-102">Сопоставитель токенов издателя используется для разрешения маркера подписывания входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="237c2-102">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="237c2-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="237c2-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerTokenResolver type=xs:string>  
        </issuerTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="237c2-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="237c2-104">Attributes and Elements</span></span>  

 <span data-ttu-id="237c2-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="237c2-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="237c2-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="237c2-106">Attributes</span></span>  
  
|<span data-ttu-id="237c2-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="237c2-107">Attribute</span></span>|<span data-ttu-id="237c2-108">Описание</span><span class="sxs-lookup"><span data-stu-id="237c2-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="237c2-109">type</span><span class="sxs-lookup"><span data-stu-id="237c2-109">type</span></span>|<span data-ttu-id="237c2-110">Указывает тип сопоставителя маркеров издателя.</span><span class="sxs-lookup"><span data-stu-id="237c2-110">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="237c2-111">Должен быть либо <xref:System.IdentityModel.Tokens.IssuerTokenResolver> классом, либо типом, производным от <xref:System.IdentityModel.Tokens.IssuerTokenResolver> класса.</span><span class="sxs-lookup"><span data-stu-id="237c2-111">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="237c2-112">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="237c2-112">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="237c2-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="237c2-113">Child Elements</span></span>  

 <span data-ttu-id="237c2-114">Нет</span><span class="sxs-lookup"><span data-stu-id="237c2-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="237c2-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="237c2-115">Parent Elements</span></span>  
  
|<span data-ttu-id="237c2-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="237c2-116">Element</span></span>|<span data-ttu-id="237c2-117">Описание</span><span class="sxs-lookup"><span data-stu-id="237c2-117">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="237c2-118">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="237c2-118">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="237c2-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="237c2-119">Remarks</span></span>  

 <span data-ttu-id="237c2-120">Сопоставитель токенов издателя используется для разрешения маркера подписывания входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="237c2-120">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="237c2-121">Он используется для получения криптографического материала, используемого для проверки подписи.</span><span class="sxs-lookup"><span data-stu-id="237c2-121">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="237c2-122">Необходимо указать `type` атрибут.</span><span class="sxs-lookup"><span data-stu-id="237c2-122">You must specify the `type` attribute.</span></span> <span data-ttu-id="237c2-123">Указанный тип может быть либо либо <xref:System.IdentityModel.Tokens.IssuerTokenResolver> пользовательским типом, производным от <xref:System.IdentityModel.Tokens.IssuerTokenResolver> класса.</span><span class="sxs-lookup"><span data-stu-id="237c2-123">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="237c2-124">Некоторые обработчики маркеров позволяют задавать параметры сопоставителя маркеров издателя в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="237c2-124">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="237c2-125">Параметры отдельных обработчиков маркеров переопределяют те, которые указаны в коллекции обработчика маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="237c2-125">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="237c2-126">Указание `<issuerTokenResolver>` элемента в качестве дочернего элемента [\<identityConfiguration>](identityconfiguration.md) элемента является устаревшим, но по-прежнему поддерживается для обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="237c2-126">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="237c2-127">Параметры `<securityTokenHandlerConfiguration>` элемента переопределяют их для `<identityConfiguration>` элемента.</span><span class="sxs-lookup"><span data-stu-id="237c2-127">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="237c2-128">Пример</span><span class="sxs-lookup"><span data-stu-id="237c2-128">Example</span></span>  

 <span data-ttu-id="237c2-129">В следующем коде XML показана конфигурация для сопоставителя маркеров издателя, основанного на пользовательском классе, производном от <xref:System.IdentityModel.Tokens.IssuerTokenResolver> .</span><span class="sxs-lookup"><span data-stu-id="237c2-129">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="237c2-130">Сопоставитель токенов поддерживает словарь пар ключей аудитории, которые инициализируются из настраиваемого элемента конфигурации ( `<AddAudienceKeyPair>` ), определенного для класса.</span><span class="sxs-lookup"><span data-stu-id="237c2-130">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="237c2-131">Класс переопределяет <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> метод для обработки этого элемента.</span><span class="sxs-lookup"><span data-stu-id="237c2-131">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="237c2-132">Переопределение показано в следующем примере. Однако методы, которые он вызывает, не отображаются для краткости.</span><span class="sxs-lookup"><span data-stu-id="237c2-132">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="237c2-133">Полный пример см `CustomToken` . в примере.</span><span class="sxs-lookup"><span data-stu-id="237c2-133">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="237c2-134">Пример</span><span class="sxs-lookup"><span data-stu-id="237c2-134">Example</span></span>
  
```csharp
public override void LoadCustomConfiguration(System.Xml.XmlNodeList nodelist)  
{  
    foreach (XmlNode node in nodelist)  
    {  
        XmlDictionaryReader rdr = XmlDictionaryReader.CreateDictionaryReader(new XmlTextReader(new StringReader(node.OuterXml)));  
        rdr.MoveToContent();  
  
        string symmetricKey = rdr.GetAttribute("symmetricKey");  
        string audience = rdr.GetAttribute("audience");  
  
        this.AddAudienceKeyPair(audience, symmetricKey);  
    }  
}  
```
  
## <a name="see-also"></a><span data-ttu-id="237c2-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="237c2-135">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
