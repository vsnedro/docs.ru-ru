---
title: <Parameter>Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: 22aaa1f3-596f-4733-93db-f4bcabcb5240
ms.openlocfilehash: c6dfc347d44a794ee8496c45ca879f9daab12b22
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128196"
---
# <a name="parameter-element-net-native"></a><span data-ttu-id="2ec2d-102">\<Parameter>Элемент (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="2ec2d-102">\<Parameter> Element (.NET Native)</span></span>
<span data-ttu-id="2ec2d-103">Применяет политику отражения к типу аргумента, переданного методу.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-103">Applies reflection policy to the type of the argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ec2d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ec2d-104">Syntax</span></span>  
  
```xml  
<Parameter Name="parameter_name"  
           Activate="policy_type"  
           Browse="policy_type"  
           Dynamic="policy_type"  
           Serialize="policy_type"  
           DataContractSerializer="policy_type"  
           DataContractJsonSerializer="policy_type"  
           XmlSerializer="policy_type"  
           MarshalObject="policy_type"  
           MarshalDelegate="policy_type"  
           MarshalStructure="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ec2d-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2ec2d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="2ec2d-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ec2d-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2ec2d-107">Attributes</span></span>  
  
|<span data-ttu-id="2ec2d-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2ec2d-108">Attribute</span></span>|<span data-ttu-id="2ec2d-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="2ec2d-109">Attribute type</span></span>|<span data-ttu-id="2ec2d-110">Описание</span><span class="sxs-lookup"><span data-stu-id="2ec2d-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="2ec2d-111">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="2ec2d-111">General</span></span>|<span data-ttu-id="2ec2d-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-112">Required attribute.</span></span> <span data-ttu-id="2ec2d-113">Имя параметра.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-113">The parameter name.</span></span> <span data-ttu-id="2ec2d-114">Например, сигнатура метода `String.CompareTo(Object value)`, значение `Name` — атрибут «value».</span><span class="sxs-lookup"><span data-stu-id="2ec2d-114">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
|`Activate`|<span data-ttu-id="2ec2d-115">Отражение</span><span class="sxs-lookup"><span data-stu-id="2ec2d-115">Reflection</span></span>|<span data-ttu-id="2ec2d-116">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-116">Optional attribute.</span></span> <span data-ttu-id="2ec2d-117">Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="2ec2d-118">Отражение</span><span class="sxs-lookup"><span data-stu-id="2ec2d-118">Reflection</span></span>|<span data-ttu-id="2ec2d-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-119">Optional attribute.</span></span> <span data-ttu-id="2ec2d-120">Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="2ec2d-121">Отражение</span><span class="sxs-lookup"><span data-stu-id="2ec2d-121">Reflection</span></span>|<span data-ttu-id="2ec2d-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-122">Optional attribute.</span></span> <span data-ttu-id="2ec2d-123">Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="2ec2d-124">Сериализация</span><span class="sxs-lookup"><span data-stu-id="2ec2d-124">Serialization</span></span>|<span data-ttu-id="2ec2d-125">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-125">Optional attribute.</span></span> <span data-ttu-id="2ec2d-126">Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="2ec2d-127">Сериализация</span><span class="sxs-lookup"><span data-stu-id="2ec2d-127">Serialization</span></span>|<span data-ttu-id="2ec2d-128">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-128">Optional attribute.</span></span> <span data-ttu-id="2ec2d-129">Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="2ec2d-130">Сериализация</span><span class="sxs-lookup"><span data-stu-id="2ec2d-130">Serialization</span></span>|<span data-ttu-id="2ec2d-131">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-131">Optional attribute.</span></span> <span data-ttu-id="2ec2d-132">Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="2ec2d-133">Сериализация</span><span class="sxs-lookup"><span data-stu-id="2ec2d-133">Serialization</span></span>|<span data-ttu-id="2ec2d-134">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-134">Optional attribute.</span></span> <span data-ttu-id="2ec2d-135">Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="2ec2d-136">Interop</span><span class="sxs-lookup"><span data-stu-id="2ec2d-136">Interop</span></span>|<span data-ttu-id="2ec2d-137">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-137">Optional attribute.</span></span> <span data-ttu-id="2ec2d-138">Определяет политику для маршалинга ссылочных типов в WinRT и COM.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-138">Controls policy for marshaling reference types to WinRT and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="2ec2d-139">Interop</span><span class="sxs-lookup"><span data-stu-id="2ec2d-139">Interop</span></span>|<span data-ttu-id="2ec2d-140">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-140">Optional attribute.</span></span> <span data-ttu-id="2ec2d-141">Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="2ec2d-142">Interop</span><span class="sxs-lookup"><span data-stu-id="2ec2d-142">Interop</span></span>|<span data-ttu-id="2ec2d-143">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-143">Optional attribute.</span></span> <span data-ttu-id="2ec2d-144">Определяет политики для маршалинга типов значений в машинный код.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="2ec2d-145">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="2ec2d-145">Name attribute</span></span>  
  
|<span data-ttu-id="2ec2d-146">Значение</span><span class="sxs-lookup"><span data-stu-id="2ec2d-146">Value</span></span>|<span data-ttu-id="2ec2d-147">Описание:</span><span class="sxs-lookup"><span data-stu-id="2ec2d-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2ec2d-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="2ec2d-148">*parameter_name*</span></span>|<span data-ttu-id="2ec2d-149">Имя параметра метода, к которому применяется политика.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-149">The name of the method parameter to which policy is applied.</span></span> <span data-ttu-id="2ec2d-150">Например, сигнатура метода `String.CompareTo(Object value)`, значение `Name` — атрибут «value».</span><span class="sxs-lookup"><span data-stu-id="2ec2d-150">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="2ec2d-151">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="2ec2d-151">All other attributes</span></span>  
  
|<span data-ttu-id="2ec2d-152">Значение</span><span class="sxs-lookup"><span data-stu-id="2ec2d-152">Value</span></span>|<span data-ttu-id="2ec2d-153">Описание:</span><span class="sxs-lookup"><span data-stu-id="2ec2d-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2ec2d-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="2ec2d-154">*policy_setting*</span></span>|<span data-ttu-id="2ec2d-155">Параметр, применяемый для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="2ec2d-156">Допустимые значения: `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="2ec2d-157">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="2ec2d-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ec2d-158">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2ec2d-158">Child Elements</span></span>  
 <span data-ttu-id="2ec2d-159">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ec2d-160">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2ec2d-160">Parent Elements</span></span>  
  
|<span data-ttu-id="2ec2d-161">Элемент</span><span class="sxs-lookup"><span data-stu-id="2ec2d-161">Element</span></span>|<span data-ttu-id="2ec2d-162">Описание</span><span class="sxs-lookup"><span data-stu-id="2ec2d-162">Description</span></span>|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="2ec2d-163">Применяет политику отражения среды выполнения к конструктору или методу.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-163">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ec2d-164">Примечания</span><span class="sxs-lookup"><span data-stu-id="2ec2d-164">Remarks</span></span>  
 <span data-ttu-id="2ec2d-165">`<Parameter>`Элемент является дочерним по отношению к [\<Method>](method-element-net-native.md) элементу и используется для применения политики к конкретному параметру метода.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-165">The `<Parameter>` element is a child of the [\<Method>](method-element-net-native.md) element and is used to apply policy to a particular method parameter.</span></span> <span data-ttu-id="2ec2d-166">Конкретный параметр метода указывается по имени, а не по типу.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-166">The specific method parameter is specified by name rather than by type.</span></span> <span data-ttu-id="2ec2d-167">По крайней мере один атрибут, который представляет тип политики, такие как `Activate` или `Dynamic`, должен присутствовать.</span><span class="sxs-lookup"><span data-stu-id="2ec2d-167">At least one attribute that represents a policy type, such as `Activate` or `Dynamic`, must be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ec2d-168">См. также</span><span class="sxs-lookup"><span data-stu-id="2ec2d-168">See also</span></span>

- [<span data-ttu-id="2ec2d-169">\<Method>Дерев</span><span class="sxs-lookup"><span data-stu-id="2ec2d-169">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="2ec2d-170">Ссылка на файл конфигурации директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="2ec2d-170">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="2ec2d-171">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="2ec2d-171">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="2ec2d-172">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="2ec2d-172">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
