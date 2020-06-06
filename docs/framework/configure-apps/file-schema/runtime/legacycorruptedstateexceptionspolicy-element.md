---
title: Элемент <legacyCorruptedStateExceptionsPolicy>
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
ms.openlocfilehash: d1d29a37999a01f3e370897a1052f4f94435a218
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116457"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="29074-102">Элемент \<legacyCorruptedStateExceptionsPolicy></span><span class="sxs-lookup"><span data-stu-id="29074-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>
<span data-ttu-id="29074-103">Указывает, позволяет ли среда CLR использовать управляемый код для перехвата нарушений доступа и других исключений поврежденного состояния.</span><span class="sxs-lookup"><span data-stu-id="29074-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyCorruptedStateExceptionsPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="29074-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29074-104">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29074-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="29074-105">Attributes and Elements</span></span>  
 <span data-ttu-id="29074-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="29074-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29074-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="29074-107">Attributes</span></span>  
  
|<span data-ttu-id="29074-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="29074-108">Attribute</span></span>|<span data-ttu-id="29074-109">Описание</span><span class="sxs-lookup"><span data-stu-id="29074-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="29074-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="29074-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="29074-111">Указывает, что приложение будет перехватывать сбои исключения состояния, такие как нарушения прав доступа.</span><span class="sxs-lookup"><span data-stu-id="29074-111">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="29074-112">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="29074-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="29074-113">Значение</span><span class="sxs-lookup"><span data-stu-id="29074-113">Value</span></span>|<span data-ttu-id="29074-114">Описание</span><span class="sxs-lookup"><span data-stu-id="29074-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="29074-115">Приложение не будет перехватывать сбои повреждения состояния, такие как нарушения прав доступа.</span><span class="sxs-lookup"><span data-stu-id="29074-115">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="29074-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="29074-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="29074-117">Приложение будет перехватывать сбои исключения состояния, такие как нарушения прав доступа.</span><span class="sxs-lookup"><span data-stu-id="29074-117">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29074-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="29074-118">Child Elements</span></span>  
 <span data-ttu-id="29074-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="29074-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="29074-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="29074-120">Parent Elements</span></span>  
  
|<span data-ttu-id="29074-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="29074-121">Element</span></span>|<span data-ttu-id="29074-122">Описание</span><span class="sxs-lookup"><span data-stu-id="29074-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="29074-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="29074-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="29074-124">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="29074-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29074-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="29074-125">Remarks</span></span>  
 <span data-ttu-id="29074-126">В .NET Framework версии 3,5 и более ранних версиях среда CLR позволяла управляемому коду перехватывать исключения, которые были вызваны поврежденными состояниями процессов.</span><span class="sxs-lookup"><span data-stu-id="29074-126">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="29074-127">Нарушение прав доступа — это пример исключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="29074-127">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="29074-128">Начиная с .NET Framework 4 управляемый код больше не перехватывает исключения этих типов в `catch` блоках.</span><span class="sxs-lookup"><span data-stu-id="29074-128">Starting with the .NET Framework 4, managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="29074-129">Однако это изменение можно переопределить и обрабатывать исключения поврежденного состояния двумя способами:</span><span class="sxs-lookup"><span data-stu-id="29074-129">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="29074-130">Задайте `<legacyCorruptedStateExceptionsPolicy>` `enabled` для атрибута элемента значение `true` .</span><span class="sxs-lookup"><span data-stu-id="29074-130">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="29074-131">Этот параметр конфигурации применяется процессвиде и влияет на все методы.</span><span class="sxs-lookup"><span data-stu-id="29074-131">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="29074-132">-или-</span><span class="sxs-lookup"><span data-stu-id="29074-132">-or-</span></span>  
  
- <span data-ttu-id="29074-133">Примените <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> атрибут к методу, содержащему `catch` блок исключений.</span><span class="sxs-lookup"><span data-stu-id="29074-133">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="29074-134">Этот элемент конфигурации доступен только в .NET Framework 4 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="29074-134">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29074-135">Пример</span><span class="sxs-lookup"><span data-stu-id="29074-135">Example</span></span>  
 <span data-ttu-id="29074-136">В следующем примере показано, как указать, что приложение должно вернуться к поведению до .NET Framework 4, и перехватить все сбои исключений состояния.</span><span class="sxs-lookup"><span data-stu-id="29074-136">The following example shows how to specify that the application should revert to the behavior before the .NET Framework 4, and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="29074-137">См. также</span><span class="sxs-lookup"><span data-stu-id="29074-137">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="29074-138">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="29074-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="29074-139">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="29074-139">Configuration File Schema</span></span>](../index.md)
