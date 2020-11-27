---
title: <MethodInstantiation> Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
ms.openlocfilehash: e247db05f8442d4fcfddbf03b5eb8955b8ff425a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250961"
---
# <a name="methodinstantiation-element-net-native"></a><span data-ttu-id="f8701-102">\<MethodInstantiation> Элемент (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="f8701-102">\<MethodInstantiation> Element (.NET Native)</span></span>

<span data-ttu-id="f8701-103">Применяет политику отражения среды выполнения к сконструированному универсальному методу.</span><span class="sxs-lookup"><span data-stu-id="f8701-103">Applies runtime reflection policy to a constructed generic method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8701-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8701-104">Syntax</span></span>  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8701-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f8701-105">Attributes and Elements</span></span>  

 <span data-ttu-id="f8701-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f8701-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8701-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f8701-107">Attributes</span></span>  
  
|<span data-ttu-id="f8701-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f8701-108">Attribute</span></span>|<span data-ttu-id="f8701-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="f8701-109">Attribute type</span></span>|<span data-ttu-id="f8701-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f8701-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="f8701-111">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="f8701-111">General</span></span>|<span data-ttu-id="f8701-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="f8701-112">Required attribute.</span></span> <span data-ttu-id="f8701-113">Задает имя метода.</span><span class="sxs-lookup"><span data-stu-id="f8701-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="f8701-114">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="f8701-114">General</span></span>|<span data-ttu-id="f8701-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="f8701-115">Optional attribute.</span></span> <span data-ttu-id="f8701-116">Определяет именованные параметры метода.</span><span class="sxs-lookup"><span data-stu-id="f8701-116">Specifies named parameters of the method.</span></span> <span data-ttu-id="f8701-117">Несколько именованных параметров разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="f8701-117">Multiple named parameters are separated by commas.</span></span> <span data-ttu-id="f8701-118">Атрибут `Signature` позволяет различать перегруженные методы.</span><span class="sxs-lookup"><span data-stu-id="f8701-118">The `Signature` attribute is used to differentiate overloaded methods.</span></span>|  
|`Arguments`|<span data-ttu-id="f8701-119">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="f8701-119">General</span></span>|<span data-ttu-id="f8701-120">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="f8701-120">Required attribute.</span></span> <span data-ttu-id="f8701-121">Задает аргументы универсального типа.</span><span class="sxs-lookup"><span data-stu-id="f8701-121">Specifies the generic type arguments.</span></span> <span data-ttu-id="f8701-122">При наличии нескольких аргументов, они разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="f8701-122">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Browse`|<span data-ttu-id="f8701-123">Отражение</span><span class="sxs-lookup"><span data-stu-id="f8701-123">Reflection</span></span>|<span data-ttu-id="f8701-124">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="f8701-124">Optional attribute.</span></span> <span data-ttu-id="f8701-125">Определяет запрос для получения сведений о методе или перечисляет методы, но не включает динамический вызов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f8701-125">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="f8701-126">Отражение</span><span class="sxs-lookup"><span data-stu-id="f8701-126">Reflection</span></span>|<span data-ttu-id="f8701-127">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="f8701-127">Optional attribute.</span></span> <span data-ttu-id="f8701-128">Управляет доступом среды выполнения к конструктору или методу для включения динамического программирования.</span><span class="sxs-lookup"><span data-stu-id="f8701-128">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="f8701-129">Эта политика гарантирует, что член может быть вызван динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f8701-129">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="f8701-130">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="f8701-130">Name attribute</span></span>  
  
|<span data-ttu-id="f8701-131">Значение</span><span class="sxs-lookup"><span data-stu-id="f8701-131">Value</span></span>|<span data-ttu-id="f8701-132">Описание</span><span class="sxs-lookup"><span data-stu-id="f8701-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f8701-133">*method_name*</span><span class="sxs-lookup"><span data-stu-id="f8701-133">*method_name*</span></span>|<span data-ttu-id="f8701-134">Имя метода.</span><span class="sxs-lookup"><span data-stu-id="f8701-134">The method name.</span></span> <span data-ttu-id="f8701-135">Тип метода определяется родительским [\<Type>](type-element-net-native.md) [\<TypeInstantiation>](typeinstantiation-element-net-native.md) элементом или.</span><span class="sxs-lookup"><span data-stu-id="f8701-135">The type of the method is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="f8701-136">Сигнатура атрибута</span><span class="sxs-lookup"><span data-stu-id="f8701-136">Signature attribute</span></span>  
  
|<span data-ttu-id="f8701-137">Значение</span><span class="sxs-lookup"><span data-stu-id="f8701-137">Value</span></span>|<span data-ttu-id="f8701-138">Описание</span><span class="sxs-lookup"><span data-stu-id="f8701-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f8701-139">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="f8701-139">*method_signature*</span></span>|<span data-ttu-id="f8701-140">Определяет именованные параметры метода.</span><span class="sxs-lookup"><span data-stu-id="f8701-140">Specifies the named parameters of the method.</span></span> <span data-ttu-id="f8701-141">При наличии нескольких параметров, они разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="f8701-141">If multiple parameters are present, they are separated by commas.</span></span>|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="f8701-142">Атрибут аргументов</span><span class="sxs-lookup"><span data-stu-id="f8701-142">Arguments attribute</span></span>  
  
|<span data-ttu-id="f8701-143">Значение</span><span class="sxs-lookup"><span data-stu-id="f8701-143">Value</span></span>|<span data-ttu-id="f8701-144">Описание</span><span class="sxs-lookup"><span data-stu-id="f8701-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f8701-145">*method_arguments*</span><span class="sxs-lookup"><span data-stu-id="f8701-145">*method_arguments*</span></span>|<span data-ttu-id="f8701-146">Задает аргументы универсального типа.</span><span class="sxs-lookup"><span data-stu-id="f8701-146">Specifies the generic type arguments.</span></span> <span data-ttu-id="f8701-147">При наличии нескольких аргументов, они разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="f8701-147">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="f8701-148">Каждый аргумент должен содержать полное имя типа.</span><span class="sxs-lookup"><span data-stu-id="f8701-148">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="f8701-149">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="f8701-149">All other attributes</span></span>  
  
|<span data-ttu-id="f8701-150">Значение</span><span class="sxs-lookup"><span data-stu-id="f8701-150">Value</span></span>|<span data-ttu-id="f8701-151">Описание</span><span class="sxs-lookup"><span data-stu-id="f8701-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f8701-152">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="f8701-152">*policy_setting*</span></span>|<span data-ttu-id="f8701-153">Параметр, применяемый к этому типу политики для метода.</span><span class="sxs-lookup"><span data-stu-id="f8701-153">The setting to apply to this policy type for the method.</span></span> <span data-ttu-id="f8701-154">Допустимые значения: `Auto`, `Excluded`, `Included` и `Required`.</span><span class="sxs-lookup"><span data-stu-id="f8701-154">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="f8701-155">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f8701-155">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8701-156">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f8701-156">Child Elements</span></span>  

 <span data-ttu-id="f8701-157">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f8701-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f8701-158">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f8701-158">Parent Elements</span></span>  
  
|<span data-ttu-id="f8701-159">Элемент</span><span class="sxs-lookup"><span data-stu-id="f8701-159">Element</span></span>|<span data-ttu-id="f8701-160">Описание</span><span class="sxs-lookup"><span data-stu-id="f8701-160">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="f8701-161">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="f8701-161">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="f8701-162">Применяет политику отражения к сконструированному универсальному типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="f8701-162">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8701-163">Примечания</span><span class="sxs-lookup"><span data-stu-id="f8701-163">Remarks</span></span>  

 <span data-ttu-id="f8701-164">Элемент `<MethodInstantiation>`  переопределяет политику отражения среды выполнения его соответствующего открытого универсального метода.</span><span class="sxs-lookup"><span data-stu-id="f8701-164">The `<MethodInstantiation>` element overrides the runtime reflection policy of its corresponding open generic method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8701-165">См. также</span><span class="sxs-lookup"><span data-stu-id="f8701-165">See also</span></span>

- [<span data-ttu-id="f8701-166">Ссылка на файл конфигурации директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="f8701-166">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="f8701-167">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="f8701-167">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="f8701-168">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="f8701-168">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="f8701-169">\<Method> Элемент</span><span class="sxs-lookup"><span data-stu-id="f8701-169">\<Method> Element</span></span>](method-element-net-native.md)
