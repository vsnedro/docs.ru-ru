---
title: Элемент <generatePublisherEvidence>
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: c2ba4a7244b7849e28eac38fb34a2cdd0d1f1048
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645358"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="721e8-102">\<Элемент generatePublisherEvidence></span><span class="sxs-lookup"><span data-stu-id="721e8-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="721e8-103">Уточняется, создает <xref:System.Security.Policy.Publisher> ли время выполнения доказательства безопасности доступа к коду (CAS).</span><span class="sxs-lookup"><span data-stu-id="721e8-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
<span data-ttu-id="721e8-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="721e8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="721e8-105">&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="721e8-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="721e8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<генерироватьPublisherEvidence>**</span><span class="sxs-lookup"><span data-stu-id="721e8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="721e8-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="721e8-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="721e8-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="721e8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="721e8-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="721e8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="721e8-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="721e8-110">Attributes</span></span>  
  
|<span data-ttu-id="721e8-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="721e8-111">Attribute</span></span>|<span data-ttu-id="721e8-112">Описание</span><span class="sxs-lookup"><span data-stu-id="721e8-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="721e8-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="721e8-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="721e8-114">Уточняется, создает <xref:System.Security.Policy.Publisher> ли время выполнения доказательства.</span><span class="sxs-lookup"><span data-stu-id="721e8-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="721e8-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="721e8-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="721e8-116">Значение</span><span class="sxs-lookup"><span data-stu-id="721e8-116">Value</span></span>|<span data-ttu-id="721e8-117">Описание</span><span class="sxs-lookup"><span data-stu-id="721e8-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="721e8-118">Не создает <xref:System.Security.Policy.Publisher> доказательств.</span><span class="sxs-lookup"><span data-stu-id="721e8-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="721e8-119">Создает <xref:System.Security.Policy.Publisher> доказательства.</span><span class="sxs-lookup"><span data-stu-id="721e8-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="721e8-120">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="721e8-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="721e8-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="721e8-121">Child Elements</span></span>  
 <span data-ttu-id="721e8-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="721e8-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="721e8-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="721e8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="721e8-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="721e8-124">Element</span></span>|<span data-ttu-id="721e8-125">Описание</span><span class="sxs-lookup"><span data-stu-id="721e8-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="721e8-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="721e8-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="721e8-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="721e8-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="721e8-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="721e8-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="721e8-129">В рамках .NET 4 и позже этот элемент не влияет на время сборки.</span><span class="sxs-lookup"><span data-stu-id="721e8-129">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="721e8-130">Для получения дополнительной информации смотрите раздел "Упрощение политики [безопасности" в разделе "Изменения безопасности".](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes)</span><span class="sxs-lookup"><span data-stu-id="721e8-130">For more information, see the "Security Policy Simplification" section in [Security Changes](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).</span></span>  
  
 <span data-ttu-id="721e8-131">Общее время выполнения языка (CLR) пытается проверить подпись Authenticode <xref:System.Security.Policy.Publisher> во время загрузки, чтобы создать улики для сборки.</span><span class="sxs-lookup"><span data-stu-id="721e8-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="721e8-132">Однако по умолчанию большинству <xref:System.Security.Policy.Publisher> приложений не нужны доказательства.</span><span class="sxs-lookup"><span data-stu-id="721e8-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="721e8-133">Стандартная политика CAS не <xref:System.Security.Policy.PublisherMembershipCondition>опирается на .</span><span class="sxs-lookup"><span data-stu-id="721e8-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="721e8-134">Следует избегать ненужных затрат на запуск, связанных с проверкой подписи издателя, если приложение не <xref:System.Security.Permissions.PublisherIdentityPermission> выполняется на компьютере с пользовательской политикой CAS или не намерено удовлетворять требования в среде частичного доверия.</span><span class="sxs-lookup"><span data-stu-id="721e8-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="721e8-135">(Требования к разрешению на идентификацию всегда удались в условиях полного доверия.)</span><span class="sxs-lookup"><span data-stu-id="721e8-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="721e8-136">Мы рекомендуем службам `<generatePublisherEvidence>` использовать элемент для повышения производительности запуска.</span><span class="sxs-lookup"><span data-stu-id="721e8-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="721e8-137">Использование этого элемента также может помочь избежать задержек, которые могут привести к тайм-ауту и отмене запуска службы.</span><span class="sxs-lookup"><span data-stu-id="721e8-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="721e8-138">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="721e8-138">Configuration File</span></span>  
 <span data-ttu-id="721e8-139">Этот элемент может быть использован только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="721e8-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="721e8-140">Пример</span><span class="sxs-lookup"><span data-stu-id="721e8-140">Example</span></span>  
 <span data-ttu-id="721e8-141">Ниже приводится следующий `<generatePublisherEvidence>` пример, как использовать элемент для отсеивания проверки политики издателя CAS для приложения.</span><span class="sxs-lookup"><span data-stu-id="721e8-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="721e8-142">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="721e8-142">See also</span></span>

- [<span data-ttu-id="721e8-143">Схема настройки выполнения</span><span class="sxs-lookup"><span data-stu-id="721e8-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="721e8-144">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="721e8-144">Configuration File Schema</span></span>](../index.md)
