---
title: <AttributeImplies>Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: 82db7193-a860-418b-84fc-fff2fdf2e025
ms.openlocfilehash: 2ab1fdc71bc43f61f69a0d9b7bea7acb35e14ea5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79181065"
---
# <a name="attributeimplies-element-net-native"></a><span data-ttu-id="895d3-102">\<AttributeImplies>Элемент (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="895d3-102">\<AttributeImplies> Element (.NET Native)</span></span>
<span data-ttu-id="895d3-103">Определяет политики для элементов кода, к которым применяется содержащий атрибут.</span><span class="sxs-lookup"><span data-stu-id="895d3-103">Defines policy for code elements the containing attribute is applied to.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="895d3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="895d3-104">Syntax</span></span>  
  
```xml  
<AttributeImplies Activate="policy_type"  
                  Browse="policy_type"  
                  Dynamic="policy_type"  
                  Serialize="policy_type"
                  DataContractSerializer="policy_setting"  
                  DataContractJsonSerializer="policy_setting"  
                  XmlSerializer="policy_setting"  
                  MarshalObject="policy_setting"  
                  MarshalDelegate="policy_setting"  
                  MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="895d3-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="895d3-105">Attributes and Elements</span></span>  
 <span data-ttu-id="895d3-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="895d3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="895d3-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="895d3-107">Attributes</span></span>  
  
|<span data-ttu-id="895d3-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="895d3-108">Attribute</span></span>|<span data-ttu-id="895d3-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="895d3-109">Attribute type</span></span>|<span data-ttu-id="895d3-110">Описание</span><span class="sxs-lookup"><span data-stu-id="895d3-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Activate`|<span data-ttu-id="895d3-111">Отражение</span><span class="sxs-lookup"><span data-stu-id="895d3-111">Reflection</span></span>|<span data-ttu-id="895d3-112">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="895d3-112">Optional attribute.</span></span> <span data-ttu-id="895d3-113">Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.</span><span class="sxs-lookup"><span data-stu-id="895d3-113">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="895d3-114">Отражение</span><span class="sxs-lookup"><span data-stu-id="895d3-114">Reflection</span></span>|<span data-ttu-id="895d3-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="895d3-115">Optional attribute.</span></span> <span data-ttu-id="895d3-116">Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="895d3-116">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="895d3-117">Отражение</span><span class="sxs-lookup"><span data-stu-id="895d3-117">Reflection</span></span>|<span data-ttu-id="895d3-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="895d3-118">Optional attribute.</span></span> <span data-ttu-id="895d3-119">Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="895d3-119">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="895d3-120">Сериализация</span><span class="sxs-lookup"><span data-stu-id="895d3-120">Serialization</span></span>|<span data-ttu-id="895d3-121">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="895d3-121">Optional attribute.</span></span> <span data-ttu-id="895d3-122">Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="895d3-122">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="895d3-123">Сериализация</span><span class="sxs-lookup"><span data-stu-id="895d3-123">Serialization</span></span>|<span data-ttu-id="895d3-124">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="895d3-124">Optional attribute.</span></span> <span data-ttu-id="895d3-125">Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="895d3-125">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="895d3-126">Сериализация</span><span class="sxs-lookup"><span data-stu-id="895d3-126">Serialization</span></span>|<span data-ttu-id="895d3-127">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="895d3-127">Optional attribute.</span></span> <span data-ttu-id="895d3-128">Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="895d3-128">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="895d3-129">Сериализация</span><span class="sxs-lookup"><span data-stu-id="895d3-129">Serialization</span></span>|<span data-ttu-id="895d3-130">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="895d3-130">Optional attribute.</span></span> <span data-ttu-id="895d3-131">Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="895d3-131">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="895d3-132">Interop</span><span class="sxs-lookup"><span data-stu-id="895d3-132">Interop</span></span>|<span data-ttu-id="895d3-133">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="895d3-133">Optional attribute.</span></span> <span data-ttu-id="895d3-134">Определяет политику для маршалинга ссылочных типов в среды выполнения Windows и COM.</span><span class="sxs-lookup"><span data-stu-id="895d3-134">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="895d3-135">Interop</span><span class="sxs-lookup"><span data-stu-id="895d3-135">Interop</span></span>|<span data-ttu-id="895d3-136">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="895d3-136">Optional attribute.</span></span> <span data-ttu-id="895d3-137">Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.</span><span class="sxs-lookup"><span data-stu-id="895d3-137">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="895d3-138">Interop</span><span class="sxs-lookup"><span data-stu-id="895d3-138">Interop</span></span>|<span data-ttu-id="895d3-139">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="895d3-139">Optional attribute.</span></span> <span data-ttu-id="895d3-140">Определяет политики для маршалинга типов значений в машинный код.</span><span class="sxs-lookup"><span data-stu-id="895d3-140">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="all-attributes"></a><span data-ttu-id="895d3-141">Все атрибуты</span><span class="sxs-lookup"><span data-stu-id="895d3-141">All attributes</span></span>  
  
|<span data-ttu-id="895d3-142">Значение</span><span class="sxs-lookup"><span data-stu-id="895d3-142">Value</span></span>|<span data-ttu-id="895d3-143">Описание:</span><span class="sxs-lookup"><span data-stu-id="895d3-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="895d3-144">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="895d3-144">*policy_setting*</span></span>|<span data-ttu-id="895d3-145">Параметр, применяемый для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="895d3-145">The setting to apply to this policy type.</span></span> <span data-ttu-id="895d3-146">Допустимые значения `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`.</span><span class="sxs-lookup"><span data-stu-id="895d3-146">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="895d3-147">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="895d3-147">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="895d3-148">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="895d3-148">Child Elements</span></span>  
 <span data-ttu-id="895d3-149">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="895d3-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="895d3-150">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="895d3-150">Parent Elements</span></span>  
  
|<span data-ttu-id="895d3-151">Элемент</span><span class="sxs-lookup"><span data-stu-id="895d3-151">Element</span></span>|<span data-ttu-id="895d3-152">Описание</span><span class="sxs-lookup"><span data-stu-id="895d3-152">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="895d3-153">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="895d3-153">Applies reflection policy to a type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="895d3-154">Примечания</span><span class="sxs-lookup"><span data-stu-id="895d3-154">Remarks</span></span>  
 <span data-ttu-id="895d3-155">Элемент `<AttributeImplies>` используется в том случае, если его содержащий тип является атрибутом (то есть классом, производным от <xref:System.Attribute?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="895d3-155">The `<AttributeImplies>` element is used if its containing type is an attribute (that is, a class derived from <xref:System.Attribute?displayProperty=nameWithType>).</span></span> <span data-ttu-id="895d3-156">Если атрибут применяется к элементу определенной программы, политика, определенная элементом `<AttributeImplies>`, применяется к этому элементу программы.</span><span class="sxs-lookup"><span data-stu-id="895d3-156">If the attribute is applied to a particular program element, the policy defined by the `<AttributeImplies>` element applies to that program element.</span></span>  
  
 <span data-ttu-id="895d3-157">Атрибуты отражения, сериализации и взаимодействия необязательны, несмотря на то, что по крайней мере один из них должен присутствовать.</span><span class="sxs-lookup"><span data-stu-id="895d3-157">The reflection, serialization, and interop attributes are all optional, although at least one should be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="895d3-158">См. также</span><span class="sxs-lookup"><span data-stu-id="895d3-158">See also</span></span>

- [<span data-ttu-id="895d3-159">\<Type>Дерев</span><span class="sxs-lookup"><span data-stu-id="895d3-159">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="895d3-160">Ссылка на файл конфигурации директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="895d3-160">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="895d3-161">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="895d3-161">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="895d3-162">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="895d3-162">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
