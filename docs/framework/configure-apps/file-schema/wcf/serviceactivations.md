---
title: <serviceActivations>
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: 64ae0bfd90ae941fc78515c7936c998201c87485
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855132"
---
# \<serviceActivations>

<span data-ttu-id="d422b-101">Элемент конфигурации, позволяющий добавлять параметры, определяющие параметры активации виртуальной службы, сопоставленные с типами служб Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="d422b-101">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="d422b-102">Это позволяет активировать службы, расположенные в WAS/IIS, без SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="d422b-102">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceActivations>**  

## <a name="syntax"></a><span data-ttu-id="d422b-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d422b-103">Syntax</span></span>

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d422b-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d422b-104">Attributes and Elements</span></span>

<span data-ttu-id="d422b-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d422b-105">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d422b-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d422b-106">Attributes</span></span>

<span data-ttu-id="d422b-107">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d422b-107">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d422b-108">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d422b-108">Child Elements</span></span>

|<span data-ttu-id="d422b-109">Элемент</span><span class="sxs-lookup"><span data-stu-id="d422b-109">Element</span></span>|<span data-ttu-id="d422b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d422b-110">Description</span></span>|
|-------------|-----------------|
|[\<add>](add-of-serviceactivations.md)|<span data-ttu-id="d422b-111">Добавляет элемент конфигурации, который задает активацию приложения службы.</span><span class="sxs-lookup"><span data-stu-id="d422b-111">Adds a configuration element that specifies the activation of a service application.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d422b-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d422b-112">Parent Elements</span></span>

|<span data-ttu-id="d422b-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="d422b-113">Element</span></span>|<span data-ttu-id="d422b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d422b-114">Description</span></span>|
|-------------|-----------------|
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="d422b-115">Определяет, какой тип среда размещения служб создает для конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="d422b-115">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d422b-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="d422b-116">Remarks</span></span>

<span data-ttu-id="d422b-117">В следующем примере показано, как настроить параметры активации в файле web.config.</span><span class="sxs-lookup"><span data-stu-id="d422b-117">The following example shows how to configure activation settings within your web.config file.</span></span>

```xml
<configuration>
  <system.serviceModel>
    <serviceHostingEnvironment>
      <serviceActivations>
        <add service="GreetingService" />
      </serviceActivations>
    </serviceHostingEnvironment>
  </system.serviceModel>
</configuration>
```

<span data-ttu-id="d422b-118">Использование этой конфигурации позволяет активировать GreetingService без SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="d422b-118">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="d422b-119">Следует отметить, что `<serviceHostingEnvironment>` является конфигурацией на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="d422b-119">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="d422b-120">Необходимо разместить файл `web.config`, содержащий конфигурацию в корневом каталоге виртуального приложения.</span><span class="sxs-lookup"><span data-stu-id="d422b-120">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="d422b-121">Кроме того, `serviceHostingEnvironment` является machineToApplication наследуемым разделом.</span><span class="sxs-lookup"><span data-stu-id="d422b-121">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="d422b-122">Если зарегистрировать одну службу в корневом каталоге компьютера, каждая служба в приложении унаследует эту службу.</span><span class="sxs-lookup"><span data-stu-id="d422b-122">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="d422b-123">Активация на основе конфигурации поддерживает активацию как по протоколу HTTP, так и по протоколу, отличному от HTTP.</span><span class="sxs-lookup"><span data-stu-id="d422b-123">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="d422b-124">Для этого требуются расширения в Релативеаддресс, например. svc,. XOML или. xamlx.</span><span class="sxs-lookup"><span data-stu-id="d422b-124">It requires extensions in the relativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="d422b-125">Можно сопоставить пользовательские расширения с известными поставщиками buildProvider, что впоследствии позволит активировать службу через любое расширение.</span><span class="sxs-lookup"><span data-stu-id="d422b-125">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="d422b-126">При возникновении конфликта раздел `<serviceActivations>` переопределяет записи в SVC-файле.</span><span class="sxs-lookup"><span data-stu-id="d422b-126">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="d422b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="d422b-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
