---
title: Элемент <UseSmallInternalThreadStacks>
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
ms.openlocfilehash: 4917b47e9e8196eabe691f74531d12308ef80311
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91174086"
---
# <a name="usesmallinternalthreadstacks-element"></a><span data-ttu-id="244eb-102">Элемент \<UseSmallInternalThreadStacks></span><span class="sxs-lookup"><span data-stu-id="244eb-102">\<UseSmallInternalThreadStacks> Element</span></span>

<span data-ttu-id="244eb-103">Запрашивает уменьшение использования памяти средой CLR, указывая явные размеры стека при создании определенных потоков, используемых внутренним образом, вместо использования размера стека по умолчанию для этих потоков.</span><span class="sxs-lookup"><span data-stu-id="244eb-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<UseSmallInternalThreadStacks>**  
  
## <a name="syntax"></a><span data-ttu-id="244eb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="244eb-104">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="244eb-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="244eb-105">Attributes and Elements</span></span>  

 <span data-ttu-id="244eb-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="244eb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="244eb-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="244eb-107">Attributes</span></span>  
  
|<span data-ttu-id="244eb-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="244eb-108">Attribute</span></span>|<span data-ttu-id="244eb-109">Описание</span><span class="sxs-lookup"><span data-stu-id="244eb-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="244eb-110">Включено</span><span class="sxs-lookup"><span data-stu-id="244eb-110">enabled</span></span>|<span data-ttu-id="244eb-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="244eb-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="244eb-112">Указывает, следует ли запрашивать, что среда CLR использует явные размеры стека вместо размера стека по умолчанию при создании определенных потоков, используемых внутренним образом.</span><span class="sxs-lookup"><span data-stu-id="244eb-112">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="244eb-113">Явные размеры стека меньше, чем размер стека по умолчанию (1 МБ).</span><span class="sxs-lookup"><span data-stu-id="244eb-113">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="244eb-114">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="244eb-114">enabled Attribute</span></span>  
  
|<span data-ttu-id="244eb-115">Значение</span><span class="sxs-lookup"><span data-stu-id="244eb-115">Value</span></span>|<span data-ttu-id="244eb-116">Описание</span><span class="sxs-lookup"><span data-stu-id="244eb-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="244eb-117">Да</span><span class="sxs-lookup"><span data-stu-id="244eb-117">true</span></span>|<span data-ttu-id="244eb-118">Запрос явных размеров стека.</span><span class="sxs-lookup"><span data-stu-id="244eb-118">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="244eb-119">false</span><span class="sxs-lookup"><span data-stu-id="244eb-119">false</span></span>|<span data-ttu-id="244eb-120">Используйте размер стека по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="244eb-120">Use the default stack size.</span></span> <span data-ttu-id="244eb-121">Это значение по умолчанию для .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="244eb-121">This is the default for the .NET Framework 4.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="244eb-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="244eb-122">Child Elements</span></span>  

 <span data-ttu-id="244eb-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="244eb-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="244eb-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="244eb-124">Parent Elements</span></span>  
  
|<span data-ttu-id="244eb-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="244eb-125">Element</span></span>|<span data-ttu-id="244eb-126">Описание</span><span class="sxs-lookup"><span data-stu-id="244eb-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="244eb-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="244eb-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="244eb-128">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="244eb-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="244eb-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="244eb-129">Remarks</span></span>  

 <span data-ttu-id="244eb-130">Этот элемент конфигурации используется для запроса уменьшенного использования виртуальной памяти в процессе, поскольку явные размеры потоков, используемые средой CLR для внутренних потоков, если запрос обрабатывается, меньше размера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="244eb-130">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="244eb-131">Этот элемент конфигурации является запросом к CLR, а не абсолютному требованию.</span><span class="sxs-lookup"><span data-stu-id="244eb-131">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="244eb-132">В .NET Framework 4 запрос учитывается только для архитектуры x86.</span><span class="sxs-lookup"><span data-stu-id="244eb-132">In the .NET Framework 4, the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="244eb-133">Этот элемент может игнорироваться полностью в будущих версиях среды CLR или заменен на явные размеры стека, которые всегда используются для выбранных внутренних потоков.</span><span class="sxs-lookup"><span data-stu-id="244eb-133">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="244eb-134">Указание этого элемента конфигурации меняет надежность для использования меньшего объема виртуальной памяти, если среда CLR учитывает запрос, так как меньшие размеры стека потенциально могут привести к большей вероятности переполняет стек.</span><span class="sxs-lookup"><span data-stu-id="244eb-134">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="244eb-135">Пример</span><span class="sxs-lookup"><span data-stu-id="244eb-135">Example</span></span>  

 <span data-ttu-id="244eb-136">В следующем примере показано, как запросить, чтобы среда CLR использовала явные размеры стека для определенных потоков, которые он использует для внутренних целей.</span><span class="sxs-lookup"><span data-stu-id="244eb-136">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="244eb-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="244eb-137">See also</span></span>

- [<span data-ttu-id="244eb-138">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="244eb-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="244eb-139">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="244eb-139">Configuration File Schema</span></span>](../index.md)
