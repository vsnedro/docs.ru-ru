---
title: Элемент <ThrowUnobservedTaskExceptions>
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
ms.openlocfilehash: de5a686bcbd88fc52173b488103f033575623d62
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153819"
---
# <a name="throwunobservedtaskexceptions-element"></a><span data-ttu-id="46005-102">Элемент \<ThrowUnobservedTaskExceptions></span><span class="sxs-lookup"><span data-stu-id="46005-102">\<ThrowUnobservedTaskExceptions> Element</span></span>
<span data-ttu-id="46005-103">Определяет, будут ли необработанные исключения задачи завершать выполняющийся процесс.</span><span class="sxs-lookup"><span data-stu-id="46005-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<ThrowUnobservedTaskExceptions>**  
  
## <a name="syntax"></a><span data-ttu-id="46005-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46005-104">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46005-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="46005-105">Attributes and Elements</span></span>  
 <span data-ttu-id="46005-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="46005-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46005-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="46005-107">Attributes</span></span>  
  
|<span data-ttu-id="46005-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="46005-108">Attribute</span></span>|<span data-ttu-id="46005-109">Описание</span><span class="sxs-lookup"><span data-stu-id="46005-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="46005-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="46005-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="46005-111">Указывает, должны ли исключения необработанных задач завершать выполняющийся процесс.</span><span class="sxs-lookup"><span data-stu-id="46005-111">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="46005-112">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="46005-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="46005-113">Значение</span><span class="sxs-lookup"><span data-stu-id="46005-113">Value</span></span>|<span data-ttu-id="46005-114">Описание</span><span class="sxs-lookup"><span data-stu-id="46005-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="46005-115">Не завершает выполняющийся процесс для исключения необработанной задачи.</span><span class="sxs-lookup"><span data-stu-id="46005-115">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="46005-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="46005-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="46005-117">Завершает выполняющийся процесс для исключения необработанной задачи.</span><span class="sxs-lookup"><span data-stu-id="46005-117">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="46005-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="46005-118">Child Elements</span></span>  
 <span data-ttu-id="46005-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="46005-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="46005-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="46005-120">Parent Elements</span></span>  
  
|<span data-ttu-id="46005-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="46005-121">Element</span></span>|<span data-ttu-id="46005-122">Описание</span><span class="sxs-lookup"><span data-stu-id="46005-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="46005-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="46005-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="46005-124">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="46005-124">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="46005-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="46005-125">Remarks</span></span>  
 <span data-ttu-id="46005-126">Если исключение, связанное с объектом <xref:System.Threading.Tasks.Task> , не было замечено, то операция отсутствует <xref:System.Threading.Tasks.Task.Wait%2A> , родительский элемент не присоединяется, а <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> свойство не было прочитано, поэтому исключение задачи считается незамеченным.</span><span class="sxs-lookup"><span data-stu-id="46005-126">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="46005-127">В .NET Framework 4, по умолчанию, если <xref:System.Threading.Tasks.Task> исключение, для которого имеется незамеченная исключительная ошибка, уничтожается сборщиком мусора, метод завершения создает исключение и завершает процесс.</span><span class="sxs-lookup"><span data-stu-id="46005-127">In the .NET Framework 4, by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="46005-128">Завершение процесса определяется временем сбора мусора и финализации.</span><span class="sxs-lookup"><span data-stu-id="46005-128">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="46005-129">Чтобы разработчикам было проще писать асинхронный код на основе задач, .NET Framework 4,5 изменяет это поведение по умолчанию для незамеченных исключений.</span><span class="sxs-lookup"><span data-stu-id="46005-129">To make it easier for developers to write asynchronous code based on tasks, the .NET Framework 4.5 changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="46005-130">Незамеченные исключения по-прежнему вызывают <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> событие, но по умолчанию процесс не завершается.</span><span class="sxs-lookup"><span data-stu-id="46005-130">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="46005-131">Вместо этого исключение пропускается после возникновения события, независимо от того, отслеживает ли обработчик событий исключение.</span><span class="sxs-lookup"><span data-stu-id="46005-131">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="46005-132">В .NET Framework 4,5 можно использовать [ \<ThrowUnobservedTaskExceptions> элемент](throwunobservedtaskexceptions-element.md) в файле конфигурации приложения, чтобы обеспечить .NET Framework 4 действия создания исключения.</span><span class="sxs-lookup"><span data-stu-id="46005-132">In the .NET Framework 4.5, you can use the [\<ThrowUnobservedTaskExceptions> element](throwunobservedtaskexceptions-element.md) in an application configuration file to enable the .NET Framework 4 behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="46005-133">Можно также указать поведение исключения одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="46005-133">You can also specify the exception behavior in one of the following ways:</span></span>  
  
- <span data-ttu-id="46005-134">Путем задания переменной среды `COMPlus_ThrowUnobservedTaskExceptions` ( `set COMPlus_ThrowUnobservedTaskExceptions=1` ).</span><span class="sxs-lookup"><span data-stu-id="46005-134">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
- <span data-ttu-id="46005-135">Задав в реестре значение DWORD Сровунобсерведтаскексцептионс = 1 в HKEY_LOCAL_MACHINE \Софтваре\микрософт \\ . Ключ NETFramework.</span><span class="sxs-lookup"><span data-stu-id="46005-135">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46005-136">Пример</span><span class="sxs-lookup"><span data-stu-id="46005-136">Example</span></span>  
 <span data-ttu-id="46005-137">В следующем примере показано, как включить создание исключений в задачах с помощью файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="46005-137">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>
    <runtime>
        <ThrowUnobservedTaskExceptions enabled="true"/>
    </runtime>
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="46005-138">Пример</span><span class="sxs-lookup"><span data-stu-id="46005-138">Example</span></span>  
 <span data-ttu-id="46005-139">В следующем примере показано, как выдается незамеченное исключение из задачи.</span><span class="sxs-lookup"><span data-stu-id="46005-139">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="46005-140">Чтобы правильно работать, код должен быть запущен в качестве выпущенной программы.</span><span class="sxs-lookup"><span data-stu-id="46005-140">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="46005-141">См. также</span><span class="sxs-lookup"><span data-stu-id="46005-141">See also</span></span>

- [<span data-ttu-id="46005-142">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="46005-142">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="46005-143">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="46005-143">Configuration File Schema</span></span>](../index.md)
