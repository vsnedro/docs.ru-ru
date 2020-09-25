---
title: Элемент <etwEnable>
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
ms.openlocfilehash: 1c3e42dfbc2c27841ed065e90bad24575e4fb2b1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178272"
---
# <a name="etwenable-element"></a><span data-ttu-id="bb7f5-102">Элемент \<etwEnable></span><span class="sxs-lookup"><span data-stu-id="bb7f5-102">\<etwEnable> Element</span></span>

<span data-ttu-id="bb7f5-103">Указывает, следует ли включить трассировку событий Windows для событий среды CLR.</span><span class="sxs-lookup"><span data-stu-id="bb7f5-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<etwEnabled>**  
  
## <a name="syntax"></a><span data-ttu-id="bb7f5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb7f5-104">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb7f5-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bb7f5-105">Attributes and Elements</span></span>  

 <span data-ttu-id="bb7f5-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bb7f5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb7f5-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bb7f5-107">Attributes</span></span>  
  
|<span data-ttu-id="bb7f5-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bb7f5-108">Attribute</span></span>|<span data-ttu-id="bb7f5-109">Описание</span><span class="sxs-lookup"><span data-stu-id="bb7f5-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bb7f5-110">Включено</span><span class="sxs-lookup"><span data-stu-id="bb7f5-110">enabled</span></span>|<span data-ttu-id="bb7f5-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="bb7f5-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="bb7f5-112">Указывает, включена ли трассировка событий Windows.</span><span class="sxs-lookup"><span data-stu-id="bb7f5-112">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="bb7f5-113">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="bb7f5-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="bb7f5-114">Значение</span><span class="sxs-lookup"><span data-stu-id="bb7f5-114">Value</span></span>|<span data-ttu-id="bb7f5-115">Описание</span><span class="sxs-lookup"><span data-stu-id="bb7f5-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bb7f5-116">Да</span><span class="sxs-lookup"><span data-stu-id="bb7f5-116">true</span></span>|<span data-ttu-id="bb7f5-117">Включите ETW.</span><span class="sxs-lookup"><span data-stu-id="bb7f5-117">Enable ETW.</span></span> <span data-ttu-id="bb7f5-118">Это значение по умолчанию для версий Windows, начинающихся с операционных систем Windows Vista и Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="bb7f5-118">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="bb7f5-119">false</span><span class="sxs-lookup"><span data-stu-id="bb7f5-119">false</span></span>|<span data-ttu-id="bb7f5-120">Отключите трассировку событий Windows.</span><span class="sxs-lookup"><span data-stu-id="bb7f5-120">Disable ETW.</span></span> <span data-ttu-id="bb7f5-121">Это значение по умолчанию для более ранних версий Windows.</span><span class="sxs-lookup"><span data-stu-id="bb7f5-121">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb7f5-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bb7f5-122">Child Elements</span></span>  

 <span data-ttu-id="bb7f5-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bb7f5-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bb7f5-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bb7f5-124">Parent Elements</span></span>  
  
|<span data-ttu-id="bb7f5-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="bb7f5-125">Element</span></span>|<span data-ttu-id="bb7f5-126">Описание</span><span class="sxs-lookup"><span data-stu-id="bb7f5-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bb7f5-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bb7f5-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="bb7f5-128">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="bb7f5-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb7f5-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="bb7f5-129">Remarks</span></span>  

 <span data-ttu-id="bb7f5-130">Начиная с Windows Vista трассировка событий Windows включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb7f5-130">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="bb7f5-131">Используйте этот элемент, чтобы отключить ETW для приложения.</span><span class="sxs-lookup"><span data-stu-id="bb7f5-131">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="bb7f5-132">В более ранних версиях Windows этот элемент используется для включения ETW для приложения.</span><span class="sxs-lookup"><span data-stu-id="bb7f5-132">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bb7f5-133">Трассировку событий Windows можно включить или отключить глобально на сервере с помощью параметра реестра.</span><span class="sxs-lookup"><span data-stu-id="bb7f5-133">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="bb7f5-134">См. раздел [Управление ведением журнала .NET Framework](../../../performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="bb7f5-134">See [Controlling .NET Framework Logging](../../../performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb7f5-135">Пример</span><span class="sxs-lookup"><span data-stu-id="bb7f5-135">Example</span></span>  

 <span data-ttu-id="bb7f5-136">В следующем примере показано, как включить трассировку ETW для приложения.</span><span class="sxs-lookup"><span data-stu-id="bb7f5-136">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb7f5-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bb7f5-137">See also</span></span>

- [<span data-ttu-id="bb7f5-138">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="bb7f5-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bb7f5-139">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="bb7f5-139">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="bb7f5-140">Контроль ведения журнала .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bb7f5-140">Controlling .NET Framework Logging</span></span>](../../../performance/controlling-logging.md)
