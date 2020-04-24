---
title: Практическое руководство. Создание политики издателя
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 7c36f6126f0d779a43a22fc11e647ba2d3b03a30
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646058"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="2932a-102">Практическое руководство. Создание политики издателя</span><span class="sxs-lookup"><span data-stu-id="2932a-102">How to: Create a Publisher Policy</span></span>

<span data-ttu-id="2932a-103">Поставщики сборок могут указать, что приложения должны использовать более новую версию сборки, включив файл политики издателя в обновленную сборку.</span><span class="sxs-lookup"><span data-stu-id="2932a-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="2932a-104">Файл политики издателя определяет настройки перенаправления сборки и базы кода и использует тот же формат, что и файл конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="2932a-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="2932a-105">Файл политики издателя компилируется в сборку и помещается в кэш глобальной сборки.</span><span class="sxs-lookup"><span data-stu-id="2932a-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>

<span data-ttu-id="2932a-106">Существует три этапа создания политики издателя:</span><span class="sxs-lookup"><span data-stu-id="2932a-106">There are three steps involved in creating a publisher policy:</span></span>

1. <span data-ttu-id="2932a-107">Создайте файл политики издателя.</span><span class="sxs-lookup"><span data-stu-id="2932a-107">Create a publisher policy file.</span></span>

2. <span data-ttu-id="2932a-108">Создание сборки политики издателя.</span><span class="sxs-lookup"><span data-stu-id="2932a-108">Create a publisher policy assembly.</span></span>

3. <span data-ttu-id="2932a-109">Добавьте сборку политики издателя в кэш глобальной сборки.</span><span class="sxs-lookup"><span data-stu-id="2932a-109">Add the publisher policy assembly to the global assembly cache.</span></span>

<span data-ttu-id="2932a-110">Схема политики издателя описана в [перенаправлении версий сборки.](redirect-assembly-versions.md)</span><span class="sxs-lookup"><span data-stu-id="2932a-110">The schema for publisher policy is described in [Redirecting Assembly Versions](redirect-assembly-versions.md).</span></span> <span data-ttu-id="2932a-111">В следующем примере показан файл политики издателя, который перенаправляет одну версию `myAssembly` в другую.</span><span class="sxs-lookup"><span data-stu-id="2932a-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
       <dependentAssembly>
         <assemblyIdentity name="myAssembly"
                           publicKeyToken="32ab4ba45e0a69a1"
                           culture="en-us" />
         <!-- Redirecting to version 2.0.0.0 of the assembly. -->
         <bindingRedirect oldVersion="1.0.0.0"
                          newVersion="2.0.0.0"/>
       </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

<span data-ttu-id="2932a-112">Чтобы узнать, как указать базу кода, [см.](specify-assembly-location.md)</span><span class="sxs-lookup"><span data-stu-id="2932a-112">To learn how to specify a code base, see [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>

## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="2932a-113">Создание Собрания политики издателей</span><span class="sxs-lookup"><span data-stu-id="2932a-113">Creating the Publisher Policy Assembly</span></span>

<span data-ttu-id="2932a-114">Используйте [сборку Linker (Al.exe)](../tools/al-exe-assembly-linker.md) для создания сборки политики издателя.</span><span class="sxs-lookup"><span data-stu-id="2932a-114">Use the [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>

#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="2932a-115">Создание сборки политики издателя</span><span class="sxs-lookup"><span data-stu-id="2932a-115">To create a publisher policy assembly</span></span>

<span data-ttu-id="2932a-116">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2932a-116">Type the following command at the command prompt:</span></span>

```console
al /link:publisherPolicyFile /out:publisherPolicyAssemblyFile /keyfile:keyPairFile /platform:processorArchitecture
```

<span data-ttu-id="2932a-117">В этой команде:</span><span class="sxs-lookup"><span data-stu-id="2932a-117">In this command:</span></span>

- <span data-ttu-id="2932a-118">Аргументом `publisherPolicyFile` является название файла политики издателя.</span><span class="sxs-lookup"><span data-stu-id="2932a-118">The `publisherPolicyFile` argument is the name of the publisher policy file.</span></span>

- <span data-ttu-id="2932a-119">Аргументом `publisherPolicyAssemblyFile` является название собрания политики издателя, которое является результатом этой команды.</span><span class="sxs-lookup"><span data-stu-id="2932a-119">The `publisherPolicyAssemblyFile` argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="2932a-120">Имя файла сборки должно следовать формату:</span><span class="sxs-lookup"><span data-stu-id="2932a-120">The assembly file name must follow the format:</span></span>

  <span data-ttu-id="2932a-121">'policy.majorNumber.minorNumber.mainAssemblyName.dll'</span><span class="sxs-lookup"><span data-stu-id="2932a-121">\`policy.majorNumber.minorNumber.mainAssemblyName.dll'</span></span>

- <span data-ttu-id="2932a-122">Аргументом `keyPairFile` является название файла, содержащего пару ключей.</span><span class="sxs-lookup"><span data-stu-id="2932a-122">The `keyPairFile` argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="2932a-123">Необходимо подписать собрание политики сборки сборки и издателя одной и той же ключевой парой.</span><span class="sxs-lookup"><span data-stu-id="2932a-123">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>

- <span data-ttu-id="2932a-124">Аргумент `processorArchitecture` определяет платформу, ориентированную на сборку, предназначенную для процессора.</span><span class="sxs-lookup"><span data-stu-id="2932a-124">The `processorArchitecture` argument identifies the platform targeted by a processor-specific assembly.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2932a-125">Возможность таргетинга на конкретную архитектуру процессора доступна начиная с .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="2932a-125">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span>

<span data-ttu-id="2932a-126">Возможность таргетинга на конкретную архитектуру процессора доступна начиная с .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="2932a-126">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span> <span data-ttu-id="2932a-127">Следующая команда создает сборку `policy.1.0.myAssembly` политики издателя, вызванную из файла политики издателя, называемого, `pub.config`присваивая сильное имя сборке с помощью пары ключей в `sgKey.snk` файле, и указывает, что сборка нацелена на архитектуру процессора x86.</span><span class="sxs-lookup"><span data-stu-id="2932a-127">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>

```console
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

<span data-ttu-id="2932a-128">Сборка политики издателя должна соответствовать архитектуре процессора сборки, к которым она применяется.</span><span class="sxs-lookup"><span data-stu-id="2932a-128">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="2932a-129">Таким образом, если <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> ваша <xref:System.Reflection.ProcessorArchitecture.MSIL>сборка имеет ценность, сборка политики издателя для этой сборки должна быть создана с `/platform:anycpu`помощью.</span><span class="sxs-lookup"><span data-stu-id="2932a-129">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="2932a-130">Необходимо предоставить отдельную сборку политики издателя для каждой сборки, конкретной для процессора.</span><span class="sxs-lookup"><span data-stu-id="2932a-130">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>

<span data-ttu-id="2932a-131">Следствием этого правила является то, что для изменения архитектуры процессора для сборки необходимо изменить основной или незначительный компонент номера версии, чтобы можно было поставить новую сборку политики издателя с правильной архитектурой процессора.</span><span class="sxs-lookup"><span data-stu-id="2932a-131">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="2932a-132">Старая сборка политики издателя не может обслуживать сборку, как только сборка имеет другую архитектуру процессора.</span><span class="sxs-lookup"><span data-stu-id="2932a-132">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>

<span data-ttu-id="2932a-133">Другим последствием является то, что ссылка версии 2.0 не может быть использована для создания сборки политики издателя для сборки, компиляции, составленной с использованием более ранних версий рамочного значения .NET, поскольку она всегда определяет архитектуру процессора.</span><span class="sxs-lookup"><span data-stu-id="2932a-133">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="2932a-134">Добавление Собрания по политике издателей в кэш Глобальной ассамблеи</span><span class="sxs-lookup"><span data-stu-id="2932a-134">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>

<span data-ttu-id="2932a-135">Используйте [инструмент Глобального кэша собраний (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) для добавления сборки политики издателя в кэш глобальной сборки.</span><span class="sxs-lookup"><span data-stu-id="2932a-135">Use the [Global Assembly Cache tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="2932a-136">Добавление сборки политики издателя в глобальный кэш сборки</span><span class="sxs-lookup"><span data-stu-id="2932a-136">To add the publisher policy assembly to the global assembly cache</span></span>

<span data-ttu-id="2932a-137">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2932a-137">Type the following command at the command prompt:</span></span>

```console
gacutil /i publisherPolicyAssemblyFile
```

<span data-ttu-id="2932a-138">Следующая команда `policy.1.0.myAssembly.dll` добавляет к глобальному кэшу сборки.</span><span class="sxs-lookup"><span data-stu-id="2932a-138">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>

```console
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> <span data-ttu-id="2932a-139">Сборка политики издателя не может быть добавлена в кэш `/link` глобальной сборки, если исходный файл политики издателя, указанный в аргументе, не находится в том же каталоге, что и сборка.</span><span class="sxs-lookup"><span data-stu-id="2932a-139">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file specified in the `/link` argument is located in the same directory as the assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="2932a-140">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2932a-140">See also</span></span>

- [<span data-ttu-id="2932a-141">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="2932a-141">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="2932a-142">Как Время выполнения находит сборки</span><span class="sxs-lookup"><span data-stu-id="2932a-142">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="2932a-143">Настройка приложений с использованием файлов конфигурации</span><span class="sxs-lookup"><span data-stu-id="2932a-143">Configuring Apps by using Configuration Files</span></span>](index.md)
- [<span data-ttu-id="2932a-144">Схема настройки выполнения</span><span class="sxs-lookup"><span data-stu-id="2932a-144">Runtime Settings Schema</span></span>](./file-schema/runtime/index.md)
- [<span data-ttu-id="2932a-145">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="2932a-145">Configuration File Schema</span></span>](./file-schema/index.md)
- [<span data-ttu-id="2932a-146">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="2932a-146">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)
