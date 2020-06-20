---
title: Практическое руководство. Создание политики издателя
description: Узнайте, как поставщики сборок могут создать файл политики издателя с обновленной сборкой в .NET, чтобы указать, что приложения должны использовать более новую версию.
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 23e9d8144ec5742e0371d566b7af59dc9dd30c9b
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105406"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="8d00e-103">Практическое руководство. Создание политики издателя</span><span class="sxs-lookup"><span data-stu-id="8d00e-103">How to: Create a Publisher Policy</span></span>

<span data-ttu-id="8d00e-104">Поставщики сборок могут указать, что приложения должны использовать более новую версию сборки, включив файл политики издателя с обновленной сборкой.</span><span class="sxs-lookup"><span data-stu-id="8d00e-104">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="8d00e-105">Файл политики издателя определяет параметры перенаправления сборок и базы кода, а также использует тот же формат, что и файл конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="8d00e-105">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="8d00e-106">Файл политики издателя компилируется в сборку и помещается в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="8d00e-106">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>

<span data-ttu-id="8d00e-107">Создание политики издателя состоит из трех этапов.</span><span class="sxs-lookup"><span data-stu-id="8d00e-107">There are three steps involved in creating a publisher policy:</span></span>

1. <span data-ttu-id="8d00e-108">Создайте файл политики издателя.</span><span class="sxs-lookup"><span data-stu-id="8d00e-108">Create a publisher policy file.</span></span>

2. <span data-ttu-id="8d00e-109">Создание сборки политики издателя.</span><span class="sxs-lookup"><span data-stu-id="8d00e-109">Create a publisher policy assembly.</span></span>

3. <span data-ttu-id="8d00e-110">Добавьте сборку политики издателя в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="8d00e-110">Add the publisher policy assembly to the global assembly cache.</span></span>

<span data-ttu-id="8d00e-111">Схема для политики издателя описана в разделе [Перенаправление версий сборки](redirect-assembly-versions.md).</span><span class="sxs-lookup"><span data-stu-id="8d00e-111">The schema for publisher policy is described in [Redirecting Assembly Versions](redirect-assembly-versions.md).</span></span> <span data-ttu-id="8d00e-112">В следующем примере показан файл политики издателя, который перенаправляет одну версию `myAssembly` на другую.</span><span class="sxs-lookup"><span data-stu-id="8d00e-112">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>

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

<span data-ttu-id="8d00e-113">Сведения о том, как указать базу кода, см. в разделе [Указание расположения сборки](specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="8d00e-113">To learn how to specify a code base, see [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>

## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="8d00e-114">Создание сборки политики издателя</span><span class="sxs-lookup"><span data-stu-id="8d00e-114">Creating the Publisher Policy Assembly</span></span>

<span data-ttu-id="8d00e-115">Используйте [Компоновщик сборок (Al.exe)](../tools/al-exe-assembly-linker.md) для создания сборки политики издателя.</span><span class="sxs-lookup"><span data-stu-id="8d00e-115">Use the [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>

#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="8d00e-116">Создание сборки политики издателя</span><span class="sxs-lookup"><span data-stu-id="8d00e-116">To create a publisher policy assembly</span></span>

<span data-ttu-id="8d00e-117">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8d00e-117">Type the following command at the command prompt:</span></span>

```console
al /link:publisherPolicyFile /out:publisherPolicyAssemblyFile /keyfile:keyPairFile /platform:processorArchitecture
```

<span data-ttu-id="8d00e-118">В этой команде:</span><span class="sxs-lookup"><span data-stu-id="8d00e-118">In this command:</span></span>

- <span data-ttu-id="8d00e-119">`publisherPolicyFile`Аргумент — это имя файла политики издателя.</span><span class="sxs-lookup"><span data-stu-id="8d00e-119">The `publisherPolicyFile` argument is the name of the publisher policy file.</span></span>

- <span data-ttu-id="8d00e-120">`publisherPolicyAssemblyFile`Аргумент — это имя сборки политики издателя, полученное в результате выполнения этой команды.</span><span class="sxs-lookup"><span data-stu-id="8d00e-120">The `publisherPolicyAssemblyFile` argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="8d00e-121">Имя файла сборки должно соответствовать формату:</span><span class="sxs-lookup"><span data-stu-id="8d00e-121">The assembly file name must follow the format:</span></span>

  <span data-ttu-id="8d00e-122">"policy.majorNumber.minorNumber.mainAssemblyName.dll"</span><span class="sxs-lookup"><span data-stu-id="8d00e-122">\`policy.majorNumber.minorNumber.mainAssemblyName.dll'</span></span>

- <span data-ttu-id="8d00e-123">`keyPairFile`Аргумент — это имя файла, содержащего пару ключей.</span><span class="sxs-lookup"><span data-stu-id="8d00e-123">The `keyPairFile` argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="8d00e-124">Сборку политики сборки и издателя необходимо подписать с помощью той же пары ключей.</span><span class="sxs-lookup"><span data-stu-id="8d00e-124">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>

- <span data-ttu-id="8d00e-125">`processorArchitecture`Аргумент определяет платформу, на которую ссылается сборка для конкретного процессора.</span><span class="sxs-lookup"><span data-stu-id="8d00e-125">The `processorArchitecture` argument identifies the platform targeted by a processor-specific assembly.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8d00e-126">Возможность ориентироваться на конкретную архитектуру процессора доступна начиная с .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="8d00e-126">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span>

<span data-ttu-id="8d00e-127">Возможность ориентироваться на конкретную архитектуру процессора доступна начиная с .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="8d00e-127">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span> <span data-ttu-id="8d00e-128">Следующая команда создает сборку политики издателя `policy.1.0.myAssembly` с именем из файла политики издателя `pub.config` , присваивает сборке строгое имя, используя пару ключей в `sgKey.snk` файле, и указывает, что сборка предназначена для архитектуры процессора x86.</span><span class="sxs-lookup"><span data-stu-id="8d00e-128">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>

```console
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

<span data-ttu-id="8d00e-129">Сборка политики издателя должна соответствовать архитектуре процессора сборки, к которой он применяется.</span><span class="sxs-lookup"><span data-stu-id="8d00e-129">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="8d00e-130">Таким же, если сборка имеет <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> значение <xref:System.Reflection.ProcessorArchitecture.MSIL> , сборка политики издателя для этой сборки должна быть создана с помощью `/platform:anycpu` .</span><span class="sxs-lookup"><span data-stu-id="8d00e-130">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="8d00e-131">Для каждой сборки конкретного процессора необходимо предоставить отдельную сборку политики издателя.</span><span class="sxs-lookup"><span data-stu-id="8d00e-131">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>

<span data-ttu-id="8d00e-132">Следствием этого правила является то, что для изменения архитектуры процессора для сборки необходимо изменить основной или дополнительный компонент номера версии, чтобы можно было указать новую сборку политики издателя с правильной архитектурой процессора.</span><span class="sxs-lookup"><span data-stu-id="8d00e-132">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="8d00e-133">Старая сборка политики издателя не может обслуживать сборку, если сборка имеет другую архитектуру процессора.</span><span class="sxs-lookup"><span data-stu-id="8d00e-133">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>

<span data-ttu-id="8d00e-134">Другой следствием является то, что компоновщик версии 2,0 нельзя использовать для создания сборки политики издателя для сборки, скомпилированной с помощью более ранних версий .NET Framework, так как она всегда определяет архитектуру процессора.</span><span class="sxs-lookup"><span data-stu-id="8d00e-134">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="8d00e-135">Добавление сборки политики издателя в глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="8d00e-135">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>

<span data-ttu-id="8d00e-136">Используйте [средство глобального кэша сборок (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) , чтобы добавить сборку политики издателя в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="8d00e-136">Use the [Global Assembly Cache tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="8d00e-137">Добавление сборки политики издателя в глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="8d00e-137">To add the publisher policy assembly to the global assembly cache</span></span>

<span data-ttu-id="8d00e-138">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8d00e-138">Type the following command at the command prompt:</span></span>

```console
gacutil /i publisherPolicyAssemblyFile
```

<span data-ttu-id="8d00e-139">Следующая команда добавляет `policy.1.0.myAssembly.dll` в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="8d00e-139">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>

```console
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> <span data-ttu-id="8d00e-140">Сборку политики издателя нельзя добавить в глобальный кэш сборок, если исходный файл политики издателя, указанный в `/link` аргументе, не находится в том же каталоге, что и сборка.</span><span class="sxs-lookup"><span data-stu-id="8d00e-140">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file specified in the `/link` argument is located in the same directory as the assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d00e-141">См. также</span><span class="sxs-lookup"><span data-stu-id="8d00e-141">See also</span></span>

- [<span data-ttu-id="8d00e-142">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="8d00e-142">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="8d00e-143">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="8d00e-143">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="8d00e-144">Настройка приложений с использованием файлов конфигурации</span><span class="sxs-lookup"><span data-stu-id="8d00e-144">Configuring Apps by using Configuration Files</span></span>](index.md)
- [<span data-ttu-id="8d00e-145">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="8d00e-145">Runtime Settings Schema</span></span>](./file-schema/runtime/index.md)
- [<span data-ttu-id="8d00e-146">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="8d00e-146">Configuration File Schema</span></span>](./file-schema/index.md)
- [<span data-ttu-id="8d00e-147">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="8d00e-147">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)
