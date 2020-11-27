---
title: <TypeParameter> Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: d37bb1b7-1ddc-4c6d-8ecf-583f804a2479
ms.openlocfilehash: dc04115914b7571b677c6d069d2d4b820b895d59
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287674"
---
# <a name="typeparameter-element-net-native"></a><span data-ttu-id="b6cb1-102">\<TypeParameter> Элемент (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="b6cb1-102">\<TypeParameter> Element (.NET Native)</span></span>

<span data-ttu-id="b6cb1-103">Применяет политику к типу, представленному аргументом типа , переданным методу.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-103">Applies policy to the type represented by a Type argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6cb1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6cb1-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6cb1-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b6cb1-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b6cb1-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6cb1-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b6cb1-107">Attributes</span></span>  
  
|<span data-ttu-id="b6cb1-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b6cb1-108">Attribute</span></span>|<span data-ttu-id="b6cb1-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="b6cb1-109">Attribute type</span></span>|<span data-ttu-id="b6cb1-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b6cb1-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="b6cb1-111">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="b6cb1-111">General</span></span>|<span data-ttu-id="b6cb1-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-112">Required attribute.</span></span> <span data-ttu-id="b6cb1-113">Имя типа параметра типа <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-113">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="b6cb1-114">Например, для сигнатуры метода `Type.GetInterfaceMap(Type interfaceType)`, значение атрибута `Name` — "interfaceType".</span><span class="sxs-lookup"><span data-stu-id="b6cb1-114">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
|`Activate`|<span data-ttu-id="b6cb1-115">Отражение</span><span class="sxs-lookup"><span data-stu-id="b6cb1-115">Reflection</span></span>|<span data-ttu-id="b6cb1-116">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-116">Optional attribute.</span></span> <span data-ttu-id="b6cb1-117">Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="b6cb1-118">Отражение</span><span class="sxs-lookup"><span data-stu-id="b6cb1-118">Reflection</span></span>|<span data-ttu-id="b6cb1-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-119">Optional attribute.</span></span> <span data-ttu-id="b6cb1-120">Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="b6cb1-121">Отражение</span><span class="sxs-lookup"><span data-stu-id="b6cb1-121">Reflection</span></span>|<span data-ttu-id="b6cb1-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-122">Optional attribute.</span></span> <span data-ttu-id="b6cb1-123">Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="b6cb1-124">Сериализация</span><span class="sxs-lookup"><span data-stu-id="b6cb1-124">Serialization</span></span>|<span data-ttu-id="b6cb1-125">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-125">Optional attribute.</span></span> <span data-ttu-id="b6cb1-126">Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="b6cb1-127">Сериализация</span><span class="sxs-lookup"><span data-stu-id="b6cb1-127">Serialization</span></span>|<span data-ttu-id="b6cb1-128">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-128">Optional attribute.</span></span> <span data-ttu-id="b6cb1-129">Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="b6cb1-130">Сериализация</span><span class="sxs-lookup"><span data-stu-id="b6cb1-130">Serialization</span></span>|<span data-ttu-id="b6cb1-131">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-131">Optional attribute.</span></span> <span data-ttu-id="b6cb1-132">Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="b6cb1-133">Сериализация</span><span class="sxs-lookup"><span data-stu-id="b6cb1-133">Serialization</span></span>|<span data-ttu-id="b6cb1-134">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-134">Optional attribute.</span></span> <span data-ttu-id="b6cb1-135">Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="b6cb1-136">Interop</span><span class="sxs-lookup"><span data-stu-id="b6cb1-136">Interop</span></span>|<span data-ttu-id="b6cb1-137">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-137">Optional attribute.</span></span> <span data-ttu-id="b6cb1-138">Определяет политику для маршалинга ссылочных типов в среды выполнения Windows и COM.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="b6cb1-139">Interop</span><span class="sxs-lookup"><span data-stu-id="b6cb1-139">Interop</span></span>|<span data-ttu-id="b6cb1-140">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-140">Optional attribute.</span></span> <span data-ttu-id="b6cb1-141">Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="b6cb1-142">Interop</span><span class="sxs-lookup"><span data-stu-id="b6cb1-142">Interop</span></span>|<span data-ttu-id="b6cb1-143">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-143">Optional attribute.</span></span> <span data-ttu-id="b6cb1-144">Определяет политики для маршалинга типов значений в машинный код.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="b6cb1-145">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="b6cb1-145">Name attribute</span></span>  
  
|<span data-ttu-id="b6cb1-146">Значение</span><span class="sxs-lookup"><span data-stu-id="b6cb1-146">Value</span></span>|<span data-ttu-id="b6cb1-147">Описание</span><span class="sxs-lookup"><span data-stu-id="b6cb1-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b6cb1-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="b6cb1-148">*parameter_name*</span></span>|<span data-ttu-id="b6cb1-149">Имя типа параметра типа <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-149">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="b6cb1-150">Например, для сигнатуры метода `Type.GetInterfaceMap(Type interfaceType)`, значение атрибута `Name` — "interfaceType".</span><span class="sxs-lookup"><span data-stu-id="b6cb1-150">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="b6cb1-151">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="b6cb1-151">All other attributes</span></span>  
  
|<span data-ttu-id="b6cb1-152">Значение</span><span class="sxs-lookup"><span data-stu-id="b6cb1-152">Value</span></span>|<span data-ttu-id="b6cb1-153">Описание</span><span class="sxs-lookup"><span data-stu-id="b6cb1-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b6cb1-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="b6cb1-154">*policy_setting*</span></span>|<span data-ttu-id="b6cb1-155">Параметр, применяемый для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="b6cb1-156">Допустимые значения: `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="b6cb1-157">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="b6cb1-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6cb1-158">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b6cb1-158">Child Elements</span></span>  

 <span data-ttu-id="b6cb1-159">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b6cb1-160">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b6cb1-160">Parent Elements</span></span>  
  
|<span data-ttu-id="b6cb1-161">Элемент</span><span class="sxs-lookup"><span data-stu-id="b6cb1-161">Element</span></span>|<span data-ttu-id="b6cb1-162">Описание</span><span class="sxs-lookup"><span data-stu-id="b6cb1-162">Description</span></span>|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="b6cb1-163">Применяет политику отражения среды выполнения к конструктору или методу.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-163">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6cb1-164">Примечания</span><span class="sxs-lookup"><span data-stu-id="b6cb1-164">Remarks</span></span>  

 <span data-ttu-id="b6cb1-165">`<TypeParameter>`Элемент аналогичен [\<Parameter>](parameter-element-net-native.md) элементу, за исключением того, что он может применяться только к параметрам типа <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="b6cb1-165">The `<TypeParameter>` element is similar to the [\<Parameter>](parameter-element-net-native.md) element, except that it can be applied only to parameters of type <xref:System.Type>.</span></span> <span data-ttu-id="b6cb1-166">Применяет политику, независимо от представленного типа во время выполнения по аргументу типа, указанному атрибутом `Name`.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-166">It applies policy to whatever type is represented at run time by the type argument specified by the `Name` attribute.</span></span>  
  
 <span data-ttu-id="b6cb1-167">Например, сериализатор NewtonSoft JSON включает статический метод `JsonConvert.DeserializeObject(String value, Type type)`.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-167">For example, the NewtonSoft JSON serializer includes a static `JsonConvert.DeserializeObject(String value, Type type)` method.</span></span> <span data-ttu-id="b6cb1-168">Следующие директивы отражения:</span><span class="sxs-lookup"><span data-stu-id="b6cb1-168">The following reflection directives:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject">  
         <GenericParameter Name="type" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
 <span data-ttu-id="b6cb1-169">определяют, что метаданные для типа среды выполнения, представленные аргументом `type`, должны быть доступны для сериализации.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-169">specify that metadata for the runtime type represented by the `type` argument should be made available for serialization.</span></span> <span data-ttu-id="b6cb1-170">Если применить эти директивы среды выполнения к проекту, который включает следующий исходный код:</span><span class="sxs-lookup"><span data-stu-id="b6cb1-170">If these runtime directives apply to a project that includes the following source code:</span></span>  
  
```csharp  
Type t = typeof(StockQuote);  
Object obj = JsonConvert.DeserializeObject(data, t);  
```  
  
 <span data-ttu-id="b6cb1-171">директивы отражения делают метаданные для типа `StockQuote` доступными для сериализатора NewtonSoft JSON во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b6cb1-171">the reflection directives make metadata for the `StockQuote` type available for the NewtonSoft JSON serializer at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6cb1-172">См. также</span><span class="sxs-lookup"><span data-stu-id="b6cb1-172">See also</span></span>

- [<span data-ttu-id="b6cb1-173">\<Method> Элемент</span><span class="sxs-lookup"><span data-stu-id="b6cb1-173">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="b6cb1-174">Ссылка на файл конфигурации директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="b6cb1-174">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="b6cb1-175">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="b6cb1-175">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="b6cb1-176">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="b6cb1-176">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
