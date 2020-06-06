---
title: Элемент <dependentAssembly>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#dependentAssembly
helpviewer_keywords:
- container tags, <dependentAssembly> element
- dependentAssembly element
- <dependentAssembly> element
ms.assetid: 14e95627-dd79-4b82-ac85-e682aa3a31d8
ms.openlocfilehash: 2de8c752867d00708173d11d1851f415a2e8518d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154209"
---
# <a name="dependentassembly-element"></a><span data-ttu-id="cf28d-102">Элемент \<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="cf28d-102">\<dependentAssembly> Element</span></span>
<span data-ttu-id="cf28d-103">Инкапсулирует политику привязки и расположение каждой сборки.</span><span class="sxs-lookup"><span data-stu-id="cf28d-103">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="cf28d-104">`dependentAssembly`Для каждой сборки используется один элемент.</span><span class="sxs-lookup"><span data-stu-id="cf28d-104">Use one `dependentAssembly` element for each assembly.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dependentAssembly>**  
  
## <a name="syntax"></a><span data-ttu-id="cf28d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf28d-105">Syntax</span></span>  
  
```xml  
<dependentAssembly>
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf28d-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cf28d-106">Attributes and Elements</span></span>  
 <span data-ttu-id="cf28d-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cf28d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf28d-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cf28d-108">Attributes</span></span>  
 <span data-ttu-id="cf28d-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cf28d-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cf28d-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cf28d-110">Child Elements</span></span>  
  
|<span data-ttu-id="cf28d-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="cf28d-111">Element</span></span>|<span data-ttu-id="cf28d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="cf28d-112">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="cf28d-113">Содержит идентифицирующие сведения о сборке.</span><span class="sxs-lookup"><span data-stu-id="cf28d-113">Contains identifying information about the assembly.</span></span> <span data-ttu-id="cf28d-114">Этот элемент должен включаться в каждый `dependentAssembly` элемент.</span><span class="sxs-lookup"><span data-stu-id="cf28d-114">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="cf28d-115">Указывает, где среда выполнения может найти общую сборку, если она не установлена на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cf28d-115">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="cf28d-116">Перенаправляет одну версию сборки на другую.</span><span class="sxs-lookup"><span data-stu-id="cf28d-116">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="cf28d-117">Указывает, применяет ли среда выполнения политику издателя для этой сборки.</span><span class="sxs-lookup"><span data-stu-id="cf28d-117">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cf28d-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cf28d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="cf28d-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="cf28d-119">Element</span></span>|<span data-ttu-id="cf28d-120">Описание</span><span class="sxs-lookup"><span data-stu-id="cf28d-120">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="cf28d-121">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="cf28d-121">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="cf28d-122">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf28d-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="cf28d-123">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="cf28d-123">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cf28d-124">Пример</span><span class="sxs-lookup"><span data-stu-id="cf28d-124">Example</span></span>  
 <span data-ttu-id="cf28d-125">В следующем примере показано, как инкапсулировать сведения о сборке для двух сборок.</span><span class="sxs-lookup"><span data-stu-id="cf28d-125">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="mySecondAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for mySecondAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf28d-126">См. также</span><span class="sxs-lookup"><span data-stu-id="cf28d-126">See also</span></span>

- [<span data-ttu-id="cf28d-127">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="cf28d-127">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="cf28d-128">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="cf28d-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="cf28d-129">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="cf28d-129">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
