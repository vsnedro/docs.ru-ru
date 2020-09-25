---
title: Элемент <developmentMode>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
ms.openlocfilehash: ddcabb831193baee30016f663f32d8562283d936
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205026"
---
# <a name="developmentmode-element"></a><span data-ttu-id="e1e09-102">Элемент \<developmentMode></span><span class="sxs-lookup"><span data-stu-id="e1e09-102">\<developmentMode> Element</span></span>

<span data-ttu-id="e1e09-103">Указывает, выполняет ли среда поиск сборок в каталогах, указанных в переменной среды DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="e1e09-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<developmentMode>**  
  
## <a name="syntax"></a><span data-ttu-id="e1e09-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1e09-104">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1e09-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e1e09-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e1e09-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e1e09-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1e09-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e1e09-107">Attributes</span></span>  
  
|<span data-ttu-id="e1e09-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e1e09-108">Attribute</span></span>|<span data-ttu-id="e1e09-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e1e09-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e1e09-110">**девелоперинсталлатион**</span><span class="sxs-lookup"><span data-stu-id="e1e09-110">**developerInstallation**</span></span>|<span data-ttu-id="e1e09-111">Указывает, выполняет ли среда поиск сборок в каталогах, указанных в переменной среды DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="e1e09-111">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="e1e09-112">Атрибут Девелоперинсталлатион</span><span class="sxs-lookup"><span data-stu-id="e1e09-112">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="e1e09-113">Значение</span><span class="sxs-lookup"><span data-stu-id="e1e09-113">Value</span></span>|<span data-ttu-id="e1e09-114">Описание</span><span class="sxs-lookup"><span data-stu-id="e1e09-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e1e09-115">**true**</span><span class="sxs-lookup"><span data-stu-id="e1e09-115">**true**</span></span>|<span data-ttu-id="e1e09-116">Выполняет поиск сборок в каталогах, заданных переменной среды DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="e1e09-116">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="e1e09-117">**false**</span><span class="sxs-lookup"><span data-stu-id="e1e09-117">**false**</span></span>|<span data-ttu-id="e1e09-118">Не выполняет поиск сборок в каталогах, заданных переменной среды DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="e1e09-118">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="e1e09-119">Это значение установлено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e1e09-119">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1e09-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e1e09-120">Child Elements</span></span>  

 <span data-ttu-id="e1e09-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e1e09-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1e09-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e1e09-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e1e09-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="e1e09-123">Element</span></span>|<span data-ttu-id="e1e09-124">Описание</span><span class="sxs-lookup"><span data-stu-id="e1e09-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e1e09-125">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e1e09-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e1e09-126">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="e1e09-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1e09-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="e1e09-127">Remarks</span></span>  

 <span data-ttu-id="e1e09-128">Используйте этот параметр только во время разработки.</span><span class="sxs-lookup"><span data-stu-id="e1e09-128">Use this setting only at development time.</span></span> <span data-ttu-id="e1e09-129">Среда выполнения не проверяет версии сборок со строгими именами, найденных в DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="e1e09-129">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="e1e09-130">Он просто использует первую найденную сборку.</span><span class="sxs-lookup"><span data-stu-id="e1e09-130">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1e09-131">Пример</span><span class="sxs-lookup"><span data-stu-id="e1e09-131">Example</span></span>  

 <span data-ttu-id="e1e09-132">В следующем примере показано, как заставить среду выполнения искать сборки в каталогах, заданных переменной среды DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="e1e09-132">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1e09-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e1e09-133">See also</span></span>

- [<span data-ttu-id="e1e09-134">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="e1e09-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e1e09-135">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e1e09-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e1e09-136">Практическое руководство. Поиск сборок с помощью DEVPATH</span><span class="sxs-lookup"><span data-stu-id="e1e09-136">How to: Locate Assemblies by Using DEVPATH</span></span>](../../how-to-locate-assemblies-by-using-devpath.md)
