---
title: Элемент <disableCommitThreadStack>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
ms.openlocfilehash: 8aefb8a20d6a95c5b8062d0c03dcb28a3557ca3d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117476"
---
# <a name="disablecommitthreadstack-element"></a><span data-ttu-id="c6e8e-102">Элемент \<disableCommitThreadStack></span><span class="sxs-lookup"><span data-stu-id="c6e8e-102">\<disableCommitThreadStack> Element</span></span>
<span data-ttu-id="c6e8e-103">Указывает, фиксируется ли весь стек потоков при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-103">Specifies whether the full thread stack is committed when a thread is started.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCommitThreadStack>**  
  
## <a name="syntax"></a><span data-ttu-id="c6e8e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6e8e-104">Syntax</span></span>  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6e8e-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c6e8e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c6e8e-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6e8e-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c6e8e-107">Attributes</span></span>  
  
|<span data-ttu-id="c6e8e-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c6e8e-108">Attribute</span></span>|<span data-ttu-id="c6e8e-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="c6e8e-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c6e8e-110">Включено</span><span class="sxs-lookup"><span data-stu-id="c6e8e-110">enabled</span></span>|<span data-ttu-id="c6e8e-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="c6e8e-112">Указывает, отключена ли фиксация всего стека потоков при запуске потока (режим по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="c6e8e-112">Specifies whether committing the full thread stack on thread startup (the default behavior) is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c6e8e-113">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="c6e8e-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="c6e8e-114">Значение</span><span class="sxs-lookup"><span data-stu-id="c6e8e-114">Value</span></span>|<span data-ttu-id="c6e8e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="c6e8e-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c6e8e-116">0</span><span class="sxs-lookup"><span data-stu-id="c6e8e-116">0</span></span>|<span data-ttu-id="c6e8e-117">Не отключать для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-117">Do not disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
|<span data-ttu-id="c6e8e-118">1</span><span class="sxs-lookup"><span data-stu-id="c6e8e-118">1</span></span>|<span data-ttu-id="c6e8e-119">Отключить для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-119">Disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6e8e-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c6e8e-120">Child Elements</span></span>  
 <span data-ttu-id="c6e8e-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c6e8e-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c6e8e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c6e8e-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="c6e8e-123">Element</span></span>|<span data-ttu-id="c6e8e-124">Описание</span><span class="sxs-lookup"><span data-stu-id="c6e8e-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c6e8e-125">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c6e8e-126">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6e8e-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="c6e8e-127">Remarks</span></span>  
 <span data-ttu-id="c6e8e-128">Режим по умолчанию для среды CLR заключается в фиксации всего стека потоков при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-128">The default behavior of the common language runtime is to commit the full thread stack when a thread is started.</span></span> <span data-ttu-id="c6e8e-129">Если на сервере с ограниченным объемом памяти необходимо создать большое число потоков и большинство из этих потоков будут использовать очень небольшое пространство стека, сервер может работать лучше, если среда не фиксирует весь стек потоков сразу после запуска потока.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-129">If a large number of threads must be created on a server that has limited memory, and most of those threads will use very little stack space, the server might perform better if the common language runtime does not commit the full thread stack immediately when a thread is started.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c6e8e-130">Неуправляемые узлы могут использовать флаг запуска `STARTUP_DISABLE_COMMITTHREADSTACK` в перечислении [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) для достижения такого же результата.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-130">Unmanaged hosts can use the `STARTUP_DISABLE_COMMITTHREADSTACK` startup flag in the [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) enumeration to accomplish the same result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6e8e-131">Пример</span><span class="sxs-lookup"><span data-stu-id="c6e8e-131">Example</span></span>  
 <span data-ttu-id="c6e8e-132">В следующем примере показано, как отключить для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="c6e8e-132">The following example shows how to disable the default behavior of the common language runtime, which is to commit the full thread stack on thread startup.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6e8e-133">См. также</span><span class="sxs-lookup"><span data-stu-id="c6e8e-133">See also</span></span>

- [<span data-ttu-id="c6e8e-134">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="c6e8e-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c6e8e-135">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="c6e8e-135">Configuration File Schema</span></span>](../index.md)
