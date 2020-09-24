---
title: Элемент <EnableAmPmParseAdjustment>
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
ms.openlocfilehash: f935f213e1bca8dac7a5401970bc6183575e2301
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167233"
---
# <a name="enableampmparseadjustment-element"></a><span data-ttu-id="89651-102">Элемент \<EnableAmPmParseAdjustment></span><span class="sxs-lookup"><span data-stu-id="89651-102">\<EnableAmPmParseAdjustment> Element</span></span>

<span data-ttu-id="89651-103">Определяет, используют ли методы синтаксического анализа даты и времени настроенный набор правил для синтаксического анализа строк даты, содержащих день, месяц, час и обозначение AM/PM.</span><span class="sxs-lookup"><span data-stu-id="89651-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<EnableAmPmParseAdjustment>**  
  
## <a name="syntax"></a><span data-ttu-id="89651-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89651-104">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89651-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="89651-105">Attributes and Elements</span></span>  

 <span data-ttu-id="89651-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="89651-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89651-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="89651-107">Attributes</span></span>  
  
|<span data-ttu-id="89651-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="89651-108">Attribute</span></span>|<span data-ttu-id="89651-109">Описание</span><span class="sxs-lookup"><span data-stu-id="89651-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="89651-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="89651-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="89651-111">Указывает, используют ли методы синтаксического анализа даты и времени настроенный набор правил для анализа строк даты, содержащих только день, месяц, час и обозначение AM/PM.</span><span class="sxs-lookup"><span data-stu-id="89651-111">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="89651-112">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="89651-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="89651-113">Значение</span><span class="sxs-lookup"><span data-stu-id="89651-113">Value</span></span>|<span data-ttu-id="89651-114">Описание</span><span class="sxs-lookup"><span data-stu-id="89651-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="89651-115">0</span><span class="sxs-lookup"><span data-stu-id="89651-115">0</span></span>|<span data-ttu-id="89651-116">Методы синтаксического анализа даты и времени не используют скорректированные правила для анализа строк даты, содержащих только день, месяц, час и обозначение AM/PM.</span><span class="sxs-lookup"><span data-stu-id="89651-116">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="89651-117">1</span><span class="sxs-lookup"><span data-stu-id="89651-117">1</span></span>|<span data-ttu-id="89651-118">Методы синтаксического анализа даты и времени используют скорректированные правила для анализа строк даты, содержащих только день, месяц, час и обозначение AM/PM.</span><span class="sxs-lookup"><span data-stu-id="89651-118">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89651-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="89651-119">Child Elements</span></span>  

 <span data-ttu-id="89651-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="89651-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="89651-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="89651-121">Parent Elements</span></span>  
  
|<span data-ttu-id="89651-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="89651-122">Element</span></span>|<span data-ttu-id="89651-123">Описание</span><span class="sxs-lookup"><span data-stu-id="89651-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="89651-124">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="89651-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="89651-125">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="89651-125">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89651-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="89651-126">Remarks</span></span>  

 <span data-ttu-id="89651-127">`<EnableAmPmParseAdjustment>`Элемент определяет, как следующие методы анализируют строку даты, которая содержит числовой день и месяц, за которыми следует час и обозначение AM/PM (например, "4/10 6 AM"):</span><span class="sxs-lookup"><span data-stu-id="89651-127">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="89651-128">Другие шаблоны не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="89651-128">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="89651-129">`<EnableAmPmParseAdjustment>`Элемент не влияет на <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> методы,, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType> <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType> и <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="89651-129">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="89651-130">В .NET Core и .NET Native настроенные правила анализа AM/PM включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="89651-130">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="89651-131">Если правило коррекции синтаксического анализа не включено, первая цифра строки интерпретируется как час 12-часового времени, а оставшаяся часть строки, за исключением обозначения AM/PM, игнорируется.</span><span class="sxs-lookup"><span data-stu-id="89651-131">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="89651-132">Дата и время, возвращаемые методом анализа, состоят из текущей даты и часа дня, извлеченных из строки даты.</span><span class="sxs-lookup"><span data-stu-id="89651-132">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="89651-133">Если правило коррекции синтаксического анализа включено, метод синтаксического анализа интерпретирует день и месяц как принадлежащий текущему году и интерпретирует время как час 12-часового времени.</span><span class="sxs-lookup"><span data-stu-id="89651-133">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="89651-134">В следующей таблице показано различие в <xref:System.DateTime> значении, когда <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> метод используется для синтаксического анализа строки "" 4/10 6 AM "со `<EnableAmPmParseAdjustment>` свойством элемента, `enabled` имеющим значение" 0 "или" 1 ".</span><span class="sxs-lookup"><span data-stu-id="89651-134">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="89651-135">Предполагается, что сегодняшняя дата — 5 января 2017, а дата отображается так, как если бы она была отформатирована с использованием строки формата "G" указанного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="89651-135">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="89651-136">Название языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="89651-136">Culture name</span></span>|<span data-ttu-id="89651-137">Enabled = "0"</span><span class="sxs-lookup"><span data-stu-id="89651-137">enabled="0"</span></span>|<span data-ttu-id="89651-138">Enabled = "1"</span><span class="sxs-lookup"><span data-stu-id="89651-138">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="89651-139">en-US</span><span class="sxs-lookup"><span data-stu-id="89651-139">en-US</span></span>|<span data-ttu-id="89651-140">1/5/2017 4:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="89651-140">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="89651-141">4/10/2017 6:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="89651-141">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="89651-142">en-GB</span><span class="sxs-lookup"><span data-stu-id="89651-142">en-GB</span></span>|<span data-ttu-id="89651-143">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="89651-143">5/1/2017 6:00:00</span></span>|<span data-ttu-id="89651-144">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="89651-144">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="89651-145">См. также</span><span class="sxs-lookup"><span data-stu-id="89651-145">See also</span></span>

- [<span data-ttu-id="89651-146">\<runtime> Элемент</span><span class="sxs-lookup"><span data-stu-id="89651-146">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="89651-147">\<configuration> Элемент</span><span class="sxs-lookup"><span data-stu-id="89651-147">\<configuration> Element</span></span>](../configuration-element.md)
