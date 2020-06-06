---
title: <GenericParameter>Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
ms.openlocfilehash: d0b18211206a8f9d4365ab3affe6d1c376003348
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128432"
---
# <a name="genericparameter-element-net-native"></a><span data-ttu-id="838e2-102">\<GenericParameter>Элемент (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="838e2-102">\<GenericParameter> Element (.NET Native)</span></span>
<span data-ttu-id="838e2-103">Применяет политику к параметру типа универсального типа или метода.</span><span class="sxs-lookup"><span data-stu-id="838e2-103">Applies policy to the parameter type of a generic type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="838e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="838e2-104">Syntax</span></span>  
  
```xml  
<GenericParameter Name="generic_parameter_name"  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="838e2-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="838e2-105">Attributes and Elements</span></span>  
 <span data-ttu-id="838e2-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="838e2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="838e2-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="838e2-107">Attributes</span></span>  
  
|<span data-ttu-id="838e2-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="838e2-108">Attribute</span></span>|<span data-ttu-id="838e2-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="838e2-109">Attribute type</span></span>|<span data-ttu-id="838e2-110">Описание</span><span class="sxs-lookup"><span data-stu-id="838e2-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="838e2-111">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="838e2-111">General</span></span>|<span data-ttu-id="838e2-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="838e2-112">Required attribute.</span></span> <span data-ttu-id="838e2-113">Имя универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="838e2-113">The name of the generic parameter.</span></span> <span data-ttu-id="838e2-114">Например, для универсального делегата <xref:System.Func%603>, значение атрибута `Name` равно «TResult» для применения политики среды выполнения к возвращаемому значению делегата.</span><span class="sxs-lookup"><span data-stu-id="838e2-114">For example, for the generic delegate <xref:System.Func%603>, the value of the `Name` attribute is "TResult" to apply runtime policy to the delegate's return value.</span></span>|  
|`Activate`|<span data-ttu-id="838e2-115">Отражение</span><span class="sxs-lookup"><span data-stu-id="838e2-115">Reflection</span></span>|<span data-ttu-id="838e2-116">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="838e2-116">Optional attribute.</span></span> <span data-ttu-id="838e2-117">Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.</span><span class="sxs-lookup"><span data-stu-id="838e2-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="838e2-118">Отражение</span><span class="sxs-lookup"><span data-stu-id="838e2-118">Reflection</span></span>|<span data-ttu-id="838e2-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="838e2-119">Optional attribute.</span></span> <span data-ttu-id="838e2-120">Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="838e2-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="838e2-121">Отражение</span><span class="sxs-lookup"><span data-stu-id="838e2-121">Reflection</span></span>|<span data-ttu-id="838e2-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="838e2-122">Optional attribute.</span></span> <span data-ttu-id="838e2-123">Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="838e2-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="838e2-124">Сериализация</span><span class="sxs-lookup"><span data-stu-id="838e2-124">Serialization</span></span>|<span data-ttu-id="838e2-125">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="838e2-125">Optional attribute.</span></span> <span data-ttu-id="838e2-126">Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="838e2-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="838e2-127">Сериализация</span><span class="sxs-lookup"><span data-stu-id="838e2-127">Serialization</span></span>|<span data-ttu-id="838e2-128">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="838e2-128">Optional attribute.</span></span> <span data-ttu-id="838e2-129">Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="838e2-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="838e2-130">Сериализация</span><span class="sxs-lookup"><span data-stu-id="838e2-130">Serialization</span></span>|<span data-ttu-id="838e2-131">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="838e2-131">Optional attribute.</span></span> <span data-ttu-id="838e2-132">Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="838e2-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="838e2-133">Сериализация</span><span class="sxs-lookup"><span data-stu-id="838e2-133">Serialization</span></span>|<span data-ttu-id="838e2-134">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="838e2-134">Optional attribute.</span></span> <span data-ttu-id="838e2-135">Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="838e2-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="838e2-136">Interop</span><span class="sxs-lookup"><span data-stu-id="838e2-136">Interop</span></span>|<span data-ttu-id="838e2-137">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="838e2-137">Optional attribute.</span></span> <span data-ttu-id="838e2-138">Определяет политику для маршалинга ссылочных типов в среды выполнения Windows и COM.</span><span class="sxs-lookup"><span data-stu-id="838e2-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="838e2-139">Interop</span><span class="sxs-lookup"><span data-stu-id="838e2-139">Interop</span></span>|<span data-ttu-id="838e2-140">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="838e2-140">Optional attribute.</span></span> <span data-ttu-id="838e2-141">Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.</span><span class="sxs-lookup"><span data-stu-id="838e2-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="838e2-142">Interop</span><span class="sxs-lookup"><span data-stu-id="838e2-142">Interop</span></span>|<span data-ttu-id="838e2-143">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="838e2-143">Optional attribute.</span></span> <span data-ttu-id="838e2-144">Определяет политики для маршалинга типов значений в машинный код.</span><span class="sxs-lookup"><span data-stu-id="838e2-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="838e2-145">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="838e2-145">Name attribute</span></span>  
  
|<span data-ttu-id="838e2-146">Значение</span><span class="sxs-lookup"><span data-stu-id="838e2-146">Value</span></span>|<span data-ttu-id="838e2-147">Описание:</span><span class="sxs-lookup"><span data-stu-id="838e2-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="838e2-148">*generic_parameter_name*</span><span class="sxs-lookup"><span data-stu-id="838e2-148">*generic_parameter_name*</span></span>|<span data-ttu-id="838e2-149">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="838e2-149">Required attribute.</span></span> <span data-ttu-id="838e2-150">Имя универсального параметра типа.</span><span class="sxs-lookup"><span data-stu-id="838e2-150">The name of the generic type parameter.</span></span> <span data-ttu-id="838e2-151">Например, для универсального делегата <xref:System.Func%603> значение *generic_parameter_name*, равное "TResult", применяет политику среды выполнения к возвращаемому значению делегата.</span><span class="sxs-lookup"><span data-stu-id="838e2-151">For example, for the generic delegate <xref:System.Func%603>, a *generic_parameter_name* value of "TResult" applies runtime policy to the delegate's return value.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="838e2-152">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="838e2-152">All other attributes</span></span>  
  
|<span data-ttu-id="838e2-153">Значение</span><span class="sxs-lookup"><span data-stu-id="838e2-153">Value</span></span>|<span data-ttu-id="838e2-154">Описание:</span><span class="sxs-lookup"><span data-stu-id="838e2-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="838e2-155">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="838e2-155">*policy_setting*</span></span>|<span data-ttu-id="838e2-156">Параметр, применяемый для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="838e2-156">The setting to apply to this policy type.</span></span> <span data-ttu-id="838e2-157">Допустимые значения: `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`.</span><span class="sxs-lookup"><span data-stu-id="838e2-157">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="838e2-158">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="838e2-158">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="838e2-159">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="838e2-159">Child Elements</span></span>  
 <span data-ttu-id="838e2-160">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="838e2-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="838e2-161">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="838e2-161">Parent Elements</span></span>  
  
|<span data-ttu-id="838e2-162">Элемент</span><span class="sxs-lookup"><span data-stu-id="838e2-162">Element</span></span>|<span data-ttu-id="838e2-163">Описание</span><span class="sxs-lookup"><span data-stu-id="838e2-163">Description</span></span>|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="838e2-164">Применяет политику отражения среды выполнения к конструктору или методу.</span><span class="sxs-lookup"><span data-stu-id="838e2-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="838e2-165">Применяет политику отражения среды выполнения для конкретного типа, например, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="838e2-165">Applies runtime reflection policy to a particular type, such as a class or structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="838e2-166">Примечания</span><span class="sxs-lookup"><span data-stu-id="838e2-166">Remarks</span></span>  
 <span data-ttu-id="838e2-167">`<GenericParameter>`Элемент является дочерним по отношению к [\<Method>](method-element-net-native.md) [\<Type>](type-element-net-native.md) элементу или и используется для применения политики к конкретному параметру универсального типа, который задается его именем в сигнатуре универсального типа или метода.</span><span class="sxs-lookup"><span data-stu-id="838e2-167">The `<GenericParameter>` element is a child of either the [\<Method>](method-element-net-native.md) or [\<Type>](type-element-net-native.md) element and is used to apply policy to a particular generic type parameter, which is specified by its name in the generic type or method signature.</span></span>  
  
 <span data-ttu-id="838e2-168">Элемент `<GenericParameter>` особенно полезен при использовании сериализаторов.</span><span class="sxs-lookup"><span data-stu-id="838e2-168">The `<GenericParameter>` element is most useful when used with serializers.</span></span> <span data-ttu-id="838e2-169">В следующем примере элемент используется `<GenericParameter>` для применения политики к типу `T` при вызове перегрузок метода JsonConvert. методов DeserializeObject сериализатора JSON NewtonSoft [ \<T> (String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) .</span><span class="sxs-lookup"><span data-stu-id="838e2-169">The following example uses the `<GenericParameter>` element to apply policy to the type `T` in calls to the NewtonSoft JSON serializer's [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) method overloads.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="838e2-170">См. также</span><span class="sxs-lookup"><span data-stu-id="838e2-170">See also</span></span>

- [<span data-ttu-id="838e2-171">\<Method>Дерев</span><span class="sxs-lookup"><span data-stu-id="838e2-171">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="838e2-172">\<Type>Дерев</span><span class="sxs-lookup"><span data-stu-id="838e2-172">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="838e2-173">Ссылка на файл конфигурации директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="838e2-173">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="838e2-174">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="838e2-174">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="838e2-175">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="838e2-175">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
