---
title: Элемент <add> для <switches>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
ms.openlocfilehash: db2de681227dfdb7420808963219b9f52381f8fe
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088962"
---
# <a name="add-element-for-switches"></a><span data-ttu-id="ee056-102">Элемент \<add> для \<switches></span><span class="sxs-lookup"><span data-stu-id="ee056-102">\<add> Element for \<switches></span></span>
<span data-ttu-id="ee056-103">Задает уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="ee056-103">Specifies the level where a trace switch is set.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<switches>**](switches-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="ee056-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee056-104">Syntax</span></span>  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee056-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ee056-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ee056-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ee056-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee056-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ee056-107">Attributes</span></span>  
  
|<span data-ttu-id="ee056-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ee056-108">Attribute</span></span>|<span data-ttu-id="ee056-109">Описание</span><span class="sxs-lookup"><span data-stu-id="ee056-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ee056-110">**name**</span><span class="sxs-lookup"><span data-stu-id="ee056-110">**name**</span></span>|<span data-ttu-id="ee056-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ee056-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="ee056-112">Указывает имя переключателя.</span><span class="sxs-lookup"><span data-stu-id="ee056-112">Specifies the name of the switch.</span></span> <span data-ttu-id="ee056-113">Значение этого атрибута соответствует параметру *DisplayName* , переданному в конструктор переключателя.</span><span class="sxs-lookup"><span data-stu-id="ee056-113">The value of this attribute corresponds to the *displayName* parameter that is passed to switch constructor.</span></span>|  
|<span data-ttu-id="ee056-114">**value**</span><span class="sxs-lookup"><span data-stu-id="ee056-114">**value**</span></span>|<span data-ttu-id="ee056-115">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ee056-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="ee056-116">Задает уровень переключателя.</span><span class="sxs-lookup"><span data-stu-id="ee056-116">Specifies the level of the switch.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee056-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ee056-117">Child Elements</span></span>  
 <span data-ttu-id="ee056-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ee056-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ee056-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ee056-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ee056-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="ee056-120">Element</span></span>|<span data-ttu-id="ee056-121">Описание</span><span class="sxs-lookup"><span data-stu-id="ee056-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ee056-122">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ee056-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`switches`|<span data-ttu-id="ee056-123">Содержит ключи трассировки и уровень, на котором они установлены.</span><span class="sxs-lookup"><span data-stu-id="ee056-123">Contains trace switches and the level where the trace switches are set.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ee056-124">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="ee056-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee056-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="ee056-125">Remarks</span></span>  
 <span data-ttu-id="ee056-126">Уровень переключателя трассировки можно изменить, поместив его в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ee056-126">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="ee056-127">Если параметр имеет значение <xref:System.Diagnostics.BooleanSwitch> , его можно включить и отключить.</span><span class="sxs-lookup"><span data-stu-id="ee056-127">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="ee056-128">Если параметр имеет значение <xref:System.Diagnostics.TraceSwitch> , можно назначить для него разные уровни, чтобы указать типы трассировки или сообщения отладки, выданные приложением.</span><span class="sxs-lookup"><span data-stu-id="ee056-128">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee056-129">Пример</span><span class="sxs-lookup"><span data-stu-id="ee056-129">Example</span></span>  
 <span data-ttu-id="ee056-130">В следующем примере показано использование **\<add>** элемента для задания `General` переключателя трассировки на <xref:System.Diagnostics.TraceLevel> уровне и включения `Data` логического переключателя трассировки.</span><span class="sxs-lookup"><span data-stu-id="ee056-130">The following example shows how to use the **\<add>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ee056-131">См. также</span><span class="sxs-lookup"><span data-stu-id="ee056-131">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="ee056-132">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="ee056-132">Trace and Debug Settings Schema</span></span>](index.md)
