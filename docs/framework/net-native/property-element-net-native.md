---
title: <Property> Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
ms.openlocfilehash: a0bdf95a1d1cadf7423f8c6595add13eda4d0d9a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250857"
---
# <a name="property-element-net-native"></a><span data-ttu-id="762e5-102">\<Property> Элемент (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="762e5-102">\<Property> Element (.NET Native)</span></span>

<span data-ttu-id="762e5-103">Применяет политику отражения среды выполнения к свойству.</span><span class="sxs-lookup"><span data-stu-id="762e5-103">Applies runtime reflection policy to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="762e5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="762e5-104">Syntax</span></span>  
  
```xml  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="762e5-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="762e5-105">Attributes and Elements</span></span>  

 <span data-ttu-id="762e5-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="762e5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="762e5-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="762e5-107">Attributes</span></span>  
  
|<span data-ttu-id="762e5-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="762e5-108">Attribute</span></span>|<span data-ttu-id="762e5-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="762e5-109">Attribute type</span></span>|<span data-ttu-id="762e5-110">Описание</span><span class="sxs-lookup"><span data-stu-id="762e5-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="762e5-111">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="762e5-111">General</span></span>|<span data-ttu-id="762e5-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="762e5-112">Required attribute.</span></span> <span data-ttu-id="762e5-113">Задает имя свойства.</span><span class="sxs-lookup"><span data-stu-id="762e5-113">Specifies the property name.</span></span>|  
|`Browse`|<span data-ttu-id="762e5-114">Отражение</span><span class="sxs-lookup"><span data-stu-id="762e5-114">Reflection</span></span>|<span data-ttu-id="762e5-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="762e5-115">Optional attribute.</span></span> <span data-ttu-id="762e5-116">Определяет запрос для получения сведений о свойстве или перечисляет свойство, но не включает динамический доступ во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="762e5-116">Controls querying for information about or enumerating the property but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="762e5-117">Отражение</span><span class="sxs-lookup"><span data-stu-id="762e5-117">Reflection</span></span>|<span data-ttu-id="762e5-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="762e5-118">Optional attribute.</span></span> <span data-ttu-id="762e5-119">Управляет доступом среды выполнения к свойству для включения динамического программирования.</span><span class="sxs-lookup"><span data-stu-id="762e5-119">Controls runtime access to the property to enable dynamic programming.</span></span> <span data-ttu-id="762e5-120">Эта политика гарантирует, что свойство можно задать или получить динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="762e5-120">This policy ensures that a property can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="762e5-121">Сериализация</span><span class="sxs-lookup"><span data-stu-id="762e5-121">Serialization</span></span>|<span data-ttu-id="762e5-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="762e5-122">Optional attribute.</span></span> <span data-ttu-id="762e5-123">Управляет доступом среды выполнения к свойству, чтобы включить экземпляры типов, предназначенных для сериализации в таких библиотеках, как сериализатор Newtonsoft JSON или для привязки данных.</span><span class="sxs-lookup"><span data-stu-id="762e5-123">Controls runtime access to a property to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="762e5-124">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="762e5-124">Name attribute</span></span>  
  
|<span data-ttu-id="762e5-125">Значение</span><span class="sxs-lookup"><span data-stu-id="762e5-125">Value</span></span>|<span data-ttu-id="762e5-126">Описание</span><span class="sxs-lookup"><span data-stu-id="762e5-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="762e5-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="762e5-127">*method_name*</span></span>|<span data-ttu-id="762e5-128">Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="762e5-128">The property name.</span></span> <span data-ttu-id="762e5-129">Тип свойства определяется родительским [\<Type>](type-element-net-native.md) [\<TypeInstantiation>](typeinstantiation-element-net-native.md) элементом или.</span><span class="sxs-lookup"><span data-stu-id="762e5-129">The type of the property is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="762e5-130">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="762e5-130">All other attributes</span></span>  
  
|<span data-ttu-id="762e5-131">Значение</span><span class="sxs-lookup"><span data-stu-id="762e5-131">Value</span></span>|<span data-ttu-id="762e5-132">Описание</span><span class="sxs-lookup"><span data-stu-id="762e5-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="762e5-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="762e5-133">*policy_setting*</span></span>|<span data-ttu-id="762e5-134">Параметр, применяемый к этому типу политики для свойства.</span><span class="sxs-lookup"><span data-stu-id="762e5-134">The setting to apply to this policy type for the property.</span></span> <span data-ttu-id="762e5-135">Допустимые значения: `Auto`, `Excluded`, `Included` и `Required`.</span><span class="sxs-lookup"><span data-stu-id="762e5-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="762e5-136">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="762e5-136">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="762e5-137">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="762e5-137">Child Elements</span></span>  

 <span data-ttu-id="762e5-138">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="762e5-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="762e5-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="762e5-139">Parent Elements</span></span>  
  
|<span data-ttu-id="762e5-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="762e5-140">Element</span></span>|<span data-ttu-id="762e5-141">Описание</span><span class="sxs-lookup"><span data-stu-id="762e5-141">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="762e5-142">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="762e5-142">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="762e5-143">Применяет политику отражения к сконструированному универсальному типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="762e5-143">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="762e5-144">Примечания</span><span class="sxs-lookup"><span data-stu-id="762e5-144">Remarks</span></span>  

 <span data-ttu-id="762e5-145">Если политика свойства не определена явно, оно наследует политику среды выполнения своего родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="762e5-145">If a property's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="762e5-146">Пример</span><span class="sxs-lookup"><span data-stu-id="762e5-146">Example</span></span>  

 <span data-ttu-id="762e5-147">В следующем примере используется отражение для создания экземпляров объекта `Book` и отображения значений его свойств.</span><span class="sxs-lookup"><span data-stu-id="762e5-147">The following example uses reflection to instantiate a `Book` object and display its property values.</span></span> <span data-ttu-id="762e5-148">Исходный файл default.rd.xml для проекта выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="762e5-148">The original default.rd.xml file for the project appears as follows:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
```  
  
 <span data-ttu-id="762e5-149">Файл применяет значение `All` к политике `Activate` для класса `Book`, который предоставляет доступ к конструкторам класса через отражение.</span><span class="sxs-lookup"><span data-stu-id="762e5-149">The file applies the `All` value to the `Activate` policy for the `Book` class, which allows access to class constructors through reflection.</span></span> <span data-ttu-id="762e5-150">Политика `Browse` для класса `Book` наследуется от его родительского пространства имен.</span><span class="sxs-lookup"><span data-stu-id="762e5-150">The `Browse` policy for the `Book` class is inherited from its parent namespace.</span></span> <span data-ttu-id="762e5-151">Это свойство имеет значение `Required Public`, что делает метаданные доступными во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="762e5-151">This is set to `Required Public`, which makes metadata available at runtime.</span></span>  
  
 <span data-ttu-id="762e5-152">Ниже приведен исходный код для этого примера.</span><span class="sxs-lookup"><span data-stu-id="762e5-152">The following is the source code for the example.</span></span> <span data-ttu-id="762e5-153">`outputBlock`Переменная представляет <xref:Windows.UI.Xaml.Controls.TextBlock> элемент управления.</span><span class="sxs-lookup"><span data-stu-id="762e5-153">The `outputBlock` variable represents a <xref:Windows.UI.Xaml.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 <span data-ttu-id="762e5-154">Тем не менее компиляция и выполнение этого примера создает исключение [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="762e5-154">However, compiling and executing this example throws a [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exception.</span></span> <span data-ttu-id="762e5-155">Несмотря на то, что мы уже сделали метаданные для типа `Book` доступными, нам не удалось обеспечить динамический доступ к реализациям свойств считывания.</span><span class="sxs-lookup"><span data-stu-id="762e5-155">Although we've made metadata for the `Book` type available, we've failed to make the implementations of the property getters available dynamically.</span></span> <span data-ttu-id="762e5-156">Эту ошибку можно исправить одним из двух способов:</span><span class="sxs-lookup"><span data-stu-id="762e5-156">We can correct this error by either in one of two ways:</span></span>  
  
- <span data-ttu-id="762e5-157">путем определения `Dynamic` политики для `Book` типа в его [\<Type>](type-element-net-native.md) элементе.</span><span class="sxs-lookup"><span data-stu-id="762e5-157">by defining the `Dynamic` policy for the `Book` type in its [\<Type>](type-element-net-native.md) element.</span></span>  
  
- <span data-ttu-id="762e5-158">Путем добавления вложенного [\<Property>](property-element-net-native.md) элемента для каждого свойства, для которого необходимо вызвать метод получения, как в следующем default.rd.xml файле.</span><span class="sxs-lookup"><span data-stu-id="762e5-158">By adding a nested [\<Property>](property-element-net-native.md) element for each property whose getter we'd like to invoke, as the following default.rd.xml file does.</span></span>  
  
    ```xml  
    <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
       <Application>  
          <Namespace Name="LibraryApplications"  Browse="Required Public" >  
             <Type Name="Book"   Activate="All" >  
                <Property Name="Title" Dynamic="Required" />  
                <Property Name="Author" Dynamic="Required" />  
                  <Property Name="ISBN" Dynamic="Required" />  
             </Type>  
          </Namespace>  
       </Application>  
    </Directives>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="762e5-159">См. также</span><span class="sxs-lookup"><span data-stu-id="762e5-159">See also</span></span>

- [<span data-ttu-id="762e5-160">Ссылка на файл конфигурации директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="762e5-160">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="762e5-161">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="762e5-161">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="762e5-162">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="762e5-162">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
