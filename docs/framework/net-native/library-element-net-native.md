---
title: <Library> Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
ms.openlocfilehash: aeaa6b1a9c3c4ceebdd0eab3f331a044971398bf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287921"
---
# <a name="library-element-net-native"></a><span data-ttu-id="4fd3d-102">\<Library> Элемент (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="4fd3d-102">\<Library> Element (.NET Native)</span></span>

<span data-ttu-id="4fd3d-103">Определяет сборку, содержащую типы и члены типов, метаданные которой доступны для отражения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="4fd3d-103">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span>  
  
 <span data-ttu-id="4fd3d-104">Элемент \<Directives></span><span class="sxs-lookup"><span data-stu-id="4fd3d-104">\<Directives> Element</span></span>  
<span data-ttu-id="4fd3d-105">Элемент \<Library></span><span class="sxs-lookup"><span data-stu-id="4fd3d-105">\<Library> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fd3d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4fd3d-106">Syntax</span></span>  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4fd3d-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4fd3d-107">Attributes and Elements</span></span>  

 <span data-ttu-id="4fd3d-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4fd3d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4fd3d-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4fd3d-109">Attributes</span></span>  
  
|<span data-ttu-id="4fd3d-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4fd3d-110">Attribute</span></span>|<span data-ttu-id="4fd3d-111">Описание</span><span class="sxs-lookup"><span data-stu-id="4fd3d-111">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="4fd3d-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4fd3d-112">Required attribute.</span></span> <span data-ttu-id="4fd3d-113">Задает имя сборки.</span><span class="sxs-lookup"><span data-stu-id="4fd3d-113">Specifies the name of an assembly.</span></span> <span data-ttu-id="4fd3d-114">Дочерние элементы данного элемента `<Library>` определяют политику отражения среды выполнения для типов и членов типов в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="4fd3d-114">Child elements of this `<Library>` element define the runtime reflection policy for types and type members found in this assembly.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="4fd3d-115">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="4fd3d-115">Name attribute</span></span>  
  
|<span data-ttu-id="4fd3d-116">Значение</span><span class="sxs-lookup"><span data-stu-id="4fd3d-116">Value</span></span>|<span data-ttu-id="4fd3d-117">Описание</span><span class="sxs-lookup"><span data-stu-id="4fd3d-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4fd3d-118">*assembly_name*</span><span class="sxs-lookup"><span data-stu-id="4fd3d-118">*assembly_name*</span></span>|<span data-ttu-id="4fd3d-119">Простое имя сборки без расширения файла.</span><span class="sxs-lookup"><span data-stu-id="4fd3d-119">The simple name of the assembly, without its file extension.</span></span> <span data-ttu-id="4fd3d-120">Этот атрибут соответствует свойству <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4fd3d-120">This attribute corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="4fd3d-121">Например, имя сборки с именем Extensions.dll является «Extensions».</span><span class="sxs-lookup"><span data-stu-id="4fd3d-121">For example, the name of an assembly named Extensions.dll is "Extensions".</span></span> <span data-ttu-id="4fd3d-122">Сведения об особой форме имени сборки *assembly_name* с поддержкой условного включения метаданных сборки см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="4fd3d-122">See the Remarks section for a special form of *assembly_name* that supports conditional inclusion of metadata from the assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4fd3d-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4fd3d-123">Child Elements</span></span>  
  
|<span data-ttu-id="4fd3d-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="4fd3d-124">Element</span></span>|<span data-ttu-id="4fd3d-125">Описание</span><span class="sxs-lookup"><span data-stu-id="4fd3d-125">Description</span></span>|  
|-------------|-----------------|  
|[\<Assembly>](assembly-element-net-native.md)|<span data-ttu-id="4fd3d-126">Применяет политику ко всем типам в определенной сборке.</span><span class="sxs-lookup"><span data-stu-id="4fd3d-126">Applies policy to all the types in a particular assembly.</span></span>|  
|[\<Namespace>](namespace-element-net-native.md)|<span data-ttu-id="4fd3d-127">Применяет политику ко всем типам в определенном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="4fd3d-127">Applies policy to all the types in a particular namespace.</span></span>|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="4fd3d-128">Применяет политику для конкретного типа, например, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="4fd3d-128">Applies policy to a particular type, such as a class or structure.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="4fd3d-129">Применяет политику к сконструированному универсальному типу.</span><span class="sxs-lookup"><span data-stu-id="4fd3d-129">Applies policy to a constructed generic type.</span></span> <span data-ttu-id="4fd3d-130">Например, [\<TypeInstantiation>](typeinstantiation-element-net-native.md) элемент можно использовать для определения политики для `List<String>` типа.</span><span class="sxs-lookup"><span data-stu-id="4fd3d-130">For example, a [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element could be used to define policy for a `List<String>` type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4fd3d-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4fd3d-131">Parent Elements</span></span>  
  
|<span data-ttu-id="4fd3d-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="4fd3d-132">Element</span></span>|<span data-ttu-id="4fd3d-133">Описание</span><span class="sxs-lookup"><span data-stu-id="4fd3d-133">Description</span></span>|  
|-------------|-----------------|  
|[\<Directives>](directives-element-net-native.md)|<span data-ttu-id="4fd3d-134">Корневой элемент файла директив среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4fd3d-134">The root element of a runtime directives file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fd3d-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="4fd3d-135">Remarks</span></span>  

 <span data-ttu-id="4fd3d-136">[\<Directives>](directives-element-net-native.md)Элемент может содержать ноль, один или несколько `<Library>` элементов.</span><span class="sxs-lookup"><span data-stu-id="4fd3d-136">The [\<Directives>](directives-element-net-native.md) element can contain zero, one, or more `<Library>` elements.</span></span>  
  
 <span data-ttu-id="4fd3d-137">Элемент `<Library>` используется как контейнер для определения программных элементов, метаданные которых требуются во время выполнения. Этот элемент не выражают политики.</span><span class="sxs-lookup"><span data-stu-id="4fd3d-137">The `<Library>` element serves as a container to define the program elements whose metadata is needed at run time; this element doesn't express policy.</span></span> <span data-ttu-id="4fd3d-138">Во время компиляции средства компилятора осуществляют поиск только в библиотеке, назначенной с помощью элемента `<Library>`, на наличие программных элементов, определенных его дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="4fd3d-138">At compile time, compiler tools search only the library designated by the `<Library>` element for program elements identified by its child elements.</span></span> <span data-ttu-id="4fd3d-139">В отличие от этого, средства компилятора выполняют поиск всех библиотек, including.NET Framework Core Library, для программных элементов, идентифицируемых дочерними элементами [\<Application>](application-element-net-native.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="4fd3d-139">In contrast, compiler tools search all libraries, including.NET Framework core libraries, for program elements identified by child elements of the [\<Application>](application-element-net-native.md) element.</span></span>  
  
 <span data-ttu-id="4fd3d-140">Директивы `<Library>` могут использоваться условно.</span><span class="sxs-lookup"><span data-stu-id="4fd3d-140">`<Library>` directives may be conditionally utilized.</span></span> <span data-ttu-id="4fd3d-141">Если имя `<Library>` элемента начинается и заканчивается звездочкой ( \* ), `<Library>` директива действует только в том случае, если приложение ссылается на сборку, указанную между звездочками.</span><span class="sxs-lookup"><span data-stu-id="4fd3d-141">If the name of the `<Library>` element starts and ends with an asterisk (\*), the `<Library>` directive has an effect only if the assembly specified between the asterisks is referenced by the app.</span></span> <span data-ttu-id="4fd3d-142">Например, следующая директива среды выполнения применяется только в том случае, если приложение ссылается на Utilities.dll сборку.</span><span class="sxs-lookup"><span data-stu-id="4fd3d-142">For example, the following runtime directive applies only if the Utilities.dll assembly is referenced by the app.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4fd3d-143">См. также</span><span class="sxs-lookup"><span data-stu-id="4fd3d-143">See also</span></span>

- [<span data-ttu-id="4fd3d-144">\<Application> Элемент</span><span class="sxs-lookup"><span data-stu-id="4fd3d-144">\<Application> Element</span></span>](application-element-net-native.md)
- [<span data-ttu-id="4fd3d-145">\<Directives> Элемент</span><span class="sxs-lookup"><span data-stu-id="4fd3d-145">\<Directives> Element</span></span>](directives-element-net-native.md)
- [<span data-ttu-id="4fd3d-146">Ссылка на файл конфигурации директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="4fd3d-146">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="4fd3d-147">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="4fd3d-147">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
