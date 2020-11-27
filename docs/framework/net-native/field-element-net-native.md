---
title: <Field> Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
ms.openlocfilehash: e63dc293c42aa620b7f7ac15fc0454bc603b9dde
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251052"
---
# <a name="field-element-net-native"></a><span data-ttu-id="d669c-102">\<Field> Элемент (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="d669c-102">\<Field> Element (.NET Native)</span></span>

<span data-ttu-id="d669c-103">Применяет политику отражения среды выполнения к полю.</span><span class="sxs-lookup"><span data-stu-id="d669c-103">Applies runtime reflection policy to a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d669c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d669c-104">Syntax</span></span>  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d669c-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d669c-105">Attributes and Elements</span></span>  

 <span data-ttu-id="d669c-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d669c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d669c-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d669c-107">Attributes</span></span>  
  
|<span data-ttu-id="d669c-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d669c-108">Attribute</span></span>|<span data-ttu-id="d669c-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="d669c-109">Attribute type</span></span>|<span data-ttu-id="d669c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d669c-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="d669c-111">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="d669c-111">General</span></span>|<span data-ttu-id="d669c-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d669c-112">Required attribute.</span></span> <span data-ttu-id="d669c-113">Определяет имя поля.</span><span class="sxs-lookup"><span data-stu-id="d669c-113">Specifies the field name.</span></span>|  
|`Browse`|<span data-ttu-id="d669c-114">Отражение</span><span class="sxs-lookup"><span data-stu-id="d669c-114">Reflection</span></span>|<span data-ttu-id="d669c-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d669c-115">Optional attribute.</span></span> <span data-ttu-id="d669c-116">Определяет запрос для получения сведений о поле или перечисляет поле, но не включает динамический доступ во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d669c-116">Controls querying for information about or enumerating the field but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="d669c-117">Отражение</span><span class="sxs-lookup"><span data-stu-id="d669c-117">Reflection</span></span>|<span data-ttu-id="d669c-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d669c-118">Optional attribute.</span></span> <span data-ttu-id="d669c-119">Управляет доступом среды выполнения к полю для включения динамического программирования.</span><span class="sxs-lookup"><span data-stu-id="d669c-119">Controls runtime access to the field to enable dynamic programming.</span></span> <span data-ttu-id="d669c-120">Эта политика гарантирует, что поле можно задать или получить динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d669c-120">This policy ensures that a field can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="d669c-121">Сериализация</span><span class="sxs-lookup"><span data-stu-id="d669c-121">Serialization</span></span>|<span data-ttu-id="d669c-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d669c-122">Optional attribute.</span></span> <span data-ttu-id="d669c-123">Управляет доступом среды выполнения к полю, чтобы включить экземпляры типов, предназначенных для сериализации в таких библиотеках, как, например, сериализатор Newtonsoft JSON или для привязки данных.</span><span class="sxs-lookup"><span data-stu-id="d669c-123">Controls runtime access to a field to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="d669c-124">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="d669c-124">Name attribute</span></span>  
  
|<span data-ttu-id="d669c-125">Значение</span><span class="sxs-lookup"><span data-stu-id="d669c-125">Value</span></span>|<span data-ttu-id="d669c-126">Описание</span><span class="sxs-lookup"><span data-stu-id="d669c-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d669c-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="d669c-127">*method_name*</span></span>|<span data-ttu-id="d669c-128">Имя поля.</span><span class="sxs-lookup"><span data-stu-id="d669c-128">The field name.</span></span> <span data-ttu-id="d669c-129">Тип поля определяется родительским [\<Type>](type-element-net-native.md) [\<TypeInstantiation>](typeinstantiation-element-net-native.md) элементом или.</span><span class="sxs-lookup"><span data-stu-id="d669c-129">The type of the field is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="d669c-130">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="d669c-130">All other attributes</span></span>  
  
|<span data-ttu-id="d669c-131">Значение</span><span class="sxs-lookup"><span data-stu-id="d669c-131">Value</span></span>|<span data-ttu-id="d669c-132">Описание</span><span class="sxs-lookup"><span data-stu-id="d669c-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d669c-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="d669c-133">*policy_setting*</span></span>|<span data-ttu-id="d669c-134">Параметр, применяемый к этому типу политики для поля.</span><span class="sxs-lookup"><span data-stu-id="d669c-134">The setting to apply to this policy type for the field.</span></span> <span data-ttu-id="d669c-135">Допустимые значения: `Auto`, `Excluded`, `Included` и `Required`.</span><span class="sxs-lookup"><span data-stu-id="d669c-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="d669c-136">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="d669c-136">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d669c-137">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d669c-137">Child Elements</span></span>  

 <span data-ttu-id="d669c-138">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d669c-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d669c-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d669c-139">Parent Elements</span></span>  
  
|<span data-ttu-id="d669c-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="d669c-140">Element</span></span>|<span data-ttu-id="d669c-141">Описание</span><span class="sxs-lookup"><span data-stu-id="d669c-141">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="d669c-142">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="d669c-142">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="d669c-143">Применяет политику отражения к сконструированному универсальному типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="d669c-143">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d669c-144">Примечания</span><span class="sxs-lookup"><span data-stu-id="d669c-144">Remarks</span></span>  

 <span data-ttu-id="d669c-145">Если политика поля не определена явно, оно наследует политику среды выполнения своего родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="d669c-145">If a field's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d669c-146">См. также</span><span class="sxs-lookup"><span data-stu-id="d669c-146">See also</span></span>

- [<span data-ttu-id="d669c-147">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="d669c-147">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="d669c-148">Ссылка на файл конфигурации директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="d669c-148">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="d669c-149">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="d669c-149">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
