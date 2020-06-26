---
title: bindingFailure MDA
description: Ознакомьтесь с помощником по отладке управляемого кода Биндингфаилуре (MDA), который активируется при сбое загрузки сборки в .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- binding failure
- binding, failures
- MDAs (managed debugging assistants), binding failures
- assemblies [.NET Framework], binding failures
- managed debugging assistants (MDAs), binding failures
- BindingFailure MDA
ms.assetid: 26ada5af-175c-4576-931a-9f07fa1723e9
ms.openlocfilehash: 98c7947c7e5d2a1f0af8c26744d3b292ed8cb4c4
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415632"
---
# <a name="bindingfailure-mda"></a><span data-ttu-id="28b8a-103">bindingFailure MDA</span><span class="sxs-lookup"><span data-stu-id="28b8a-103">bindingFailure MDA</span></span>

<span data-ttu-id="28b8a-104">Помощник по отладке управляемого кода (MDA) `bindingFailure` запускается в случае сбоя при загрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="28b8a-104">The `bindingFailure` managed debugging assistant (MDA) is activated when an assembly fails to load.</span></span>

## <a name="symptoms"></a><span data-ttu-id="28b8a-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="28b8a-105">Symptoms</span></span>

<span data-ttu-id="28b8a-106">Код попытался загрузить сборку с использованием статической ссылки или одного из методов загрузчика, такого как <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> или <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="28b8a-106">Code has attempted to load an assembly using a static reference or one of the loader methods, such as <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="28b8a-107">Сборка не загружается, в результате чего возникает исключение <xref:System.IO.FileNotFoundException> или <xref:System.IO.FileLoadException>.</span><span class="sxs-lookup"><span data-stu-id="28b8a-107">The assembly is not loaded and a <xref:System.IO.FileNotFoundException> or <xref:System.IO.FileLoadException> exception is thrown.</span></span>

## <a name="cause"></a><span data-ttu-id="28b8a-108">Причина</span><span class="sxs-lookup"><span data-stu-id="28b8a-108">Cause</span></span>

<span data-ttu-id="28b8a-109">Если среде выполнения не удается загрузить сборку, происходит сбой привязки.</span><span class="sxs-lookup"><span data-stu-id="28b8a-109">A binding failure occurs when the runtime is unable to load an assembly.</span></span> <span data-ttu-id="28b8a-110">Сбой привязки может возникать в одной из следующих ситуаций:</span><span class="sxs-lookup"><span data-stu-id="28b8a-110">A binding failure might be the result of one of the following situations:</span></span>

- <span data-ttu-id="28b8a-111">Общеязыковой среде выполнения (CLR) не удается найти запрошенную сборку.</span><span class="sxs-lookup"><span data-stu-id="28b8a-111">The common language runtime (CLR) cannot find the requested assembly.</span></span> <span data-ttu-id="28b8a-112">Это может быть вызвано самыми разными причинами, например отсутствием установленной сборки или некорректной конфигурацией поиска сборок в приложении.</span><span class="sxs-lookup"><span data-stu-id="28b8a-112">There are many reasons this can occur, such as the assembly not being installed or the application not being correctly configured to find the assembly.</span></span>

- <span data-ttu-id="28b8a-113">Типичный сценарий возникновения проблемы связан с передачей типа в другой домен приложения, которому требуется среда CLR для загрузки сборки, содержащей этот тип, в другом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="28b8a-113">A common problem scenario is passing a type to another application domain, which requires the CLR to load the assembly containing that type in the other application domain.</span></span> <span data-ttu-id="28b8a-114">Если конфигурация другого домена приложения отличается от исходного, при загрузке сборки среда выполнения может столкнуться с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="28b8a-114">It may not be possible for the runtime to load the assembly if the other application domain is configured differently from the original application domain.</span></span> <span data-ttu-id="28b8a-115">Например, в этих двух доменах приложений могут быть установлены разные значения свойства <xref:System.AppDomain.BaseDirectory%2A>.</span><span class="sxs-lookup"><span data-stu-id="28b8a-115">For example, the two application domains might have different <xref:System.AppDomain.BaseDirectory%2A> property values.</span></span>

- <span data-ttu-id="28b8a-116">Запрошенная сборка повреждена или не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="28b8a-116">The requested assembly is corrupted or is not an assembly.</span></span>

- <span data-ttu-id="28b8a-117">Код, который пытается загрузить сборку, не имеет разрешений на управление доступом для кода, необходимых для загрузки сборок.</span><span class="sxs-lookup"><span data-stu-id="28b8a-117">The code attempting to load the assembly does not have the correct code access security permissions to load assemblies.</span></span>

- <span data-ttu-id="28b8a-118">Учетные данные пользователя не предоставляют разрешений, необходимых для чтения файла.</span><span class="sxs-lookup"><span data-stu-id="28b8a-118">The user credentials do not provide the required permissions to read the file.</span></span>

## <a name="resolution"></a><span data-ttu-id="28b8a-119">Решение</span><span class="sxs-lookup"><span data-stu-id="28b8a-119">Resolution</span></span>

<span data-ttu-id="28b8a-120">В первую очередь необходимо определить причины, по которым среде CLR не удается выполнить привязку к запрошенной сборке.</span><span class="sxs-lookup"><span data-stu-id="28b8a-120">The first step is to determine why the CLR could not bind to the requested assembly.</span></span> <span data-ttu-id="28b8a-121">Существует много различных причин, по которым среде выполнения не удается найти или загрузить запрошенную сборку. Некоторые из них перечислены в разделе "Причина".</span><span class="sxs-lookup"><span data-stu-id="28b8a-121">There are many reasons why the runtime might not have found or been able load the requested assembly, such as the scenarios listed in the Cause section.</span></span> <span data-ttu-id="28b8a-122">Чтобы устранить причину сбоя привязки, рекомендуется выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="28b8a-122">The following actions are recommended to eliminate the cause of the binding failure:</span></span>

- <span data-ttu-id="28b8a-123">Определите причину, используя данные, предоставленные помощником по отладке управляемого кода `bindingFailure`:</span><span class="sxs-lookup"><span data-stu-id="28b8a-123">Determine the cause by using the data provided by the `bindingFailure` MDA:</span></span>

  - <span data-ttu-id="28b8a-124">Запустите программу [Fuslogvw.exe (средство просмотра журнала привязки сборок)](../tools/fuslogvw-exe-assembly-binding-log-viewer.md) для чтения журналов ошибок, создаваемых средством привязки сборок.</span><span class="sxs-lookup"><span data-stu-id="28b8a-124">Run the [Fuslogvw.exe (Assembly Binding Log Viewer)](../tools/fuslogvw-exe-assembly-binding-log-viewer.md) to read the error logs produced by the assembly binder.</span></span>

  - <span data-ttu-id="28b8a-125">Определите, находится ли запрошенная сборка в указанном месте.</span><span class="sxs-lookup"><span data-stu-id="28b8a-125">Determine if the assembly is at the location requested.</span></span> <span data-ttu-id="28b8a-126">В случае методов <xref:System.Reflection.Assembly.LoadFrom%2A> и <xref:System.Reflection.Assembly.LoadFile%2A> запрошенное расположение можно легко определить.</span><span class="sxs-lookup"><span data-stu-id="28b8a-126">In the case of the <xref:System.Reflection.Assembly.LoadFrom%2A> and <xref:System.Reflection.Assembly.LoadFile%2A> methods, the requested location can be easily determined.</span></span> <span data-ttu-id="28b8a-127">При использовании метода <xref:System.Reflection.Assembly.Load%2A>, который осуществляет привязку по удостоверению сборки, необходимо определить сборки, соответствующие этому удостоверению, в пути пробы свойства <xref:System.AppDomain.BaseDirectory%2A> домена приложений и глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="28b8a-127">In the case of the <xref:System.Reflection.Assembly.Load%2A> method, which binds using the assembly identity, you must look for assemblies that match that identity in the application domain's <xref:System.AppDomain.BaseDirectory%2A> property probe path and the global assembly cache.</span></span>

- <span data-ttu-id="28b8a-128">Устраните выявленные ранее причины.</span><span class="sxs-lookup"><span data-stu-id="28b8a-128">Resolve the cause based on the preceding determination.</span></span> <span data-ttu-id="28b8a-129">Возможны следующие варианты решения проблемы:</span><span class="sxs-lookup"><span data-stu-id="28b8a-129">Possible resolution options are the following:</span></span>

  - <span data-ttu-id="28b8a-130">Установите запрошенную сборку в глобальный кэш сборок и вызовите</span><span class="sxs-lookup"><span data-stu-id="28b8a-130">Install the requested assembly in the global assembly cache and call the.</span></span> <span data-ttu-id="28b8a-131">метод <xref:System.Reflection.Assembly.Load%2A> для загрузки сборки по удостоверению.</span><span class="sxs-lookup"><span data-stu-id="28b8a-131"><xref:System.Reflection.Assembly.Load%2A> method to load the assembly by identity.</span></span>

  - <span data-ttu-id="28b8a-132">Скопируйте запрошенную сборку в каталог приложения и вызовите метод <xref:System.Reflection.Assembly.Load%2A> для загрузки сборки по удостоверению.</span><span class="sxs-lookup"><span data-stu-id="28b8a-132">Copy the requested assembly into the application directory and call the <xref:System.Reflection.Assembly.Load%2A> method to load the assembly by identity.</span></span>

  - <span data-ttu-id="28b8a-133">Измените конфигурацию домена приложения, в котором произошел сбой привязки, включив в нее путь к сборке. Для этого измените значение свойства <xref:System.AppDomain.BaseDirectory%2A> или добавьте частные пути пробы.</span><span class="sxs-lookup"><span data-stu-id="28b8a-133">Reconfigure the application domain in which the binding failure occurred to include the assembly path by either changing the <xref:System.AppDomain.BaseDirectory%2A> property or adding private probing paths.</span></span>

  - <span data-ttu-id="28b8a-134">Измените список управления доступом и разрешите чтение файла для выполнивших вход пользователей.</span><span class="sxs-lookup"><span data-stu-id="28b8a-134">Change the access control list for the file to allow the logged-on user to read the file.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="28b8a-135">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="28b8a-135">Effect on the Runtime</span></span>

<span data-ttu-id="28b8a-136">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="28b8a-136">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="28b8a-137">Он только создает отчеты о сбоях привязки.</span><span class="sxs-lookup"><span data-stu-id="28b8a-137">It only reports data about binding failures.</span></span>

## <a name="output"></a><span data-ttu-id="28b8a-138">Вывод</span><span class="sxs-lookup"><span data-stu-id="28b8a-138">Output</span></span>

<span data-ttu-id="28b8a-139">Этот помощник по отладке управляемого кода создает отчет о сбое при загрузке сборок, в который включаются запрошенный путь и (или) отображаемое имя, контекст привязки, домен приложения, в котором была запрошена загрузка, а также причина сбоя.</span><span class="sxs-lookup"><span data-stu-id="28b8a-139">The MDA reports the assembly that failed to load, including the requested path and/or display name, the binding context, the application domain in which the load was requested, and the reason for the failure.</span></span>

<span data-ttu-id="28b8a-140">Если среде CLR недоступны соответствующие данные, отображаемое имя и запрошенный путь могут быть пустыми.</span><span class="sxs-lookup"><span data-stu-id="28b8a-140">The display name or requested path may be blank if that data was not available to the CLR.</span></span> <span data-ttu-id="28b8a-141">Если сбоем завершается вызов метода <xref:System.Reflection.Assembly.Load%2A>, чаще всего среде выполнения не удается определить отображаемое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="28b8a-141">If the call that failed was to the <xref:System.Reflection.Assembly.Load%2A> method, it is likely the runtime could not determine the display name for the assembly.</span></span>

## <a name="configuration"></a><span data-ttu-id="28b8a-142">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="28b8a-142">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <bindingFailure />
  </assistants>
</mdaConfig>
```

## <a name="example"></a><span data-ttu-id="28b8a-143">Пример</span><span class="sxs-lookup"><span data-stu-id="28b8a-143">Example</span></span>

<span data-ttu-id="28b8a-144">В следующем примере кода показана ситуация, которая может привести к запуску помощника по отладке управляемого кода:</span><span class="sxs-lookup"><span data-stu-id="28b8a-144">The following code example demonstrates a situation that can activate this MDA:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.Reflection;
namespace ConsoleApplication1
{
    class Program
    {
        static void Main(string[] args)
        {
            // This call attempts to load a nonexistent assembly.
            // The call will throw a System.IO.FileNotFound exception
            // and cause the activation of the bindingFailure MDA
            // if it is registered.
            Assembly.Load("NonExistentAssembly");
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="28b8a-145">См. также</span><span class="sxs-lookup"><span data-stu-id="28b8a-145">See also</span></span>

- [<span data-ttu-id="28b8a-146">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="28b8a-146">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
