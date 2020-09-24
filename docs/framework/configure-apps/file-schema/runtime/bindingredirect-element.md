---
title: Элемент <bindingRedirect>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/bindingRedirect
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bindingRedirect
helpviewer_keywords:
- <bindingRedirect> element
- container tags, <bindingRedirect> element
- bindingRedirect element
ms.assetid: 67784ecd-9663-434e-bd6a-26975e447ac0
ms.openlocfilehash: 7667f78d2c341990585526fd153c0b230658a2ee
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167253"
---
# <a name="bindingredirect-element"></a><span data-ttu-id="83f56-102">Элемент \<bindingRedirect></span><span class="sxs-lookup"><span data-stu-id="83f56-102">\<bindingRedirect> Element</span></span>

<span data-ttu-id="83f56-103">Перенаправляет одну версию сборки на другую.</span><span class="sxs-lookup"><span data-stu-id="83f56-103">Redirects one assembly version to another.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bindingRedirect>**  
  
## <a name="syntax"></a><span data-ttu-id="83f56-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83f56-104">Syntax</span></span>  
  
```xml  
   <bindingRedirect
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83f56-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="83f56-105">Attributes and Elements</span></span>  

 <span data-ttu-id="83f56-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="83f56-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83f56-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="83f56-107">Attributes</span></span>  
  
|<span data-ttu-id="83f56-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="83f56-108">Attribute</span></span>|<span data-ttu-id="83f56-109">Описание</span><span class="sxs-lookup"><span data-stu-id="83f56-109">Description</span></span>|  
|---------------|-----------------|  
|`oldVersion`|<span data-ttu-id="83f56-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="83f56-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="83f56-111">Задает первоначально запрошенную версию сборки.</span><span class="sxs-lookup"><span data-stu-id="83f56-111">Specifies the version of the assembly that was originally requested.</span></span> <span data-ttu-id="83f56-112">Номер версии сборки имеет формат *основной. дополнительный. сборка. Редакция*.</span><span class="sxs-lookup"><span data-stu-id="83f56-112">The format of an assembly version number is *major.minor.build.revision*.</span></span> <span data-ttu-id="83f56-113">Допустимые значения для каждой части этого номера версии — от 0 до 65535.</span><span class="sxs-lookup"><span data-stu-id="83f56-113">Valid values for each part of this version number are 0 to 65535.</span></span><br /><br /> <span data-ttu-id="83f56-114">Диапазон версий можно также задать в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="83f56-114">You can also specify a range of versions in the following format:</span></span><br /><br /> <span data-ttu-id="83f56-115">*n. n. n. n-n. n. n. n*</span><span class="sxs-lookup"><span data-stu-id="83f56-115">*n.n.n.n - n.n.n.n*</span></span>|  
|`newVersion`|<span data-ttu-id="83f56-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="83f56-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="83f56-117">Указывает версию сборки, используемую вместо первоначально запрошенной версии в формате: *n. n. n. n*</span><span class="sxs-lookup"><span data-stu-id="83f56-117">Specifies the version of the assembly to use instead of the originally requested version in the format: *n.n.n.n*</span></span><br /><br /> <span data-ttu-id="83f56-118">Это значение может указывать более раннюю версию, чем `oldVersion`.</span><span class="sxs-lookup"><span data-stu-id="83f56-118">This value can specify an earlier version than `oldVersion`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83f56-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="83f56-119">Child Elements</span></span>  
  
|<span data-ttu-id="83f56-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="83f56-120">Element</span></span>|<span data-ttu-id="83f56-121">Описание</span><span class="sxs-lookup"><span data-stu-id="83f56-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="83f56-122">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="83f56-122">None</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="83f56-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="83f56-123">Parent Elements</span></span>  
  
|<span data-ttu-id="83f56-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="83f56-124">Element</span></span>|<span data-ttu-id="83f56-125">Описание</span><span class="sxs-lookup"><span data-stu-id="83f56-125">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="83f56-126">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="83f56-126">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="83f56-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="83f56-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="83f56-128">Инкапсулирует политику привязки и расположение каждой сборки.</span><span class="sxs-lookup"><span data-stu-id="83f56-128">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="83f56-129">Для каждой сборки используется только один элемент dependentAssembly.</span><span class="sxs-lookup"><span data-stu-id="83f56-129">Use one dependentAssembly element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="83f56-130">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="83f56-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83f56-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="83f56-131">Remarks</span></span>  

 <span data-ttu-id="83f56-132">При сборке приложения .NET Framework с использованием сборки со строгим именем приложение во время выполнения по умолчанию будет использовать эту версию сборки, даже если доступна новая версия.</span><span class="sxs-lookup"><span data-stu-id="83f56-132">When you build a .NET Framework application against a strong-named assembly, the application uses that version of the assembly at run time by default, even if a new version is available.</span></span> <span data-ttu-id="83f56-133">Однако приложение можно настроить для выполнения с новой версией сборки.</span><span class="sxs-lookup"><span data-stu-id="83f56-133">However, you can configure the application to run against a newer version of the assembly.</span></span> <span data-ttu-id="83f56-134">Дополнительные сведения о том, как среда выполнения использует эти файлы для определения используемой версии сборки, см. в разделе [как среда выполнения находит сборки](../../../deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="83f56-134">For details on how the runtime uses these files to determine which assembly version to use, see [How the Runtime Locates Assemblies](../../../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="83f56-135">Перенаправление нескольких версий сборок можно выполнить, включив в элемент `bindingRedirect` несколько элементов `dependentAssembly`.</span><span class="sxs-lookup"><span data-stu-id="83f56-135">You can redirect more than one assembly version by including multiple `bindingRedirect` elements in a `dependentAssembly` element.</span></span> <span data-ttu-id="83f56-136">Можно также выполнить перенаправление с более новой версии на более раннюю версию сборки.</span><span class="sxs-lookup"><span data-stu-id="83f56-136">You can also redirect from a newer version to an older version of the assembly.</span></span>  
  
 <span data-ttu-id="83f56-137">Для явного перенаправления привязки сборки в файле конфигурации приложения необходимо разрешение безопасности.</span><span class="sxs-lookup"><span data-stu-id="83f56-137">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="83f56-138">Это относится к перенаправлению как сборок платформы .NET Framework, так и сторонних сборок.</span><span class="sxs-lookup"><span data-stu-id="83f56-138">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="83f56-139">Разрешение предоставляется путем установки <xref:System.Security.Permissions.SecurityPermissionFlag> флага для <xref:System.Security.Permissions.SecurityPermission> .</span><span class="sxs-lookup"><span data-stu-id="83f56-139">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="83f56-140">Дополнительные сведения см. в статье [разрешение безопасности перенаправления привязки сборок](../../assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="83f56-140">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="83f56-141">Пример</span><span class="sxs-lookup"><span data-stu-id="83f56-141">Example</span></span>  

 <span data-ttu-id="83f56-142">В следующем примере показан способ перенаправления одной версии сборки на другую.</span><span class="sxs-lookup"><span data-stu-id="83f56-142">The following example shows how to redirect one assembly version to another.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="83f56-143">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="83f56-143">See also</span></span>

- [<span data-ttu-id="83f56-144">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="83f56-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="83f56-145">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="83f56-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="83f56-146">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="83f56-146">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
