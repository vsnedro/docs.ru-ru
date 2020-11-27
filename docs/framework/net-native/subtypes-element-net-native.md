---
title: <Subtypes> Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: fb854070-248b-46cf-9dab-c322e2b4d624
ms.openlocfilehash: 7484152c351f59ee84b601584bd84347186628a3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287817"
---
# <a name="subtypes-element-net-native"></a><span data-ttu-id="91b32-102">\<Subtypes> Элемент (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="91b32-102">\<Subtypes> Element (.NET Native)</span></span>

<span data-ttu-id="91b32-103">Применяет политику среды выполнения для всех классов, унаследованных из содержащего типа.</span><span class="sxs-lookup"><span data-stu-id="91b32-103">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91b32-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="91b32-104">Syntax</span></span>  
  
```xml  
<Subtypes Activate="policy_type"  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91b32-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="91b32-105">Attributes and Elements</span></span>  

 <span data-ttu-id="91b32-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="91b32-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91b32-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="91b32-107">Attributes</span></span>  
  
|<span data-ttu-id="91b32-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="91b32-108">Attribute</span></span>|<span data-ttu-id="91b32-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="91b32-109">Attribute type</span></span>|<span data-ttu-id="91b32-110">Описание</span><span class="sxs-lookup"><span data-stu-id="91b32-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Activate`|<span data-ttu-id="91b32-111">Отражение</span><span class="sxs-lookup"><span data-stu-id="91b32-111">Reflection</span></span>|<span data-ttu-id="91b32-112">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="91b32-112">Optional attribute.</span></span> <span data-ttu-id="91b32-113">Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.</span><span class="sxs-lookup"><span data-stu-id="91b32-113">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="91b32-114">Отражение</span><span class="sxs-lookup"><span data-stu-id="91b32-114">Reflection</span></span>|<span data-ttu-id="91b32-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="91b32-115">Optional attribute.</span></span> <span data-ttu-id="91b32-116">Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="91b32-116">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="91b32-117">Отражение</span><span class="sxs-lookup"><span data-stu-id="91b32-117">Reflection</span></span>|<span data-ttu-id="91b32-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="91b32-118">Optional attribute.</span></span> <span data-ttu-id="91b32-119">Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="91b32-119">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="91b32-120">Сериализация</span><span class="sxs-lookup"><span data-stu-id="91b32-120">Serialization</span></span>|<span data-ttu-id="91b32-121">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="91b32-121">Optional attribute.</span></span> <span data-ttu-id="91b32-122">Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="91b32-122">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="91b32-123">Сериализация</span><span class="sxs-lookup"><span data-stu-id="91b32-123">Serialization</span></span>|<span data-ttu-id="91b32-124">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="91b32-124">Optional attribute.</span></span> <span data-ttu-id="91b32-125">Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="91b32-125">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="91b32-126">Сериализация</span><span class="sxs-lookup"><span data-stu-id="91b32-126">Serialization</span></span>|<span data-ttu-id="91b32-127">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="91b32-127">Optional attribute.</span></span> <span data-ttu-id="91b32-128">Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="91b32-128">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="91b32-129">Сериализация</span><span class="sxs-lookup"><span data-stu-id="91b32-129">Serialization</span></span>|<span data-ttu-id="91b32-130">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="91b32-130">Optional attribute.</span></span> <span data-ttu-id="91b32-131">Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="91b32-131">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="91b32-132">Interop</span><span class="sxs-lookup"><span data-stu-id="91b32-132">Interop</span></span>|<span data-ttu-id="91b32-133">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="91b32-133">Optional attribute.</span></span> <span data-ttu-id="91b32-134">Определяет политику для маршалинга ссылочных типов в среды выполнения Windows и COM.</span><span class="sxs-lookup"><span data-stu-id="91b32-134">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="91b32-135">Interop</span><span class="sxs-lookup"><span data-stu-id="91b32-135">Interop</span></span>|<span data-ttu-id="91b32-136">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="91b32-136">Optional attribute.</span></span> <span data-ttu-id="91b32-137">Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.</span><span class="sxs-lookup"><span data-stu-id="91b32-137">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="91b32-138">Interop</span><span class="sxs-lookup"><span data-stu-id="91b32-138">Interop</span></span>|<span data-ttu-id="91b32-139">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="91b32-139">Optional attribute.</span></span> <span data-ttu-id="91b32-140">Определяет политики для маршалинга типов значений в машинный код.</span><span class="sxs-lookup"><span data-stu-id="91b32-140">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="all-attributes"></a><span data-ttu-id="91b32-141">Все атрибуты</span><span class="sxs-lookup"><span data-stu-id="91b32-141">All attributes</span></span>  
  
|<span data-ttu-id="91b32-142">Значение</span><span class="sxs-lookup"><span data-stu-id="91b32-142">Value</span></span>|<span data-ttu-id="91b32-143">Описание</span><span class="sxs-lookup"><span data-stu-id="91b32-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="91b32-144">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="91b32-144">*policy_setting*</span></span>|<span data-ttu-id="91b32-145">Параметр, применяемый для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="91b32-145">The setting to apply to this policy type.</span></span> <span data-ttu-id="91b32-146">Допустимые значения `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`.</span><span class="sxs-lookup"><span data-stu-id="91b32-146">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="91b32-147">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="91b32-147">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91b32-148">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="91b32-148">Child Elements</span></span>  

 <span data-ttu-id="91b32-149">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="91b32-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91b32-150">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="91b32-150">Parent Elements</span></span>  
  
|<span data-ttu-id="91b32-151">Элемент</span><span class="sxs-lookup"><span data-stu-id="91b32-151">Element</span></span>|<span data-ttu-id="91b32-152">Описание</span><span class="sxs-lookup"><span data-stu-id="91b32-152">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="91b32-153">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="91b32-153">Applies reflection policy to a type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91b32-154">Примечания</span><span class="sxs-lookup"><span data-stu-id="91b32-154">Remarks</span></span>  

 <span data-ttu-id="91b32-155">Элемент `<Subtypes>` применяет политику ко всем подтипам его содержащего типа.</span><span class="sxs-lookup"><span data-stu-id="91b32-155">The `<Subtypes>` element applies policy to all the subtypes of its containing type.</span></span> <span data-ttu-id="91b32-156">Используется для применения различных политик для производных типов и их базовых классов.</span><span class="sxs-lookup"><span data-stu-id="91b32-156">You use it when you want to apply different policies to derived types and their base classes.</span></span>  
  
 <span data-ttu-id="91b32-157">Атрибуты отражения, сериализации и взаимодействия необязательны, несмотря на то, что по крайней мере один из них должен присутствовать.</span><span class="sxs-lookup"><span data-stu-id="91b32-157">The reflection, serialization, and interop attributes are all optional, although at least one should be present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91b32-158">Пример</span><span class="sxs-lookup"><span data-stu-id="91b32-158">Example</span></span>  

 <span data-ttu-id="91b32-159">В следующем примере определяется класс с именем `BaseClass` и подкласс с именем `Derived1`.</span><span class="sxs-lookup"><span data-stu-id="91b32-159">The following example defines a class named `BaseClass` and a subclass named `Derived1`.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#4](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/subtypes.cs#4)]  
  
 <span data-ttu-id="91b32-160">Как показано в следующем коде, файл директив среды выполнения явно задает политики `Dynamic` и `Activate` для `BaseClass` в `Excluded`.</span><span class="sxs-lookup"><span data-stu-id="91b32-160">As shown in the following code, the runtime directives file explicitly sets the `Dynamic` and `Activate` policies for `BaseClass` to `Excluded`.</span></span> <span data-ttu-id="91b32-161">Из-за этого, объекты типа `BaseClass` не могут использоваться для динамического создания экземпляров или создания путем вызовов конструктора класса `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="91b32-161">Because of this, objects of type `BaseClass` cannot be instantiated dynamically or by calls to the `BaseClass` class constructor.</span></span> <span data-ttu-id="91b32-162">Тем не менее, элемент `<Subtypes>` допускает использование классов, производных от `BaseClass`, для динамического создания экземпляров, а также для создания с помощью вызовов их конструкторов класса.</span><span class="sxs-lookup"><span data-stu-id="91b32-162">However, the `<Subtypes>` element allows classes derived from `BaseClass` to be instantiated dynamically and through calls to their class constructors.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
   <Assembly Name="*Application*" Dynamic="Required All" />  
     <Type Name="Examples.Libraries.BaseClass" Activate ="Excluded" Dynamic="Excluded" >  
        <Subtypes Activate="Public" Dynamic ="Public"/>  
     </Type>  
  </Application>  
</Directives>  
```  
  
 <span data-ttu-id="91b32-163">Благодаря директиве `<Subtypes>`, следующий код, динамически создающий экземпляр `Derived1` экземпляр путем вызова метода <xref:System.Activator.CreateInstance%28System.Type%29?displayProperty=nameWithType>, выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="91b32-163">Because of the `<Subtypes>` directive, the following code that instantiates a `Derived1` instance dynamically by calling the <xref:System.Activator.CreateInstance%28System.Type%29?displayProperty=nameWithType> method executes successfully.</span></span>  <span data-ttu-id="91b32-164">Здесь переменная блока представляет объект <xref:System.Windows.Controls.TextBlock> в пустом приложении для магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="91b32-164">The block variable here is a <xref:System.Windows.Controls.TextBlock> object in a blank Windows Store app.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/subtypes.cs#5)]  
  
## <a name="see-also"></a><span data-ttu-id="91b32-165">См. также</span><span class="sxs-lookup"><span data-stu-id="91b32-165">See also</span></span>

- [<span data-ttu-id="91b32-166">\<Type> Элемент</span><span class="sxs-lookup"><span data-stu-id="91b32-166">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="91b32-167">Ссылка на файл конфигурации директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="91b32-167">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="91b32-168">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="91b32-168">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="91b32-169">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="91b32-169">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
