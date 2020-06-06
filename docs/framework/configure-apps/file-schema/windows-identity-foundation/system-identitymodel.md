---
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: a54f5ce86aee1a5e831c0b10aa1471d4a82f40a5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251794"
---
# \<system.identityModel>
<span data-ttu-id="114b3-102">Предоставляет конфигурацию для включения параметров Windows Identity Foundation (WIF) в приложениях.</span><span class="sxs-lookup"><span data-stu-id="114b3-102">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.identityModel>**  
  
## <a name="syntax"></a><span data-ttu-id="114b3-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="114b3-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="114b3-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="114b3-104">Attributes and Elements</span></span>  
 <span data-ttu-id="114b3-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="114b3-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="114b3-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="114b3-106">Attributes</span></span>  
 <span data-ttu-id="114b3-107">Нет</span><span class="sxs-lookup"><span data-stu-id="114b3-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="114b3-108">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="114b3-108">Child Elements</span></span>  
  
|<span data-ttu-id="114b3-109">Элемент</span><span class="sxs-lookup"><span data-stu-id="114b3-109">Element</span></span>|<span data-ttu-id="114b3-110">Описание</span><span class="sxs-lookup"><span data-stu-id="114b3-110">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="114b3-111">Задает параметры удостоверений уровня службы.</span><span class="sxs-lookup"><span data-stu-id="114b3-111">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="114b3-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="114b3-112">Parent Elements</span></span>  
  
|<span data-ttu-id="114b3-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="114b3-113">Element</span></span>|<span data-ttu-id="114b3-114">Описание</span><span class="sxs-lookup"><span data-stu-id="114b3-114">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="114b3-115">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="114b3-115">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="114b3-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="114b3-116">Remarks</span></span>  
 <span data-ttu-id="114b3-117">Добавьте `<system.identityModel>` раздел в файл конфигурации, чтобы настроить службу или приложение для использования Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="114b3-117">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="114b3-118">`<system.identityModel>`Элемент представлен <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> классом.</span><span class="sxs-lookup"><span data-stu-id="114b3-118">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="114b3-119">Пример</span><span class="sxs-lookup"><span data-stu-id="114b3-119">Example</span></span>  
 <span data-ttu-id="114b3-120">В следующем примере показано, как добавить `<system.identityModel>` раздел в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="114b3-120">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="114b3-121">Сначала необходимо добавить раздел конфигурации и объявление пространства имен в `<configSections>` элемент.</span><span class="sxs-lookup"><span data-stu-id="114b3-121">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="114b3-122">Затем можно добавить `<system.IdentityModel>` элемент в файл конфигурации, чтобы указать одну или несколько конфигураций удостоверений.</span><span class="sxs-lookup"><span data-stu-id="114b3-122">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
    <!--WIF 4.5 sections -->  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
  </configSections>  
  
  ...  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost/WebApplication1/" />  
      </audienceUris>  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089">  
        <trustedIssuers>  
          <add thumbprint="313D3B … 9106A9EC" name="SelfSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
      <certificateValidation certificateValidationMode="None"/>  
    </identityConfiguration>  
  </system.identityModel>  
  
  ...  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="114b3-123">См. также</span><span class="sxs-lookup"><span data-stu-id="114b3-123">See also</span></span>

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
