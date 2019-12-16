---
title: "Практическое руководство. Подписание сборки строгим именем"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strong-named assemblies, signing with strong names
- signing assemblies
- assemblies [.NET Framework], signing
- assemblies [.NET Framework], strong-named
ms.assetid: 2c30799a-a826-46b4-a25d-c584027a6c67
caps.latest.revision: 23
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7758871a22b8b58d7df5cf2df481db185c07a987
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-sign-an-assembly-with-a-strong-name"></a><span data-ttu-id="170d1-102">Практическое руководство. Подписание сборки строгим именем</span><span class="sxs-lookup"><span data-stu-id="170d1-102">How to: Sign an Assembly with a Strong Name</span></span>
<span data-ttu-id="170d1-103">Существует несколько способов подписать сборку строгим именем:</span><span class="sxs-lookup"><span data-stu-id="170d1-103">There are a number of ways to sign an assembly with a strong name:</span></span>  
  
-   <span data-ttu-id="170d1-104">С использованием **Подписывание** в диалоговом окне **Свойства** проекта в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="170d1-104">By using the **Signing** tab in a project's **Properties** dialog box in Visual Studio.</span></span> <span data-ttu-id="170d1-105">Это самый простой и удобный способ подписать сборку строгим именем.</span><span class="sxs-lookup"><span data-stu-id="170d1-105">This is the easiest and most convenient way to sign an assembly with a strong name.</span></span>  
  
-   <span data-ttu-id="170d1-106">С использованием [компоновщика сборок (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) , который связывает модуль кода .NET Framework (NETMODULE-файл) с файлом ключа.</span><span class="sxs-lookup"><span data-stu-id="170d1-106">By using the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to link a .NET Framework code module (a .netmodule file) with a key file.</span></span>  
  
-   <span data-ttu-id="170d1-107">С использованием атрибутов сборки, позволяющих вставить в код данные строгого имени.</span><span class="sxs-lookup"><span data-stu-id="170d1-107">By using assembly attributes to insert the strong name information into your code.</span></span> <span data-ttu-id="170d1-108">Можно использовать либо <xref:System.Reflection.AssemblyKeyFileAttribute> , либо <xref:System.Reflection.AssemblyKeyNameAttribute> в зависимости от того, где находится используемый файл ключа.</span><span class="sxs-lookup"><span data-stu-id="170d1-108">You can use either the <xref:System.Reflection.AssemblyKeyFileAttribute> or the <xref:System.Reflection.AssemblyKeyNameAttribute> attribute, depending on where the key file to be used is located.</span></span>  
  
-   <span data-ttu-id="170d1-109">С использованием параметров компилятора.</span><span class="sxs-lookup"><span data-stu-id="170d1-109">By using compiler options.</span></span>  
  
 <span data-ttu-id="170d1-110">Для подписи сборки строгим именем необходимо иметь пару ключей шифрования.</span><span class="sxs-lookup"><span data-stu-id="170d1-110">You must have a cryptographic key pair to sign an assembly with a strong name.</span></span> <span data-ttu-id="170d1-111">Дополнительные сведения о создании пары ключей смотрите в разделе [Практическое руководство. Создание пары открытого и закрытого ключей](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md).</span><span class="sxs-lookup"><span data-stu-id="170d1-111">For more information about creating a key pair, see [How to: Create a Public-Private Key Pair](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md).</span></span>  
  
### <a name="to-create-and-sign-an-assembly-with-a-strong-name-by-using-visual-studio"></a><span data-ttu-id="170d1-112">Создание и подпись сборки строгим именем с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="170d1-112">To create and sign an assembly with a strong name by using Visual Studio</span></span>  
  
1.  <span data-ttu-id="170d1-113">В **обозревателе решений**откройте контекстное меню проекта и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="170d1-113">In **Solution Explorer**, open the shortcut menu for the project, and then choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="170d1-114">Перейдите на вкладку **Подписывание** .</span><span class="sxs-lookup"><span data-stu-id="170d1-114">Choose the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="170d1-115">Выберите поле **Подписать сборку**.</span><span class="sxs-lookup"><span data-stu-id="170d1-115">Select the **Sign the assembly** box.</span></span>  
  
4.  <span data-ttu-id="170d1-116">В поле **Выберите файл ключей строгого имени** нажмите **\<Обзор…>**, после чего выберите файл ключей.</span><span class="sxs-lookup"><span data-stu-id="170d1-116">In the **Choose a strong name key file** box, choose **\<Browse…>**, and then navigate to the key file.</span></span> <span data-ttu-id="170d1-117">Чтобы создать новый файл ключей, выберите **\<Создать…>** и введите его имя в диалоговом окне **Создание ключа строгого имени**.</span><span class="sxs-lookup"><span data-stu-id="170d1-117">To create a new key file, choose **\<New…>** and enter its name in the **Create Strong Name Key** dialog box.</span></span>  
  
### <a name="to-create-and-sign-an-assembly-with-a-strong-name-by-using-the-assembly-linker"></a><span data-ttu-id="170d1-118">Создание и подпись сборки строгим именем с помощью компоновщика сборок</span><span class="sxs-lookup"><span data-stu-id="170d1-118">To create and sign an assembly with a strong name by using the Assembly Linker</span></span>  
  
-   <span data-ttu-id="170d1-119">В [командной строке Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md) введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="170d1-119">At the [Visual Studio Command Prompt](../../../docs/framework/tools/developer-command-prompt-for-vs.md), type the following command:</span></span>  
  
     <span data-ttu-id="170d1-120">**al** **/out:**\<*assemblyName*> *\<moduleName>* **/keyfile:**\<*keyfileName*></span><span class="sxs-lookup"><span data-stu-id="170d1-120">**al** **/out:**\<*assemblyName*> *\<moduleName>* **/keyfile:**\<*keyfileName*></span></span>  
  
     <span data-ttu-id="170d1-121">где:</span><span class="sxs-lookup"><span data-stu-id="170d1-121">where:</span></span>  
  
     <span data-ttu-id="170d1-122">*имя_сборки*</span><span class="sxs-lookup"><span data-stu-id="170d1-122">*assemblyName*</span></span>  
     <span data-ttu-id="170d1-123">Имя строго подписанной сборки (файл DLL или EXE), которая будет создана компоновщиком сборок.</span><span class="sxs-lookup"><span data-stu-id="170d1-123">The name of the strongly signed assembly (a .dll or .exe file) that Assembly Linker will emit.</span></span>  
  
     <span data-ttu-id="170d1-124">*имя модуля*</span><span class="sxs-lookup"><span data-stu-id="170d1-124">*moduleName*</span></span>  
     <span data-ttu-id="170d1-125">Имя модуля кода .NET Framework (NETMODULE-файла), который содержит один тип или несколько.</span><span class="sxs-lookup"><span data-stu-id="170d1-125">The name of a .NET Framework code module (a .netmodule file) that includes one or more types.</span></span> <span data-ttu-id="170d1-126">NETMODULE-файл можно создать путем компиляции кода с параметром `/target:module` в C# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="170d1-126">You can create a .netmodule file by compiling your code with the `/target:module` switch in C# or Visual Basic.</span></span>  
  
     <span data-ttu-id="170d1-127">*имя_файла*</span><span class="sxs-lookup"><span data-stu-id="170d1-127">*keyfileName*</span></span>  
     <span data-ttu-id="170d1-128">Имя контейнера или файла, содержащего пару ключей.</span><span class="sxs-lookup"><span data-stu-id="170d1-128">The name of the container or file that contains the key pair.</span></span> <span data-ttu-id="170d1-129">Компоновщик сборок интерпретирует относительный путь с точки зрения текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="170d1-129">Assembly Linker interprets a relative path in relationship to the current directory.</span></span>  
  
 <span data-ttu-id="170d1-130">Следующий пример подписывает сборку `MyAssembly.dll` строгим именем с помощью файла ключей `sgKey.snk`.</span><span class="sxs-lookup"><span data-stu-id="170d1-130">The following example signs the assembly `MyAssembly.dll` with a strong name by using the key file `sgKey.snk`.</span></span>  
  
```  
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  
```  
  
 <span data-ttu-id="170d1-131">Дополнительные сведения об использовании этого инструмента см. в разделе [Компоновщик сборок](../../../docs/framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="170d1-131">For more information about this tool, see [Assembly Linker](../../../docs/framework/tools/al-exe-assembly-linker.md).</span></span>  
  
#### <a name="to-sign-an-assembly-with-a-strong-name-by-using-attributes"></a><span data-ttu-id="170d1-132">Подпись сборки строгим именем с помощью атрибутов</span><span class="sxs-lookup"><span data-stu-id="170d1-132">To sign an assembly with a strong name by using attributes</span></span>  
  
1.  <span data-ttu-id="170d1-133">Добавьте <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=fullName> или <xref:System.Reflection.AssemblyKeyNameAttribute> в файл исходного кода и укажите имя файла или контейнера, содержащего пару ключей, которая используется при подписи сборки строгим именем.</span><span class="sxs-lookup"><span data-stu-id="170d1-133">Add the <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=fullName> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute to your source code file, and specify the name of the file or container that contains the key pair to use when signing the assembly with a strong name.</span></span>  
  
2.  <span data-ttu-id="170d1-134">Компилируйте файл исходного кода в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="170d1-134">Compile the source code file normally.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="170d1-135">Компиляторы C# и Visual Basic выдают предупреждения (CS1699 и BC41008, соответственно), если в исходном коде встречается <xref:System.Reflection.AssemblyKeyFileAttribute> или <xref:System.Reflection.AssemblyKeyNameAttribute> .</span><span class="sxs-lookup"><span data-stu-id="170d1-135">The C# and Visual Basic compilers issue compiler warnings (CS1699 and BC41008, respectively) when they encounter the <xref:System.Reflection.AssemblyKeyFileAttribute> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute in source code.</span></span> <span data-ttu-id="170d1-136">Эти предупреждения можно игнорировать.</span><span class="sxs-lookup"><span data-stu-id="170d1-136">You can ignore the warnings.</span></span>  
  
 <span data-ttu-id="170d1-137">В следующем примере кода используется атрибут <xref:System.Reflection.AssemblyKeyFileAttribute> с файлом ключей под названием `keyfile.snk`, который находится в том же каталоге, где компилируется сборка.</span><span class="sxs-lookup"><span data-stu-id="170d1-137">The following example uses the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute with a key file called `keyfile.snk`, which is located in the directory where the assembly is compiled.</span></span>  
  
 <span data-ttu-id="170d1-138">[!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)] [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)] [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]</span><span class="sxs-lookup"><span data-stu-id="170d1-138">[!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)] [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)] [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]</span></span>  
  
 <span data-ttu-id="170d1-139">Кроме того, при компиляции исходного файла можно использовать отложенную подпись.</span><span class="sxs-lookup"><span data-stu-id="170d1-139">You can also delay sign an assembly when compiling your source file.</span></span> <span data-ttu-id="170d1-140">Дополнительные сведения см. в разделе [Отложенная подпись сборки](../../../docs/framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="170d1-140">For more information, see [Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-sign-an-assembly-with-a-strong-name-by-using-the-compiler"></a><span data-ttu-id="170d1-141">Подпись сборки строгим именем с использованием компилятора</span><span class="sxs-lookup"><span data-stu-id="170d1-141">To sign an assembly with a strong name by using the compiler</span></span>  
  
-   <span data-ttu-id="170d1-142">Компилируйте файлы исходного кода с помощью параметра компилятора `/keyfile` или `/delaysign` в C# и Visual Basic либо параметра компоновщика `/KEYFILE` или `/DELAYSIGN` в C++.</span><span class="sxs-lookup"><span data-stu-id="170d1-142">Compile your source code file or files with the `/keyfile` or `/delaysign` compiler option in C# and Visual Basic, or the `/KEYFILE` or `/DELAYSIGN` linker option in C++.</span></span> <span data-ttu-id="170d1-143">После имени параметра добавьте двоеточие и имя файла ключей.</span><span class="sxs-lookup"><span data-stu-id="170d1-143">After the option name, add a colon and the name of the key file.</span></span> <span data-ttu-id="170d1-144">При использовании компиляторов, работающих в режиме командной строки, можно скопировать файл ключей в каталог, содержащий файлы исходного кода.</span><span class="sxs-lookup"><span data-stu-id="170d1-144">When using command-line compilers, you can copy the key file to the directory that contains your source code files.</span></span>  
  
     <span data-ttu-id="170d1-145">Подробные сведения об отложенной подписи см. в разделе [Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="170d1-145">For information on delay signing, see [Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).</span></span>  
  
     <span data-ttu-id="170d1-146">В следующем примере используется компилятор C# и сборка `UtilityLibrary.dll` подписывается строгим именем с помощью файла ключей `sgKey.snk`.</span><span class="sxs-lookup"><span data-stu-id="170d1-146">The following example uses the C# compiler and signs the assembly `UtilityLibrary.dll` with a strong name by using the key file `sgKey.snk`.</span></span>  
  
    ```  
    csc /t:library UtilityLibrary.cs /keyfile:sgKey.snk  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="170d1-147">См. также</span><span class="sxs-lookup"><span data-stu-id="170d1-147">See Also</span></span>  
 <span data-ttu-id="170d1-148">[Создание и использование сборок со строгими именами](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="170d1-148">[Creating and Using Strong-Named Assemblies](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md) </span></span>  
 <span data-ttu-id="170d1-149">[Практическое руководство. Создание пары открытого и закрытого ключей](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md) </span><span class="sxs-lookup"><span data-stu-id="170d1-149">[How to: Create a Public-Private Key Pair](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md) </span></span>  
 <span data-ttu-id="170d1-150">[Al.exe (компоновщик сборок)](../../../docs/framework/tools/al-exe-assembly-linker.md) </span><span class="sxs-lookup"><span data-stu-id="170d1-150">[Al.exe (Assembly Linker)](../../../docs/framework/tools/al-exe-assembly-linker.md) </span></span>  
 <span data-ttu-id="170d1-151">[Отложенная подпись сборки](../../../docs/framework/app-domains/delay-sign-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="170d1-151">[Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md) </span></span>  
 <span data-ttu-id="170d1-152">[Управление сборками и подписывание манифестов](/visualstudio/ide/managing-assembly-and-manifest-signing) </span><span class="sxs-lookup"><span data-stu-id="170d1-152">[Managing Assembly and Manifest Signing](/visualstudio/ide/managing-assembly-and-manifest-signing) </span></span>  
 [<span data-ttu-id="170d1-153">Страница "Подписывание" в конструкторе проектов</span><span class="sxs-lookup"><span data-stu-id="170d1-153">Signing Page, Project Designer</span></span>](https://msdn.microsoft.com/library/0k50fs3b)
