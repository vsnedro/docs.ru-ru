---
title: <Event>Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
ms.openlocfilehash: 60da48d5872d7ce61afcffa7977411bc6e1efc7f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79181042"
---
# <a name="event-element-net-native"></a><span data-ttu-id="0956c-102">\<Event>Элемент (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="0956c-102">\<Event> Element (.NET Native)</span></span>
<span data-ttu-id="0956c-103">Применяет политику отражения среды выполнения к событию.</span><span class="sxs-lookup"><span data-stu-id="0956c-103">Applies runtime reflection policy to an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0956c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0956c-104">Syntax</span></span>  
  
```xml  
<Event Name="event_name"
       Browse="policy_type"
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0956c-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0956c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0956c-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0956c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0956c-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0956c-107">Attributes</span></span>  
  
|<span data-ttu-id="0956c-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0956c-108">Attribute</span></span>|<span data-ttu-id="0956c-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="0956c-109">Attribute type</span></span>|<span data-ttu-id="0956c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="0956c-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="0956c-111">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="0956c-111">General</span></span>|<span data-ttu-id="0956c-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="0956c-112">Required attribute.</span></span> <span data-ttu-id="0956c-113">Задает имя события.</span><span class="sxs-lookup"><span data-stu-id="0956c-113">Specifies the event name.</span></span>|  
|`Browse`|<span data-ttu-id="0956c-114">Отражение</span><span class="sxs-lookup"><span data-stu-id="0956c-114">Reflection</span></span>|<span data-ttu-id="0956c-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="0956c-115">Optional attribute.</span></span> <span data-ttu-id="0956c-116">Определяет запрос для получения сведений о событиях или перечисляет события, но не включает динамический доступ во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0956c-116">Controls querying for information about or enumerating the event but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="0956c-117">Отражение</span><span class="sxs-lookup"><span data-stu-id="0956c-117">Reflection</span></span>|<span data-ttu-id="0956c-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="0956c-118">Optional attribute.</span></span> <span data-ttu-id="0956c-119">Управляет доступом среды выполнения к событию для включения динамического программирования.</span><span class="sxs-lookup"><span data-stu-id="0956c-119">Controls runtime access to the event to enable dynamic programming.</span></span> <span data-ttu-id="0956c-120">Эта политика гарантирует, что события могут обрабатываться динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0956c-120">This policy ensures that an event can be handled dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="0956c-121">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="0956c-121">Name attribute</span></span>  
  
|<span data-ttu-id="0956c-122">Значение</span><span class="sxs-lookup"><span data-stu-id="0956c-122">Value</span></span>|<span data-ttu-id="0956c-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="0956c-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0956c-124">*method_name*</span><span class="sxs-lookup"><span data-stu-id="0956c-124">*method_name*</span></span>|<span data-ttu-id="0956c-125">Имя события.</span><span class="sxs-lookup"><span data-stu-id="0956c-125">The event name.</span></span> <span data-ttu-id="0956c-126">Тип события определяется родительским [\<Type>](type-element-net-native.md) [\<TypeInstantiation>](typeinstantiation-element-net-native.md) элементом или.</span><span class="sxs-lookup"><span data-stu-id="0956c-126">The type of the event is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="0956c-127">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="0956c-127">All other attributes</span></span>  
  
|<span data-ttu-id="0956c-128">Значение</span><span class="sxs-lookup"><span data-stu-id="0956c-128">Value</span></span>|<span data-ttu-id="0956c-129">Описание:</span><span class="sxs-lookup"><span data-stu-id="0956c-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0956c-130">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="0956c-130">*policy_setting*</span></span>|<span data-ttu-id="0956c-131">Параметр, применяемый к этому типу политики для события.</span><span class="sxs-lookup"><span data-stu-id="0956c-131">The setting to apply to this policy type for the event.</span></span> <span data-ttu-id="0956c-132">Допустимые значения: `Auto`, `Excluded`, `Included` и `Required`.</span><span class="sxs-lookup"><span data-stu-id="0956c-132">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="0956c-133">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="0956c-133">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0956c-134">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0956c-134">Child Elements</span></span>  
 <span data-ttu-id="0956c-135">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0956c-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0956c-136">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0956c-136">Parent Elements</span></span>  
  
|<span data-ttu-id="0956c-137">Элемент</span><span class="sxs-lookup"><span data-stu-id="0956c-137">Element</span></span>|<span data-ttu-id="0956c-138">Описание</span><span class="sxs-lookup"><span data-stu-id="0956c-138">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="0956c-139">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="0956c-139">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="0956c-140">Применяет политику отражения к сконструированному универсальному типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="0956c-140">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0956c-141">Примечания</span><span class="sxs-lookup"><span data-stu-id="0956c-141">Remarks</span></span>  
 <span data-ttu-id="0956c-142">Если политика события не определена явно, оно наследует политику среды выполнения своего родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="0956c-142">If an event's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0956c-143">См. также</span><span class="sxs-lookup"><span data-stu-id="0956c-143">See also</span></span>

- [<span data-ttu-id="0956c-144">Ссылка на файл конфигурации директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="0956c-144">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="0956c-145">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="0956c-145">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="0956c-146">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="0956c-146">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
