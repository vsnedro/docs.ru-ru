---
title: <add> из <serviceActivations>
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: a0f68717f765482f53e675458fae63d1a374d6fb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850326"
---
# <a name="add-of-serviceactivations"></a><span data-ttu-id="bc24d-102">\<add> из \<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="bc24d-102">\<add> of \<serviceActivations></span></span>

<span data-ttu-id="bc24d-103">Элемент конфигурации, позволяющий определить параметры активации виртуальной службы, которые сопоставляются с типами служб Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="bc24d-103">A configuration element that allows you to define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="bc24d-104">Это позволяет активировать службы, расположенные в WAS/IIS, без SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="bc24d-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceActivations>**](serviceactivations.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  

## <a name="syntax"></a><span data-ttu-id="bc24d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc24d-105">Syntax</span></span>

```xml
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bc24d-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bc24d-106">Attributes and Elements</span></span>

<span data-ttu-id="bc24d-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bc24d-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="bc24d-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bc24d-108">Attributes</span></span>

|<span data-ttu-id="bc24d-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bc24d-109">Attribute</span></span>|<span data-ttu-id="bc24d-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="bc24d-110">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="bc24d-111">фабрика</span><span class="sxs-lookup"><span data-stu-id="bc24d-111">factory</span></span>|<span data-ttu-id="bc24d-112">Строка, задающая имя типа CLR фабрики, которая формирует элемент активации службы.</span><span class="sxs-lookup"><span data-stu-id="bc24d-112">A string that specifies the CLR type name of the factory that generates a service activation element.</span></span>|
|<span data-ttu-id="bc24d-113">служба</span><span class="sxs-lookup"><span data-stu-id="bc24d-113">service</span></span>|<span data-ttu-id="bc24d-114">ServiceType, реализующий службу (либо полное, либо короткое имя типа) (когда оно размещено в папке App_Code).</span><span class="sxs-lookup"><span data-stu-id="bc24d-114">The ServiceType that implements the service (either the full qualified Typename or the short Typename (when it is placed in the App_Code folder).</span></span>|
|<span data-ttu-id="bc24d-115">relativeAddress</span><span class="sxs-lookup"><span data-stu-id="bc24d-115">relativeAddress</span></span>|<span data-ttu-id="bc24d-116">Относительный адрес в текущем приложении IIS (например, «Service.svc»).</span><span class="sxs-lookup"><span data-stu-id="bc24d-116">The relative address within the current IIS application - for example "Service.svc".</span></span> <span data-ttu-id="bc24d-117">В WCF 4,0 этот относительный адрес должен содержать одно из известных расширений файлов (. svc,. xamlx,...). Для Релативеурл не существует физического файла.</span><span class="sxs-lookup"><span data-stu-id="bc24d-117">In WCF 4.0 this relative address has to contain one of the known file extensions (.svc, .xamlx, ...). No physical file has to exist for the relativeUrl</span></span>|

### <a name="child-elements"></a><span data-ttu-id="bc24d-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bc24d-118">Child Elements</span></span>

<span data-ttu-id="bc24d-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bc24d-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bc24d-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bc24d-120">Parent Elements</span></span>

|<span data-ttu-id="bc24d-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="bc24d-121">Element</span></span>|<span data-ttu-id="bc24d-122">Описание</span><span class="sxs-lookup"><span data-stu-id="bc24d-122">Description</span></span>|
|-------------|-----------------|
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="bc24d-123">Раздел конфигурации, в котором описываются параметры активации.</span><span class="sxs-lookup"><span data-stu-id="bc24d-123">A configuration section that describes activation settings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bc24d-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="bc24d-124">Remarks</span></span>

<span data-ttu-id="bc24d-125">В следующем примере показано, как настроить параметры активации в файле web.config.</span><span class="sxs-lookup"><span data-stu-id="bc24d-125">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="bc24d-126">Использование этой конфигурации позволяет активировать GreetingService без SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="bc24d-126">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="bc24d-127">Следует отметить, что `<serviceHostingEnvironment>` является конфигурацией на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="bc24d-127">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="bc24d-128">Необходимо разместить файл `web.config`, содержащий конфигурацию в корневом каталоге виртуального приложения.</span><span class="sxs-lookup"><span data-stu-id="bc24d-128">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="bc24d-129">Кроме того, `serviceHostingEnvironment` является machineToApplication наследуемым разделом.</span><span class="sxs-lookup"><span data-stu-id="bc24d-129">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="bc24d-130">Если зарегистрировать одну службу в корневом каталоге компьютера, каждая служба в приложении унаследует эту службу.</span><span class="sxs-lookup"><span data-stu-id="bc24d-130">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="bc24d-131">Активация на основе конфигурации поддерживает активацию как по протоколу HTTP, так и по протоколу, отличному от HTTP.</span><span class="sxs-lookup"><span data-stu-id="bc24d-131">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="bc24d-132">Для этого требуются расширения в Релативеаддресс, например. svc,. XOML или. xamlx.</span><span class="sxs-lookup"><span data-stu-id="bc24d-132">It requires extensions in the relativeAddress, i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="bc24d-133">Можно сопоставить пользовательские расширения с известными поставщиками buildProvider, что впоследствии позволит активировать службу через любое расширение.</span><span class="sxs-lookup"><span data-stu-id="bc24d-133">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="bc24d-134">При возникновении конфликта раздел `<serviceActivations>` переопределяет записи в SVC-файле.</span><span class="sxs-lookup"><span data-stu-id="bc24d-134">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc24d-135">См. также</span><span class="sxs-lookup"><span data-stu-id="bc24d-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
