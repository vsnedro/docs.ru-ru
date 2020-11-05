---
title: Практическое руководство. Подписывание сборки строгим именем
description: В этой статье показано, как подписать сборку .NET с использованием строгого имени с помощью вкладки "Подписывание", компоновщика сборок, атрибутов сборки или параметров компилятора.
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, signing with strong names
- signing assemblies
- assemblies [.NET], signing
- assemblies [.NET], strong-named
ms.assetid: 2c30799a-a826-46b4-a25d-c584027a6c67
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 5192f7f372b9ef7927930c3599aebc6fca9f1f0f
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687651"
---
# <a name="how-to-sign-an-assembly-with-a-strong-name"></a><span data-ttu-id="0c312-103">Практическое руководство. Подписывание сборки строгим именем</span><span class="sxs-lookup"><span data-stu-id="0c312-103">How to: Sign an assembly with a strong name</span></span>

> [!NOTE]
> <span data-ttu-id="0c312-104">Хотя .NET Core поддерживает сборки со строгими именами и все сборки в библиотеке .NET Core подписаны, большинству сборок сторонних разработчиков строгие имена не требуются.</span><span class="sxs-lookup"><span data-stu-id="0c312-104">Although .NET Core supports strong-named assemblies, and all assemblies in the .NET Core library are signed, the majority of third-party assemblies do not need strong names.</span></span> <span data-ttu-id="0c312-105">Дополнительные сведения см. в разделе [Подпись строгим именем](https://github.com/dotnet/runtime/blob/master/docs/project/strong-name-signing.md) в GitHub.</span><span class="sxs-lookup"><span data-stu-id="0c312-105">For more information, see [Strong Name Signing](https://github.com/dotnet/runtime/blob/master/docs/project/strong-name-signing.md) on GitHub.</span></span>

<span data-ttu-id="0c312-106">Существует несколько способов подписать сборку строгим именем:</span><span class="sxs-lookup"><span data-stu-id="0c312-106">There are a number of ways to sign an assembly with a strong name:</span></span>  
  
- <span data-ttu-id="0c312-107">С использованием **Подписывание** в диалоговом окне **Свойства** проекта в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0c312-107">By using the **Signing** tab in a project's **Properties** dialog box in Visual Studio.</span></span> <span data-ttu-id="0c312-108">Это самый простой и удобный способ подписать сборку строгим именем.</span><span class="sxs-lookup"><span data-stu-id="0c312-108">This is the easiest and most convenient way to sign an assembly with a strong name.</span></span>  
  
- <span data-ttu-id="0c312-109">С использованием [компоновщика сборок (Al.exe)](../../framework/tools/al-exe-assembly-linker.md), который связывает модуль кода .NET Framework ( *NETMODULE* -файл) с файлом ключа.</span><span class="sxs-lookup"><span data-stu-id="0c312-109">By using the [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) to link a .NET Framework code module (a *.netmodule* file) with a key file.</span></span>  
  
- <span data-ttu-id="0c312-110">С использованием атрибутов сборки, позволяющих вставить в код данные строгого имени.</span><span class="sxs-lookup"><span data-stu-id="0c312-110">By using assembly attributes to insert the strong name information into your code.</span></span> <span data-ttu-id="0c312-111">Можно использовать либо <xref:System.Reflection.AssemblyKeyFileAttribute> , либо <xref:System.Reflection.AssemblyKeyNameAttribute> в зависимости от того, где находится используемый файл ключа.</span><span class="sxs-lookup"><span data-stu-id="0c312-111">You can use either the <xref:System.Reflection.AssemblyKeyFileAttribute> or the <xref:System.Reflection.AssemblyKeyNameAttribute> attribute, depending on where the key file to be used is located.</span></span>  
  
- <span data-ttu-id="0c312-112">С использованием параметров компилятора.</span><span class="sxs-lookup"><span data-stu-id="0c312-112">By using compiler options.</span></span>  
  
 <span data-ttu-id="0c312-113">Для подписи сборки строгим именем необходимо иметь пару ключей шифрования.</span><span class="sxs-lookup"><span data-stu-id="0c312-113">You must have a cryptographic key pair to sign an assembly with a strong name.</span></span> <span data-ttu-id="0c312-114">Дополнительные сведения о создании пары ключей см. в разделе [Практическое руководство. Создание пары открытого и закрытого ключей](create-public-private-key-pair.md).</span><span class="sxs-lookup"><span data-stu-id="0c312-114">For more information about creating a key pair, see [How to: Create a public-private key pair](create-public-private-key-pair.md).</span></span>  
  
## <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-visual-studio"></a><span data-ttu-id="0c312-115">Создание и подпись сборки строгим именем с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0c312-115">Create and sign an assembly with a strong name by using Visual Studio</span></span>  
  
1. <span data-ttu-id="0c312-116">В **обозревателе решений** откройте контекстное меню проекта и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="0c312-116">In **Solution Explorer** , open the shortcut menu for the project, and then choose **Properties**.</span></span>  
  
2. <span data-ttu-id="0c312-117">Перейдите на вкладку **Подписывание** .</span><span class="sxs-lookup"><span data-stu-id="0c312-117">Choose the **Signing** tab.</span></span>  
  
3. <span data-ttu-id="0c312-118">Выберите поле **Подписать сборку** .</span><span class="sxs-lookup"><span data-stu-id="0c312-118">Select the **Sign the assembly** box.</span></span>  
  
4. <span data-ttu-id="0c312-119">В поле **Выберите файл ключа строгого имени** нажмите кнопку **Обзор** , после чего выберите файл ключа.</span><span class="sxs-lookup"><span data-stu-id="0c312-119">In the **Choose a strong name key file** box, choose **Browse** , and then navigate to the key file.</span></span> <span data-ttu-id="0c312-120">Чтобы создать файл ключа, выберите **Создать** и введите его имя в диалоговом окне **Создание ключа строгого имени**.</span><span class="sxs-lookup"><span data-stu-id="0c312-120">To create a new key file, choose **New** and enter its name in the **Create Strong Name Key** dialog box.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c312-121">Чтобы [отложить подпись сборки](delay-sign.md), выберите файл открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="0c312-121">In order to [delay sign an assembly](delay-sign.md), choose a public key file.</span></span>  
  
### <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-the-assembly-linker"></a><span data-ttu-id="0c312-122">Создание и подпись сборки строгим именем с помощью компоновщика сборок</span><span class="sxs-lookup"><span data-stu-id="0c312-122">Create and sign an assembly with a strong name by using the Assembly Linker</span></span>  
  
<span data-ttu-id="0c312-123">В [командной строке разработчика для Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md) введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0c312-123">At the [Developer Command Prompt for Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), enter the following command:</span></span>  

<span data-ttu-id="0c312-124">**al** **/out:** \<*assemblyName*> *\<moduleName>* **/keyfile:** \<*keyfileName*></span><span class="sxs-lookup"><span data-stu-id="0c312-124">**al** **/out:**\<*assemblyName*> *\<moduleName>* **/keyfile:**\<*keyfileName*></span></span>  

<span data-ttu-id="0c312-125">Где:</span><span class="sxs-lookup"><span data-stu-id="0c312-125">Where:</span></span>  

- <span data-ttu-id="0c312-126">*assemblyName* — это имя строго подписанной сборки (файл *DLL* или *EXE* ), которая будет создана компоновщиком сборок.</span><span class="sxs-lookup"><span data-stu-id="0c312-126">*assemblyName* is the name of the strongly signed assembly (a *.dll* or *.exe* file) that Assembly Linker will emit.</span></span>  
  
- <span data-ttu-id="0c312-127">*moduleName* — это имя модуля кода .NET Framework ( *NETMODULE* -файла), который содержит один или несколько типов.</span><span class="sxs-lookup"><span data-stu-id="0c312-127">*moduleName* is the name of a .NET Framework code module (a *.netmodule* file) that includes one or more types.</span></span> <span data-ttu-id="0c312-128">*NETMODULE* -файл можно создать путем компиляции кода с параметром `/target:module` в C# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0c312-128">You can create a *.netmodule* file by compiling your code with the `/target:module` switch in C# or Visual Basic.</span></span>
  
- <span data-ttu-id="0c312-129">*keyfileName* — это имя контейнера или файла, содержащего пару ключей.</span><span class="sxs-lookup"><span data-stu-id="0c312-129">*keyfileName* is the name of the container or file that contains the key pair.</span></span> <span data-ttu-id="0c312-130">Компоновщик сборок интерпретирует относительный путь с точки зрения текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="0c312-130">Assembly Linker interprets a relative path in relation to the current directory.</span></span>  

<span data-ttu-id="0c312-131">Следующий пример подписывает сборку *MyAssembly.dll* строгим именем с помощью файла ключа *sgKey.snk*.</span><span class="sxs-lookup"><span data-stu-id="0c312-131">The following example signs the assembly *MyAssembly.dll* with a strong name by using the key file *sgKey.snk*.</span></span>  

```console
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  
```  
  
<span data-ttu-id="0c312-132">Дополнительные сведения об использовании этого инструмента см. в разделе [Компоновщик сборок](../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="0c312-132">For more information about this tool, see [Assembly Linker](../../framework/tools/al-exe-assembly-linker.md).</span></span>  
  
## <a name="sign-an-assembly-with-a-strong-name-by-using-attributes"></a><span data-ttu-id="0c312-133">Подпись сборки строгим именем с помощью атрибутов</span><span class="sxs-lookup"><span data-stu-id="0c312-133">Sign an assembly with a strong name by using attributes</span></span>  
  
1. <span data-ttu-id="0c312-134">Добавьте <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> или <xref:System.Reflection.AssemblyKeyNameAttribute> в файл исходного кода и укажите имя файла или контейнера, содержащего пару ключей, которая используется при подписи сборки строгим именем.</span><span class="sxs-lookup"><span data-stu-id="0c312-134">Add the <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute to your source code file, and specify the name of the file or container that contains the key pair to use when signing the assembly with a strong name.</span></span>  

2. <span data-ttu-id="0c312-135">Компилируйте файл исходного кода в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="0c312-135">Compile the source code file normally.</span></span>  

   > [!NOTE]
   > <span data-ttu-id="0c312-136">Компиляторы C# и Visual Basic выдают предупреждения (CS1699 и BC41008, соответственно), если в исходном коде встречается <xref:System.Reflection.AssemblyKeyFileAttribute> или <xref:System.Reflection.AssemblyKeyNameAttribute> .</span><span class="sxs-lookup"><span data-stu-id="0c312-136">The C# and Visual Basic compilers issue compiler warnings (CS1699 and BC41008, respectively) when they encounter the <xref:System.Reflection.AssemblyKeyFileAttribute> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute in source code.</span></span> <span data-ttu-id="0c312-137">Эти предупреждения можно игнорировать.</span><span class="sxs-lookup"><span data-stu-id="0c312-137">You can ignore the warnings.</span></span>  

<span data-ttu-id="0c312-138">В следующем примере кода используется атрибут <xref:System.Reflection.AssemblyKeyFileAttribute> с файлом ключа *keyfile.snk* , который находится в том же каталоге, где компилируется сборка.</span><span class="sxs-lookup"><span data-stu-id="0c312-138">The following example uses the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute with a key file called *keyfile.snk* , which is located in the directory where the assembly is compiled.</span></span>  

```cpp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")];
```

```csharp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")]
```

```vb
<Assembly:AssemblyKeyFileAttribute("keyfile.snk")>
```

<span data-ttu-id="0c312-139">Кроме того, при компиляции исходного файла можно использовать отложенную подпись.</span><span class="sxs-lookup"><span data-stu-id="0c312-139">You can also delay sign an assembly when compiling your source file.</span></span> <span data-ttu-id="0c312-140">Дополнительные сведения см. в разделе [Отложенная подпись сборки](delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="0c312-140">For more information, see [Delay-sign an assembly](delay-sign.md).</span></span>  

## <a name="sign-an-assembly-with-a-strong-name-by-using-the-compiler"></a><span data-ttu-id="0c312-141">Подпись сборки строгим именем с использованием компилятора</span><span class="sxs-lookup"><span data-stu-id="0c312-141">Sign an assembly with a strong name by using the compiler</span></span>  

<span data-ttu-id="0c312-142">Компилируйте файлы исходного кода с помощью параметра компилятора `/keyfile` или `/delaysign` в C# и Visual Basic либо параметра компоновщика `/KEYFILE` или `/DELAYSIGN` в C++.</span><span class="sxs-lookup"><span data-stu-id="0c312-142">Compile your source code file or files with the `/keyfile` or `/delaysign` compiler option in C# and Visual Basic, or the `/KEYFILE` or `/DELAYSIGN` linker option in C++.</span></span> <span data-ttu-id="0c312-143">После имени параметра добавьте двоеточие и имя файла ключей.</span><span class="sxs-lookup"><span data-stu-id="0c312-143">After the option name, add a colon and the name of the key file.</span></span> <span data-ttu-id="0c312-144">При использовании компиляторов, работающих в режиме командной строки, можно скопировать файл ключей в каталог, содержащий файлы исходного кода.</span><span class="sxs-lookup"><span data-stu-id="0c312-144">When using command-line compilers, you can copy the key file to the directory that contains your source code files.</span></span>  

<span data-ttu-id="0c312-145">Подробные сведения об отложенной подписи см. в разделе [Отложенная подпись сборки](delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="0c312-145">For information on delay signing, see [Delay-sign an assembly](delay-sign.md).</span></span>  

<span data-ttu-id="0c312-146">В следующем примере используется компилятор C# и сборка *UtilityLibrary.dll* подписывается строгим именем с помощью файла ключа *sgKey.snk*.</span><span class="sxs-lookup"><span data-stu-id="0c312-146">The following example uses the C# compiler and signs the assembly *UtilityLibrary.dll* with a strong name by using the key file *sgKey.snk*.</span></span>  

```cmd
csc /t:library UtilityLibrary.cs /keyfile:sgKey.snk  
```  

## <a name="see-also"></a><span data-ttu-id="0c312-147">См. также</span><span class="sxs-lookup"><span data-stu-id="0c312-147">See also</span></span>

- [<span data-ttu-id="0c312-148">Создание и использование сборок со строгими именами</span><span class="sxs-lookup"><span data-stu-id="0c312-148">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
- [<span data-ttu-id="0c312-149">Практическое руководство. Создание пары открытого и закрытого ключей</span><span class="sxs-lookup"><span data-stu-id="0c312-149">How to: Create a public-private key pair</span></span>](create-public-private-key-pair.md)
- [<span data-ttu-id="0c312-150">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="0c312-150">Al.exe (Assembly Linker)</span></span>](../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="0c312-151">Отложенная подпись сборки</span><span class="sxs-lookup"><span data-stu-id="0c312-151">Delay-sign an assembly</span></span>](delay-sign.md)
- [<span data-ttu-id="0c312-152">Управление подписыванием сборок и манифестов</span><span class="sxs-lookup"><span data-stu-id="0c312-152">Manage assembly and manifest signing</span></span>](/visualstudio/ide/managing-assembly-and-manifest-signing)
- [<span data-ttu-id="0c312-153">Страница "Подписывание" в конструкторе проектов</span><span class="sxs-lookup"><span data-stu-id="0c312-153">Signing page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)
