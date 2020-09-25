---
title: Элемент <assemblyBinding> для <runtime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding
helpviewer_keywords:
- <assemblyBinding> element
- assemblyBinding element
- container tags, <assemblyBinding> element
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
ms.openlocfilehash: b6a39bcecfd2485481677496adcf026d986c283b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170250"
---
# <a name="assemblybinding-element-for-runtime"></a><span data-ttu-id="d8b24-102">Элемент \<assemblyBinding> для \<runtime></span><span class="sxs-lookup"><span data-stu-id="d8b24-102">\<assemblyBinding> Element for \<runtime></span></span>

<span data-ttu-id="d8b24-103">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="d8b24-103">Contains information about assembly version redirection and the locations of assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="d8b24-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8b24-104">Syntax</span></span>  
  
```xml  
      <assemblyBinding
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8b24-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d8b24-105">Attributes and Elements</span></span>  

 <span data-ttu-id="d8b24-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d8b24-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8b24-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d8b24-107">Attributes</span></span>  
  
|<span data-ttu-id="d8b24-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d8b24-108">Attribute</span></span>|<span data-ttu-id="d8b24-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d8b24-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d8b24-110">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="d8b24-110">**xmlns**</span></span>|<span data-ttu-id="d8b24-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d8b24-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="d8b24-112">Задает пространство имен XML, необходимое для привязки сборок.</span><span class="sxs-lookup"><span data-stu-id="d8b24-112">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="d8b24-113">Используйте строку urn:schemas-microsoft-com:asm.v1 в качестве значения.</span><span class="sxs-lookup"><span data-stu-id="d8b24-113">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span>|  
|<span data-ttu-id="d8b24-114">**appliesTo**</span><span class="sxs-lookup"><span data-stu-id="d8b24-114">**appliesTo**</span></span>|<span data-ttu-id="d8b24-115">Задает версию среды выполнения, к которой применяется перенаправление сборки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d8b24-115">Specifies the runtime version the .NET Framework assembly redirection applies to.</span></span> <span data-ttu-id="d8b24-116">Этот необязательный атрибут содержит номер версии .NET Framework, к которой применяется перенаправление.</span><span class="sxs-lookup"><span data-stu-id="d8b24-116">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="d8b24-117">Если атрибут **appliesTo** не указан, элемент **\<assemblyBinding>** применяется ко всем версиям платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d8b24-117">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="d8b24-118">Атрибут **appliesTo** появился в .NET Framework версии 1,1; он игнорируется .NET Framework версии 1,0.</span><span class="sxs-lookup"><span data-stu-id="d8b24-118">The **appliesTo** attribute was introduced in .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="d8b24-119">Это означает, что при использовании платформы .NET Framework версии 1.0 применяются все элементы **\<assemblyBinding>** , даже если атрибут **appliesTo** задан.</span><span class="sxs-lookup"><span data-stu-id="d8b24-119">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8b24-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d8b24-120">Child Elements</span></span>  
  
|<span data-ttu-id="d8b24-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="d8b24-121">Element</span></span>|<span data-ttu-id="d8b24-122">Описание</span><span class="sxs-lookup"><span data-stu-id="d8b24-122">Description</span></span>|  
|-------------|-----------------|  
|[\<dependentAssembly>](dependentassembly-element.md)|<span data-ttu-id="d8b24-123">Инкапсулирует политику привязки и расположение сборки.</span><span class="sxs-lookup"><span data-stu-id="d8b24-123">Encapsulates binding policy and assembly location for an assembly.</span></span> <span data-ttu-id="d8b24-124">**\<dependentAssembly>** Для каждой сборки используется один тег.</span><span class="sxs-lookup"><span data-stu-id="d8b24-124">Use one **\<dependentAssembly>** tag for each assembly.</span></span>|  
|[\<probing>](probing-element.md)|<span data-ttu-id="d8b24-125">Задает вложенные папки, в которых среда CLR выполняет поиск при загрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="d8b24-125">Specifies subdirectories the common language runtime searches when loading assemblies.</span></span>|  
|[\<publisherPolicy>](publisherpolicy-element.md)|<span data-ttu-id="d8b24-126">Указывает, применяет ли среда выполнения политику издателя.</span><span class="sxs-lookup"><span data-stu-id="d8b24-126">Specifies whether the runtime applies publisher policy.</span></span>|  
|[\<qualifyAssembly>](qualifyassembly-element.md)|<span data-ttu-id="d8b24-127">Задает полное имя сборки, которая должна загружаться динамически в случае использования неполного имени.</span><span class="sxs-lookup"><span data-stu-id="d8b24-127">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d8b24-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d8b24-128">Parent Elements</span></span>  
  
|<span data-ttu-id="d8b24-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="d8b24-129">Element</span></span>|<span data-ttu-id="d8b24-130">Описание</span><span class="sxs-lookup"><span data-stu-id="d8b24-130">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d8b24-131">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d8b24-131">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d8b24-132">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="d8b24-132">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d8b24-133">Пример</span><span class="sxs-lookup"><span data-stu-id="d8b24-133">Example</span></span>  

 <span data-ttu-id="d8b24-134">В следующем примере показан способ перенаправления одной версии сборки на другую и предоставлена база кода.</span><span class="sxs-lookup"><span data-stu-id="d8b24-134">The following example shows how to redirect one assembly version to another and provide a codebase.</span></span>  
  
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
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="d8b24-135">В следующем примере показано, как использовать атрибут **appliesTo** для перенаправления привязки .NET Framework сборки.</span><span class="sxs-lookup"><span data-stu-id="d8b24-135">The following example shows how to use the **appliesTo** attribute to redirect binding of a .NET Framework assembly.</span></span>  
  
```xml  
<runtime>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
      <dependentAssembly>
         <assemblyIdentity name="mscorcfg" publicKeyToken="b03f5f7f11d50a3a" culture=""/>  
         <bindingRedirect oldVersion="0.0.0.0-65535.65535.65535.65535" newVersion="1.0.3300.0"/>  
      </dependentAssembly>  
   </assemblyBinding>  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8b24-136">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d8b24-136">See also</span></span>

- [<span data-ttu-id="d8b24-137">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="d8b24-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d8b24-138">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="d8b24-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="d8b24-139">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="d8b24-139">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
