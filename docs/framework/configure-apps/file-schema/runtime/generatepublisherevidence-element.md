---
title: Элемент <generatePublisherEvidence>
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: c2ba4a7244b7849e28eac38fb34a2cdd0d1f1048
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "81645358"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="6deb5-102">Элемент \<generatePublisherEvidence></span><span class="sxs-lookup"><span data-stu-id="6deb5-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="6deb5-103">Указывает, создает ли среда выполнения <xref:System.Security.Policy.Publisher> свидетельство для управления доступом для кода (CAS).</span><span class="sxs-lookup"><span data-stu-id="6deb5-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**  
  
## <a name="syntax"></a><span data-ttu-id="6deb5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6deb5-104">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6deb5-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6deb5-105">Attributes and Elements</span></span>  
 <span data-ttu-id="6deb5-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6deb5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6deb5-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6deb5-107">Attributes</span></span>  
  
|<span data-ttu-id="6deb5-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6deb5-108">Attribute</span></span>|<span data-ttu-id="6deb5-109">Описание</span><span class="sxs-lookup"><span data-stu-id="6deb5-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="6deb5-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="6deb5-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="6deb5-111">Указывает, создает ли среда выполнения <xref:System.Security.Policy.Publisher> свидетельство.</span><span class="sxs-lookup"><span data-stu-id="6deb5-111">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="6deb5-112">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="6deb5-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="6deb5-113">Значение</span><span class="sxs-lookup"><span data-stu-id="6deb5-113">Value</span></span>|<span data-ttu-id="6deb5-114">Описание</span><span class="sxs-lookup"><span data-stu-id="6deb5-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="6deb5-115">Не создает <xref:System.Security.Policy.Publisher> свидетельство.</span><span class="sxs-lookup"><span data-stu-id="6deb5-115">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="6deb5-116">Создает <xref:System.Security.Policy.Publisher> свидетельство.</span><span class="sxs-lookup"><span data-stu-id="6deb5-116">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="6deb5-117">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6deb5-117">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6deb5-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6deb5-118">Child Elements</span></span>  
 <span data-ttu-id="6deb5-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6deb5-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6deb5-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6deb5-120">Parent Elements</span></span>  
  
|<span data-ttu-id="6deb5-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="6deb5-121">Element</span></span>|<span data-ttu-id="6deb5-122">Описание</span><span class="sxs-lookup"><span data-stu-id="6deb5-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6deb5-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6deb5-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6deb5-124">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="6deb5-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6deb5-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="6deb5-125">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6deb5-126">В .NET Framework 4 и более поздних версиях этот элемент не влияет на время загрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="6deb5-126">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="6deb5-127">Дополнительные сведения см. в разделе "упрощение политики безопасности" раздела [изменения в системе безопасности](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).</span><span class="sxs-lookup"><span data-stu-id="6deb5-127">For more information, see the "Security Policy Simplification" section in [Security Changes](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).</span></span>  
  
 <span data-ttu-id="6deb5-128">Среда CLR пытается проверить подпись Authenticode во время загрузки, чтобы создать <xref:System.Security.Policy.Publisher> свидетельство для сборки.</span><span class="sxs-lookup"><span data-stu-id="6deb5-128">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="6deb5-129">Однако по умолчанию большинству приложений не требуется <xref:System.Security.Policy.Publisher> свидетельство.</span><span class="sxs-lookup"><span data-stu-id="6deb5-129">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="6deb5-130">Стандартная политика CAS не зависит от <xref:System.Security.Policy.PublisherMembershipCondition> .</span><span class="sxs-lookup"><span data-stu-id="6deb5-130">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="6deb5-131">Следует избегать ненужных затрат на запуск, связанных с проверкой подписи издателя, если приложение не выполняется на компьютере с настраиваемой политикой CAS или планирует удовлетворить требования к <xref:System.Security.Permissions.PublisherIdentityPermission> в среде с частичным доверием.</span><span class="sxs-lookup"><span data-stu-id="6deb5-131">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="6deb5-132">(Требования для разрешений идентификации всегда выполняются в среде с полным доверием.)</span><span class="sxs-lookup"><span data-stu-id="6deb5-132">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6deb5-133">Рекомендуется, чтобы службы использовали `<generatePublisherEvidence>` элемент для повышения производительности при запуске.</span><span class="sxs-lookup"><span data-stu-id="6deb5-133">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="6deb5-134">Использование этого элемента также может помочь избежать задержек, которые могут привести к превышению времени ожидания и отмене запуска службы.</span><span class="sxs-lookup"><span data-stu-id="6deb5-134">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="6deb5-135">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="6deb5-135">Configuration File</span></span>  
 <span data-ttu-id="6deb5-136">Этот элемент может использоваться только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="6deb5-136">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6deb5-137">Пример</span><span class="sxs-lookup"><span data-stu-id="6deb5-137">Example</span></span>  
 <span data-ttu-id="6deb5-138">В следующем примере показано, как использовать `<generatePublisherEvidence>` элемент, чтобы отключить проверку политики ИЗДАТЕЛЯ CAS для приложения.</span><span class="sxs-lookup"><span data-stu-id="6deb5-138">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6deb5-139">См. также</span><span class="sxs-lookup"><span data-stu-id="6deb5-139">See also</span></span>

- [<span data-ttu-id="6deb5-140">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="6deb5-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6deb5-141">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="6deb5-141">Configuration File Schema</span></span>](../index.md)
