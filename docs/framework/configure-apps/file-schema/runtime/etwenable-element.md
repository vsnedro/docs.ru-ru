---
title: Элемент <etwEnable>
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
ms.openlocfilehash: 14cea171a4a25e148ea32f75a8ef09b83a4ec8ad
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117400"
---
# <a name="etwenable-element"></a><span data-ttu-id="a8992-102">Элемент \<etwEnable></span><span class="sxs-lookup"><span data-stu-id="a8992-102">\<etwEnable> Element</span></span>
<span data-ttu-id="a8992-103">Указывает, следует ли включить трассировку событий Windows для событий среды CLR.</span><span class="sxs-lookup"><span data-stu-id="a8992-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<etwEnabled>**  
  
## <a name="syntax"></a><span data-ttu-id="a8992-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8992-104">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8992-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a8992-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a8992-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a8992-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8992-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a8992-107">Attributes</span></span>  
  
|<span data-ttu-id="a8992-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a8992-108">Attribute</span></span>|<span data-ttu-id="a8992-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="a8992-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a8992-110">Включено</span><span class="sxs-lookup"><span data-stu-id="a8992-110">enabled</span></span>|<span data-ttu-id="a8992-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a8992-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="a8992-112">Указывает, включена ли трассировка событий Windows.</span><span class="sxs-lookup"><span data-stu-id="a8992-112">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a8992-113">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="a8992-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="a8992-114">Значение</span><span class="sxs-lookup"><span data-stu-id="a8992-114">Value</span></span>|<span data-ttu-id="a8992-115">Описание</span><span class="sxs-lookup"><span data-stu-id="a8992-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a8992-116">Да</span><span class="sxs-lookup"><span data-stu-id="a8992-116">true</span></span>|<span data-ttu-id="a8992-117">Включите ETW.</span><span class="sxs-lookup"><span data-stu-id="a8992-117">Enable ETW.</span></span> <span data-ttu-id="a8992-118">Это значение по умолчанию для версий Windows, начинающихся с операционных систем Windows Vista и Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="a8992-118">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="a8992-119">false</span><span class="sxs-lookup"><span data-stu-id="a8992-119">false</span></span>|<span data-ttu-id="a8992-120">Отключите трассировку событий Windows.</span><span class="sxs-lookup"><span data-stu-id="a8992-120">Disable ETW.</span></span> <span data-ttu-id="a8992-121">Это значение по умолчанию для более ранних версий Windows.</span><span class="sxs-lookup"><span data-stu-id="a8992-121">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a8992-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a8992-122">Child Elements</span></span>  
 <span data-ttu-id="a8992-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a8992-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a8992-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a8992-124">Parent Elements</span></span>  
  
|<span data-ttu-id="a8992-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="a8992-125">Element</span></span>|<span data-ttu-id="a8992-126">Описание</span><span class="sxs-lookup"><span data-stu-id="a8992-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a8992-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a8992-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a8992-128">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="a8992-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8992-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="a8992-129">Remarks</span></span>  
 <span data-ttu-id="a8992-130">Начиная с Windows Vista трассировка событий Windows включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a8992-130">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="a8992-131">Используйте этот элемент, чтобы отключить ETW для приложения.</span><span class="sxs-lookup"><span data-stu-id="a8992-131">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="a8992-132">В более ранних версиях Windows этот элемент используется для включения ETW для приложения.</span><span class="sxs-lookup"><span data-stu-id="a8992-132">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a8992-133">Трассировку событий Windows можно включить или отключить глобально на сервере с помощью параметра реестра.</span><span class="sxs-lookup"><span data-stu-id="a8992-133">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="a8992-134">См. раздел [Управление ведением журнала .NET Framework](../../../performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="a8992-134">See [Controlling .NET Framework Logging](../../../performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8992-135">Пример</span><span class="sxs-lookup"><span data-stu-id="a8992-135">Example</span></span>  
 <span data-ttu-id="a8992-136">В следующем примере показано, как включить трассировку ETW для приложения.</span><span class="sxs-lookup"><span data-stu-id="a8992-136">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8992-137">См. также</span><span class="sxs-lookup"><span data-stu-id="a8992-137">See also</span></span>

- [<span data-ttu-id="a8992-138">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="a8992-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a8992-139">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="a8992-139">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a8992-140">Контроль ведения журнала .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a8992-140">Controlling .NET Framework Logging</span></span>](../../../performance/controlling-logging.md)
