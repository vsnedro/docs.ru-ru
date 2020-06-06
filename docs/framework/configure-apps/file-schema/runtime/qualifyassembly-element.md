---
title: Элемент <qualifyAssembly>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
ms.openlocfilehash: 74e83900c68ab4b3fe01beb3f97657b0140d78ad
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153923"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="9045f-102">Элемент \<qualifyAssembly></span><span class="sxs-lookup"><span data-stu-id="9045f-102">\<qualifyAssembly> Element</span></span>
<span data-ttu-id="9045f-103">Задает полное имя сборки, которая должна загружаться динамически в случае использования неполного имени.</span><span class="sxs-lookup"><span data-stu-id="9045f-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**  
  
## <a name="syntax"></a><span data-ttu-id="9045f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9045f-104">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9045f-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9045f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9045f-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9045f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9045f-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9045f-107">Attributes</span></span>  
  
|<span data-ttu-id="9045f-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9045f-108">Attribute</span></span>|<span data-ttu-id="9045f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9045f-109">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="9045f-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="9045f-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="9045f-111">Задает частичное имя сборки в том виде, в котором оно отображается в коде.</span><span class="sxs-lookup"><span data-stu-id="9045f-111">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="9045f-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="9045f-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="9045f-113">Задает полное имя сборки в том виде, в каком оно отображается в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="9045f-113">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9045f-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9045f-114">Child Elements</span></span>  
 <span data-ttu-id="9045f-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9045f-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9045f-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9045f-116">Parent Elements</span></span>  
  
|<span data-ttu-id="9045f-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="9045f-117">Element</span></span>|<span data-ttu-id="9045f-118">Описание</span><span class="sxs-lookup"><span data-stu-id="9045f-118">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="9045f-119">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="9045f-119">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="9045f-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9045f-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9045f-121">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="9045f-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9045f-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="9045f-122">Remarks</span></span>  
 <span data-ttu-id="9045f-123">Вызов <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> метода с использованием частичных имен сборок приводит к тому, что среда CLR ищет сборку только в базовом каталоге приложения.</span><span class="sxs-lookup"><span data-stu-id="9045f-123">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="9045f-124">Используйте **\<qualifyAssembly>** элемент в файле конфигурации приложения, чтобы предоставить полные сведения о сборке (имя, версию, маркер открытого ключа и язык и региональные параметры) и вызвать поиск сборки в глобальном кэше сборок в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="9045f-124">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="9045f-125">Атрибут **FullName** должен включать четыре поля удостоверения сборки: имя, версия, токен открытого ключа и язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="9045f-125">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="9045f-126">Атрибут **партиалнаме** должен ссылаться на сборку частично.</span><span class="sxs-lookup"><span data-stu-id="9045f-126">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="9045f-127">Необходимо указать по крайней мере текстовое имя сборки (наиболее распространенный случай), но можно также включить версию, токен открытого ключа или язык и региональные параметры (или любое сочетание четырех, но не все четыре).</span><span class="sxs-lookup"><span data-stu-id="9045f-127">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="9045f-128">**Партиалнаме** должно соответствовать имени, указанному в вызове.</span><span class="sxs-lookup"><span data-stu-id="9045f-128">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="9045f-129">Например, нельзя указать в `"math"` файле конфигурации в качестве атрибута **партиалнаме** и вызвать `Assembly.Load("math, Version=3.3.3.3")` в коде.</span><span class="sxs-lookup"><span data-stu-id="9045f-129">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9045f-130">Пример</span><span class="sxs-lookup"><span data-stu-id="9045f-130">Example</span></span>  
 <span data-ttu-id="9045f-131">Следующий пример логически включает вызов `Assembly.Load("math")` `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")` .</span><span class="sxs-lookup"><span data-stu-id="9045f-131">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9045f-132">См. также</span><span class="sxs-lookup"><span data-stu-id="9045f-132">See also</span></span>

- [<span data-ttu-id="9045f-133">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="9045f-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9045f-134">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="9045f-134">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="9045f-135">[Частичные ссылки на сборки](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9045f-135">[Partial Assembly References](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
