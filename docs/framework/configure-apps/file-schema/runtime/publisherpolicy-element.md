---
title: Элемент <publisherPolicy>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
ms.openlocfilehash: 89fa8a991cc7d0352eb0a13cdfd3a6063ea468e7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115846"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="da1e8-102">Элемент \<publisherPolicy></span><span class="sxs-lookup"><span data-stu-id="da1e8-102">\<publisherPolicy> Element</span></span>
<span data-ttu-id="da1e8-103">Указывает, применяет ли среда выполнения политику издателя.</span><span class="sxs-lookup"><span data-stu-id="da1e8-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<publisherPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="da1e8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da1e8-104">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da1e8-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="da1e8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="da1e8-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="da1e8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da1e8-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="da1e8-107">Attributes</span></span>  
  
|<span data-ttu-id="da1e8-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="da1e8-108">Attribute</span></span>|<span data-ttu-id="da1e8-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="da1e8-109">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="da1e8-110">Указывает, следует ли применять политику издателя.</span><span class="sxs-lookup"><span data-stu-id="da1e8-110">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="da1e8-111">применить атрибут</span><span class="sxs-lookup"><span data-stu-id="da1e8-111">apply Attribute</span></span>  
  
|<span data-ttu-id="da1e8-112">Значение</span><span class="sxs-lookup"><span data-stu-id="da1e8-112">Value</span></span>|<span data-ttu-id="da1e8-113">Описание</span><span class="sxs-lookup"><span data-stu-id="da1e8-113">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="da1e8-114">Применяет политику издателя.</span><span class="sxs-lookup"><span data-stu-id="da1e8-114">Applies publisher policy.</span></span> <span data-ttu-id="da1e8-115">Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="da1e8-115">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="da1e8-116">Политика издателя не применяется.</span><span class="sxs-lookup"><span data-stu-id="da1e8-116">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da1e8-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="da1e8-117">Child Elements</span></span>  

<span data-ttu-id="da1e8-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="da1e8-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da1e8-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="da1e8-119">Parent Elements</span></span>  
  
|<span data-ttu-id="da1e8-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="da1e8-120">Element</span></span>|<span data-ttu-id="da1e8-121">Описание</span><span class="sxs-lookup"><span data-stu-id="da1e8-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="da1e8-122">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="da1e8-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="da1e8-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="da1e8-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="da1e8-124">Инкапсулирует политику привязки и расположение каждой сборки.</span><span class="sxs-lookup"><span data-stu-id="da1e8-124">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="da1e8-125">`<dependentAssembly>`Для каждой сборки используется один элемент.</span><span class="sxs-lookup"><span data-stu-id="da1e8-125">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="da1e8-126">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="da1e8-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da1e8-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="da1e8-127">Remarks</span></span>  
 <span data-ttu-id="da1e8-128">Когда поставщик компонента выпускает новую версию сборки, поставщик может включить политику издателя, чтобы приложения, использующие старую версию, теперь использовали новую версию.</span><span class="sxs-lookup"><span data-stu-id="da1e8-128">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="da1e8-129">Чтобы указать, следует ли применять политику издателя для определенной сборки, поставьте **\<publisherPolicy>** элемент в **\<dependentAssembly>** элемент.</span><span class="sxs-lookup"><span data-stu-id="da1e8-129">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="da1e8-130">Значение по умолчанию для атрибута **Apply** — **Да**.</span><span class="sxs-lookup"><span data-stu-id="da1e8-130">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="da1e8-131">Присвоение атрибуту **Apply** значения **No** переопределяет любые предыдущие параметры **Yes** для сборки.</span><span class="sxs-lookup"><span data-stu-id="da1e8-131">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="da1e8-132">Чтобы приложение явно игнорировало политику издателя с помощью [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) элемента в файле конфигурации приложения, требуется разрешение.</span><span class="sxs-lookup"><span data-stu-id="da1e8-132">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="da1e8-133">Разрешение предоставляется путем установки <xref:System.Security.Permissions.SecurityPermissionFlag> флага для <xref:System.Security.Permissions.SecurityPermission> .</span><span class="sxs-lookup"><span data-stu-id="da1e8-133">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="da1e8-134">Дополнительные сведения см. в статье [разрешение безопасности перенаправления привязки сборок](../../assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="da1e8-134">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="da1e8-135">Пример</span><span class="sxs-lookup"><span data-stu-id="da1e8-135">Example</span></span>  
 <span data-ttu-id="da1e8-136">В следующем примере отключается политика издателя для сборки `myAssembly` .</span><span class="sxs-lookup"><span data-stu-id="da1e8-136">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="da1e8-137">См. также</span><span class="sxs-lookup"><span data-stu-id="da1e8-137">See also</span></span>

- [<span data-ttu-id="da1e8-138">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="da1e8-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="da1e8-139">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="da1e8-139">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="da1e8-140">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="da1e8-140">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="da1e8-141">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="da1e8-141">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
