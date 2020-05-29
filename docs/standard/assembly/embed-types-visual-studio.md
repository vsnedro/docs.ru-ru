---
title: Пошаговое руководство. Внедрение типов из управляемых сборок в Visual Studio
description: В этом пошаговом руководстве показано, как внедрять типы из управляемых сборок в .NET с помощью Visual Studio. Внедренные типы могут поддерживать независимость от версии.
ms.date: 08/19/2019
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
dev_langs:
- csharp
- vb
ms.openlocfilehash: 636e5f8095b64cd0f445555c96d00945ccf7eaf8
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378984"
---
# <a name="walkthrough-embed-types-from-managed-assemblies-in-visual-studio"></a><span data-ttu-id="dcff9-104">Пошаговое руководство. Внедрение типов из управляемых сборок в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dcff9-104">Walkthrough: Embed types from managed assemblies in Visual Studio</span></span>

<span data-ttu-id="dcff9-105">Внедряя сведения о типе из управляемой сборки со строгим именем, можно свободно объединять типы в приложении, делая версию независимой.</span><span class="sxs-lookup"><span data-stu-id="dcff9-105">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="dcff9-106">Это означает, что в программе можно использовать типы из любой версии управляемой библиотеки, т. е. необходимость компиляции для каждой новой версии отпадает.</span><span class="sxs-lookup"><span data-stu-id="dcff9-106">That is, your program can be written to use types from any version of a managed library without having to be recompiled for each new version.</span></span>

<span data-ttu-id="dcff9-107">Внедрение типов часто используется с COM-взаимодействием, например в приложениях, использующих объекты автоматизации из Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="dcff9-107">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="dcff9-108">Сведения о типе внедрения позволяют одной и той же сборке программы работать с различными версиями Microsoft Office на разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="dcff9-108">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="dcff9-109">Тем не менее внедрение типа можно также использовать с полностью управляемыми решениями.</span><span class="sxs-lookup"><span data-stu-id="dcff9-109">However, you can also use type embedding with fully managed solutions.</span></span>

<span data-ttu-id="dcff9-110">После указания открытых интерфейсов, доступных для внедрения, создайте реализующие их классы среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="dcff9-110">After you specify the public interfaces that can be embedded, you create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="dcff9-111">Во время разработки клиентская программа встраивает сведения о типе для интерфейсов, ссылаясь на сборку, содержащую открытые интерфейсы, и присваивая свойству `Embed Interop Types` ссылки значение `True`.</span><span class="sxs-lookup"><span data-stu-id="dcff9-111">A client program can embed the type information for the interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="dcff9-112">После этого клиентская программа может загружать экземпляры объектов среды выполнения, типизированные как указанные интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="dcff9-112">The client program can then load instances of the runtime objects typed as those interfaces.</span></span> <span data-ttu-id="dcff9-113">Это эквивалентно использованию компилятора командной строки и ссылки на сборку с помощью [параметра компилятора -link](../../csharp/language-reference/compiler-options/link-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="dcff9-113">This is equivalent to using the command line compiler and referencing the assembly by using the [-link compiler option](../../csharp/language-reference/compiler-options/link-compiler-option.md).</span></span>

<span data-ttu-id="dcff9-114">При создании новой версии сборки среды выполнения со строгим именем повторная компиляция клиентской программы не требуется.</span><span class="sxs-lookup"><span data-stu-id="dcff9-114">If you create a new version of your strong-named runtime assembly, the client program doesn't have to be recompiled.</span></span> <span data-ttu-id="dcff9-115">Клиентская программа продолжает работать с той версией сборки среды выполнения, которая ей доступна, используя сведения о внедренном типе для открытых интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="dcff9-115">The client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>

<span data-ttu-id="dcff9-116">С помощью этого пошагового руководства:</span><span class="sxs-lookup"><span data-stu-id="dcff9-116">In this walkthrough, you:</span></span>

1. <span data-ttu-id="dcff9-117">Создайте сборку со строгим именем и открытым интерфейсом, содержащим сведения о типе, который может быть внедрен.</span><span class="sxs-lookup"><span data-stu-id="dcff9-117">Create a strong-named assembly with a public interface containing type information that can be embedded.</span></span>
1. <span data-ttu-id="dcff9-118">Создайте сборку среды выполнения со строгим именем, реализующую открытый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="dcff9-118">Create a strong-named runtime assembly that implements the public interface.</span></span>
1. <span data-ttu-id="dcff9-119">Создайте клиентскую программу, внедряющую сведения о типе из открытого интерфейса и создающую экземпляр класса из сборки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="dcff9-119">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>
1. <span data-ttu-id="dcff9-120">Внесите изменения и создайте сборку среды выполнения заново.</span><span class="sxs-lookup"><span data-stu-id="dcff9-120">Modify and rebuild the runtime assembly.</span></span>
1. <span data-ttu-id="dcff9-121">Запустите клиентскую программу, чтобы увидеть, что новая версия сборки среды выполнения используется без повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="dcff9-121">Run the client program to see that it uses the new version of the runtime assembly without having to be recompiled.</span></span>

[!INCLUDE[note_settings_general](../../../includes/note-settings-general-md.md)]

## <a name="conditions-and-limitations"></a><span data-ttu-id="dcff9-122">Условия и ограничения</span><span class="sxs-lookup"><span data-stu-id="dcff9-122">Conditions and limitations</span></span>

<span data-ttu-id="dcff9-123">Вы можете внедрить информацию о типах из сборки при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="dcff9-123">You can embed type information from an assembly under the following conditions:</span></span>

- <span data-ttu-id="dcff9-124">Сборка предоставляет по крайней мере один открытый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="dcff9-124">The assembly exposes at least one public interface.</span></span>
- <span data-ttu-id="dcff9-125">Внедренные интерфейсы снабжаются аннотацией с указанием атрибутов `ComImport` и `Guid` с уникальными GUID.</span><span class="sxs-lookup"><span data-stu-id="dcff9-125">The embedded interfaces are annotated with `ComImport` attributes and `Guid` attributes with unique GUIDs.</span></span>
- <span data-ttu-id="dcff9-126">Сборка снабжается аннотацией с указанием атрибута `ImportedFromTypeLib` или атрибута `PrimaryInteropAssembly`, а также атрибута сборки `Guid`.</span><span class="sxs-lookup"><span data-stu-id="dcff9-126">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="dcff9-127">По умолчанию шаблоны проектов Visual C# и Visual Basic включают атрибут сборки `Guid`.</span><span class="sxs-lookup"><span data-stu-id="dcff9-127">The Visual C# and Visual Basic project templates include an assembly-level `Guid` attribute by default.</span></span>

<span data-ttu-id="dcff9-128">Так как основной функцией внедрения типа является поддержка внедрения сборок COM-взаимодействия, при внедрении сведений о типе в полностью управляемое решение применяются следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="dcff9-128">Because the primary function of type embedding is to support COM interop assemblies, the following limitations apply when you embed type information in a fully-managed solution:</span></span>

- <span data-ttu-id="dcff9-129">Внедряются только атрибуты, характерные для COM-взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="dcff9-129">Only attributes specific to COM interop are embedded.</span></span> <span data-ttu-id="dcff9-130">Другие атрибуты игнорируются.</span><span class="sxs-lookup"><span data-stu-id="dcff9-130">Other attributes are ignored.</span></span>
- <span data-ttu-id="dcff9-131">Если тип включает универсальные параметры внедренного типа, использовать этот тип за границей сборки невозможно.</span><span class="sxs-lookup"><span data-stu-id="dcff9-131">If a type uses generic parameters, and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="dcff9-132">Граница сборки пересекается, например, при вызове метода из другой сборки или выведении типа из типа, определенного в другой сборке.</span><span class="sxs-lookup"><span data-stu-id="dcff9-132">Examples of crossing an assembly boundary include calling a method from another assembly or deriving a type from a type defined in another assembly.</span></span>
- <span data-ttu-id="dcff9-133">Константы не внедряются.</span><span class="sxs-lookup"><span data-stu-id="dcff9-133">Constants are not embedded.</span></span>
- <span data-ttu-id="dcff9-134">Класс <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> не поддерживает использование внедренного типа в качестве ключа.</span><span class="sxs-lookup"><span data-stu-id="dcff9-134">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> class does not support an embedded type as a key.</span></span> <span data-ttu-id="dcff9-135">Для поддержки внедренного типа в качестве ключа можно реализовать свой собственный тип словаря.</span><span class="sxs-lookup"><span data-stu-id="dcff9-135">You can implement your own dictionary type to support an embedded type as a key.</span></span>

## <a name="create-an-interface"></a><span data-ttu-id="dcff9-136">Создание интерфейса</span><span class="sxs-lookup"><span data-stu-id="dcff9-136">Create an interface</span></span>

<span data-ttu-id="dcff9-137">Первый шаг заключается в создании сборки интерфейса для эквивалентности типов.</span><span class="sxs-lookup"><span data-stu-id="dcff9-137">The first step is to create the type equivalence interface assembly.</span></span>

1. <span data-ttu-id="dcff9-138">В Visual Studio последовательно выберите **Файл** > **Создать** > **Проект**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-138">In Visual Studio, select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="dcff9-139">В диалоговом окне **Создание проекта** введите *библиотека классов* в поле **Поиск шаблонов**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-139">In the **Create a new project** dialog box, type *class library* in the **Search for templates** box.</span></span> <span data-ttu-id="dcff9-140">Выберите шаблон **Библиотека классов (.NET Framework)** для C# или Visual Basic в списке и щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-140">Select either the C# or Visual Basic **Class Library (.NET Framework)** template from the list, and then select **Next**.</span></span>

1. <span data-ttu-id="dcff9-141">В диалоговом окне **Настроить новый проект** в поле **Имя проекта** введите *TypeEquivalenceInterface* и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-141">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceInterface*, and then select **Create**.</span></span> <span data-ttu-id="dcff9-142">Проект создан.</span><span class="sxs-lookup"><span data-stu-id="dcff9-142">The new project is created.</span></span>

1. <span data-ttu-id="dcff9-143">В **обозревателе решений** щелкните правой кнопкой мыши файл *Class1.cs* или *Class1.vb*, выберите пункт **Переименовать** и переименуйте файл с *Class1* на *ISampleInterface*.</span><span class="sxs-lookup"><span data-stu-id="dcff9-143">In **Solution Explorer**, right-click the *Class1.cs* or *Class1.vb* file, select **Rename**, and rename the file from *Class1* to *ISampleInterface*.</span></span> <span data-ttu-id="dcff9-144">Ответьте **Да** на запрос, чтобы также переименовать класс на `ISampleInterface`.</span><span class="sxs-lookup"><span data-stu-id="dcff9-144">Respond **Yes** to the prompt to also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="dcff9-145">Этот класс представляет открытый интерфейс для класса.</span><span class="sxs-lookup"><span data-stu-id="dcff9-145">This class represents the public interface for the class.</span></span>

1. <span data-ttu-id="dcff9-146">В **обозревателе решений** щелкните правой кнопкой мыши проект **TypeEquivalenceInterface** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-146">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project, and then select **Properties**.</span></span>

1. <span data-ttu-id="dcff9-147">Выберите элемент **Сборка** в левой области экрана **Свойства** и задайте в поле **Путь вывода** расположение на компьютере, например *C:\TypeEquivalenceSample*.</span><span class="sxs-lookup"><span data-stu-id="dcff9-147">Select **Build** on the left pane of the **Properties** screen, and set the **Output path** to a location on your computer, such as *C:\TypeEquivalenceSample*.</span></span> <span data-ttu-id="dcff9-148">Данное расположение используется в рамках всего этого пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="dcff9-148">You use the same location throughout this walkthrough.</span></span>

1. <span data-ttu-id="dcff9-149">Выберите **Подписывание** в левой области экрана **Свойства** и установите флажок **Подписать сборку**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-149">Select **Signing** on the left pane of the **Properties** screen, and then select the **Sign the assembly** check box.</span></span> <span data-ttu-id="dcff9-150">В раскрывающемся списке **Выберите файл ключа строгого имени** выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-150">In the dropdown for **Choose a strong name key file**, select **New**.</span></span>

1. <span data-ttu-id="dcff9-151">В диалоговом окне **Создание ключа строгого имени** в разделе **Имя файла ключа** введите *key.snk*.</span><span class="sxs-lookup"><span data-stu-id="dcff9-151">In the **Create Strong Name Key** dialog, under **Key file name**, type *key.snk*.</span></span> <span data-ttu-id="dcff9-152">Снимите флажок **Защитить мой файл ключей паролем** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-152">Deselect the **Protect my key file with a password** check box, and then select **OK**.</span></span>

1. <span data-ttu-id="dcff9-153">Откройте файл класса *ISampleInterface* в редакторе кода и замените его содержимое следующим кодом, чтобы создать интерфейс `ISampleInterface`:</span><span class="sxs-lookup"><span data-stu-id="dcff9-153">Open the *ISampleInterface* class file in the code editor, and replace its contents with the following code to create the `ISampleInterface` interface:</span></span>

   ```csharp
   using System;
   using System.Runtime.InteropServices;

   namespace TypeEquivalenceInterface
   {
       [ComImport]
       [Guid("8DA56996-A151-4136-B474-32784559F6DF")]
       public interface ISampleInterface
       {
           void GetUserInput();
           string UserInput { get; }
       }
   }
   ```

   ```vb
   Imports System.Runtime.InteropServices

   <ComImport()>
   <Guid("8DA56996-A151-4136-B474-32784559F6DF")>
   Public Interface ISampleInterface
       Sub GetUserInput()
       ReadOnly Property UserInput As String
   End Interface
   ```

1. <span data-ttu-id="dcff9-154">В меню **Сервис** выберите пункт **Создать GUID** и в диалоговом окне **Создание GUID** выберите **Формат реестра**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-154">On the **Tools** menu, select **Create Guid**, and in the **Create GUID** dialog box, select **Registry Format**.</span></span> <span data-ttu-id="dcff9-155">Выберите **Копировать**, а затем **Выход**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-155">Select **Copy**, and then select **Exit**.</span></span>

1. <span data-ttu-id="dcff9-156">В атрибуте `Guid` кода замените пример GUID на скопированный GUID и удалите фигурные скобки ( **{ }** ).</span><span class="sxs-lookup"><span data-stu-id="dcff9-156">In the `Guid` attribute of your code, replace the sample GUID with the GUID you copied, and remove the braces (**{ }**).</span></span>

1. <span data-ttu-id="dcff9-157">В **обозревателе решений** разверните папку **Свойства** и выберите файл *AssemblyInfo.cs* или *AssemblyInfo.vb* file.</span><span class="sxs-lookup"><span data-stu-id="dcff9-157">In **Solution Explorer**, expand the **Properties** folder and select the *AssemblyInfo.cs* or *AssemblyInfo.vb* file.</span></span> <span data-ttu-id="dcff9-158">В редакторе кода добавьте в файл следующий атрибут:</span><span class="sxs-lookup"><span data-stu-id="dcff9-158">In the code editor, add the following attribute to the file:</span></span>

   ```csharp
   [assembly: ImportedFromTypeLib("")]
   ```

   ```vb
   <Assembly: ImportedFromTypeLib("")>
   ```

1. <span data-ttu-id="dcff9-159">Выберите **Файл** > **Сохранить все** или нажмите клавиши **CTRL**+**SHIFT**+**S** для сохранения файлов и проекта.</span><span class="sxs-lookup"><span data-stu-id="dcff9-159">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="dcff9-160">В **обозревателе решений** щелкните правой кнопкой мыши проект **TypeEquivalenceInterface** и выберите пункт **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-160">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Build**.</span></span> <span data-ttu-id="dcff9-161">DLL-файл библиотеки классов компилируется и сохраняется по указанному пути вывода сборки, например *C:\TypeEquivalenceSample*.</span><span class="sxs-lookup"><span data-stu-id="dcff9-161">The class library DLL file is compiled and saved to the specified build output path, for example *C:\TypeEquivalenceSample*.</span></span>

## <a name="create-a-runtime-class"></a><span data-ttu-id="dcff9-162">Создание класса среды выполнения</span><span class="sxs-lookup"><span data-stu-id="dcff9-162">Create a runtime class</span></span>

<span data-ttu-id="dcff9-163">Далее создайте класс среды выполнения для эквивалентности типов.</span><span class="sxs-lookup"><span data-stu-id="dcff9-163">Next, create the type equivalence runtime class.</span></span>

1. <span data-ttu-id="dcff9-164">В Visual Studio последовательно выберите **Файл** > **Создать** > **Проект**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-164">In Visual Studio, select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="dcff9-165">В диалоговом окне **Создание проекта** введите *библиотека классов* в поле **Поиск шаблонов**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-165">In the **Create a new project** dialog box, type *class library* in the **Search for templates** box.</span></span> <span data-ttu-id="dcff9-166">Выберите шаблон **Библиотека классов (.NET Framework)** для C# или Visual Basic в списке и щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-166">Select either the C# or Visual Basic **Class Library (.NET Framework)** template from the list, and then select **Next**.</span></span>

1. <span data-ttu-id="dcff9-167">В диалоговом окне **Настроить новый проект** в поле **Имя проекта** введите *TypeEquivalenceRuntime* и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-167">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceRuntime*, and then select **Create**.</span></span> <span data-ttu-id="dcff9-168">Проект создан.</span><span class="sxs-lookup"><span data-stu-id="dcff9-168">The new project is created.</span></span>

1. <span data-ttu-id="dcff9-169">В **обозревателе решений** щелкните правой кнопкой мыши файл *Class1.cs* или *Class1.vb*, выберите пункт **Переименовать** и переименуйте файл с *Class1* на *SampleClass*.</span><span class="sxs-lookup"><span data-stu-id="dcff9-169">In **Solution Explorer**, right-click the *Class1.cs* or *Class1.vb* file, select **Rename**, and rename the file from *Class1* to *SampleClass*.</span></span> <span data-ttu-id="dcff9-170">Ответьте **Да** на запрос, чтобы также переименовать класс на `SampleClass`.</span><span class="sxs-lookup"><span data-stu-id="dcff9-170">Respond **Yes** to the prompt to also rename the class to `SampleClass`.</span></span> <span data-ttu-id="dcff9-171">Этот класс реализует интерфейс `ISampleInterface` .</span><span class="sxs-lookup"><span data-stu-id="dcff9-171">This class implements the `ISampleInterface` interface.</span></span>

1. <span data-ttu-id="dcff9-172">В **обозревателе решений** щелкните правой кнопкой мыши проект **TypeEquivalenceInterface** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-172">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Properties**.</span></span>

1. <span data-ttu-id="dcff9-173">Выберите элемент **Сборка** в левой области экрана **Свойства** и задайте в поле **Путь вывода** то же расположение, которое использовали для проекта TypeEquivalenceInterface, например, *C:\TypeEquivalenceSample*.</span><span class="sxs-lookup"><span data-stu-id="dcff9-173">Select **Build** on the left pane of the **Properties** screen, and then set the **Output path** to the same location you used for the TypeEquivalenceInterface project, for example, *C:\TypeEquivalenceSample*.</span></span>

1. <span data-ttu-id="dcff9-174">Выберите **Подписывание** в левой области экрана **Свойства** и установите флажок **Подписать сборку**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-174">Select **Signing** on the left pane of the **Properties** screen, and then select the **Sign the assembly** check box.</span></span> <span data-ttu-id="dcff9-175">В раскрывающемся списке **Выберите файл ключа строгого имени** выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-175">In the dropdown for **Choose a strong name key file**, select **New**.</span></span>

1. <span data-ttu-id="dcff9-176">В диалоговом окне **Создание ключа строгого имени** в разделе **Имя файла ключа** введите *key.snk*.</span><span class="sxs-lookup"><span data-stu-id="dcff9-176">In the **Create Strong Name Key** dialog, under **Key file name**, type *key.snk*.</span></span> <span data-ttu-id="dcff9-177">Снимите флажок **Защитить мой файл ключей паролем** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-177">Deselect the **Protect my key file with a password** check box, and then select **OK**.</span></span>

1. <span data-ttu-id="dcff9-178">В **обозревателе решений** щелкните проект **TypeEquivalenceRuntime** правой кнопкой мыши и выберите **Добавить** > **Ссылка**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-178">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Add** > **Reference**.</span></span>

1. <span data-ttu-id="dcff9-179">В диалоговом окне **Диспетчер ссылок** выберите **Обзор** и перейдите к папке пути вывода.</span><span class="sxs-lookup"><span data-stu-id="dcff9-179">In the **Reference Manager** dialog, select **Browse** and browse to the output path folder.</span></span> <span data-ttu-id="dcff9-180">Выберите файл *TypeEquivalenceInterface.dll*, нажмите кнопку **Добавить** и затем кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-180">Select the *TypeEquivalenceInterface.dll* file, select **Add**, and then select **OK**.</span></span>

1. <span data-ttu-id="dcff9-181">В **обозревателе решений** разверните папку **Ссылки** и выберите ссылку **TypeEquivalenceInterface**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-181">In **Solution Explorer**, expand the **References** folder and select the **TypeEquivalenceInterface** reference.</span></span> <span data-ttu-id="dcff9-182">В области **Свойства** задайте для параметра **Определенная версия** значение **False**, если оно еще не установлено.</span><span class="sxs-lookup"><span data-stu-id="dcff9-182">In the **Properties** pane, set **Specific Version** to **False** if it is not already.</span></span>

1. <span data-ttu-id="dcff9-183">Откройте файл класса *SampleClass* в редакторе кода и замените его содержимое следующим кодом, чтобы создать класс `SampleClass`:</span><span class="sxs-lookup"><span data-stu-id="dcff9-183">Open the *SampleClass* class file in the code editor, and replace its contents with the following code to create the `SampleClass` class:</span></span>

   ```csharp
   using System;
   using TypeEquivalenceInterface;

   namespace TypeEquivalenceRuntime
   {
       public class SampleClass : ISampleInterface
       {
           private string p_UserInput;
           public string UserInput { get { return p_UserInput; } }

           public void GetUserInput()
           {
               Console.WriteLine("Please enter a value:");
               p_UserInput = Console.ReadLine();
           }
       }
   }
   ```

   ```vb
   Imports TypeEquivalenceInterface

   Public Class SampleClass
       Implements ISampleInterface

       Private p_UserInput As String
       Public ReadOnly Property UserInput() As String Implements ISampleInterface.UserInput
           Get
               Return p_UserInput
           End Get
       End Property

       Public Sub GetUserInput() Implements ISampleInterface.GetUserInput
           Console.WriteLine("Please enter a value:")
           p_UserInput = Console.ReadLine()
       End Sub
   End Class
   ```

1. <span data-ttu-id="dcff9-184">Выберите **Файл** > **Сохранить все** или нажмите клавиши **CTRL**+**SHIFT**+**S** для сохранения файлов и проекта.</span><span class="sxs-lookup"><span data-stu-id="dcff9-184">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="dcff9-185">В **обозревателе решений** щелкните проект **TypeEquivalenceRuntime** правой кнопкой мыши и выберите **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-185">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Build**.</span></span> <span data-ttu-id="dcff9-186">DLL-файл библиотеки классов компилируется и сохраняется по указанному пути вывода сборки.</span><span class="sxs-lookup"><span data-stu-id="dcff9-186">The class library DLL file is compiled and saved to the specified build output path.</span></span>

## <a name="create-a-client-project"></a><span data-ttu-id="dcff9-187">Создание клиентского проекта</span><span class="sxs-lookup"><span data-stu-id="dcff9-187">Create a client project</span></span>

<span data-ttu-id="dcff9-188">Наконец, создайте клиентскую программу эквивалентности типов, которая ссылается на сборку интерфейса.</span><span class="sxs-lookup"><span data-stu-id="dcff9-188">Finally, create a type equivalence client program that references the interface assembly.</span></span>

1. <span data-ttu-id="dcff9-189">В Visual Studio последовательно выберите **Файл** > **Создать** > **Проект**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-189">In Visual Studio, select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="dcff9-190">В диалоговом окне **Создание проекта** введите *консоль* в поле **Поиск шаблонов**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-190">In the **Create a new project** dialog box, type *console* in the **Search for templates** box.</span></span> <span data-ttu-id="dcff9-191">Выберите шаблон **Консольное приложение (.NET Framework)** для C# или Visual Basic в списке и щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-191">Select either the C# or Visual Basic **Console App (.NET Framework)** template from the list, and then select **Next**.</span></span>

1. <span data-ttu-id="dcff9-192">В диалоговом окне **Настроить новый проект** в поле **Имя проекта** введите *TypeEquivalenceClient* и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-192">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceClient*, and then select **Create**.</span></span> <span data-ttu-id="dcff9-193">Проект создан.</span><span class="sxs-lookup"><span data-stu-id="dcff9-193">The new project is created.</span></span>

1. <span data-ttu-id="dcff9-194">В **обозревателе решений** щелкните правой кнопкой мыши проект **TypeEquivalenceClient** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-194">In **Solution Explorer**, right-click the **TypeEquivalenceClient** project and select **Properties**.</span></span>

1. <span data-ttu-id="dcff9-195">Выберите элемент **Сборка** в левой области экрана **Свойства** и задайте в поле **Путь вывода** то же расположение, которое использовали для проекта TypeEquivalenceInterface, например, *C:\TypeEquivalenceSample*.</span><span class="sxs-lookup"><span data-stu-id="dcff9-195">Select **Build** on the left pane of the **Properties** screen, and then set the **Output path** to the same location you used for the TypeEquivalenceInterface project, for example, *C:\TypeEquivalenceSample*.</span></span>

1. <span data-ttu-id="dcff9-196">В **обозревателе решений** щелкните правой кнопкой мыши проект **TypeEquivalenceClient** и выберите **Добавить** > **Ссылка**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-196">In **Solution Explorer**, right-click the **TypeEquivalenceClient** project and select **Add** > **Reference**.</span></span>

1. <span data-ttu-id="dcff9-197">В диалоговом окне **Диспетчер ссылок** выберите файл **TypeEquivalenceInterface.dll**, если он уже присутствует в списке.</span><span class="sxs-lookup"><span data-stu-id="dcff9-197">In the **Reference Manager** dialog, if the **TypeEquivalenceInterface.dll** file is already listed, select it.</span></span> <span data-ttu-id="dcff9-198">В противном случае выберите **Обзор**, перейдите к папке пути вывода, выберите файл *TypeEquivalenceInterface.dll* (а не *TypeEquivalenceRuntime.dll*) и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-198">If not, select **Browse**, browse to the output path folder, select the *TypeEquivalenceInterface.dll* file (not the *TypeEquivalenceRuntime.dll*), and select **Add**.</span></span> <span data-ttu-id="dcff9-199">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-199">Select **OK**.</span></span>

1. <span data-ttu-id="dcff9-200">В **обозревателе решений** разверните папку **Ссылки** и выберите ссылку **TypeEquivalenceInterface**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-200">In **Solution Explorer**, expand the **References** folder and select the **TypeEquivalenceInterface** reference.</span></span> <span data-ttu-id="dcff9-201">В области **Свойства** установите для параметра **Внедрить типы взаимодействия** значение **True**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-201">In the **Properties** pane, set **Embed Interop Types** to **True**.</span></span>

1. <span data-ttu-id="dcff9-202">Откройте файл *Program.cs* или *Module1.vb* в редакторе кода и замените его содержимое следующим кодом, чтобы создать клиентскую программу:</span><span class="sxs-lookup"><span data-stu-id="dcff9-202">Open the *Program.cs* or *Module1.vb* file in the code editor, and replace its contents with the following code to create the client program:</span></span>

   ```csharp
   using System;
   using System.Reflection;
   using TypeEquivalenceInterface;

   namespace TypeEquivalenceClient
   {
       class Program
       {
           static void Main(string[] args)
           {
               Assembly sampleAssembly = Assembly.Load("TypeEquivalenceRuntime");
               ISampleInterface sampleClass =
                   (ISampleInterface)sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass");
               sampleClass.GetUserInput();
               Console.WriteLine(sampleClass.UserInput);
               Console.WriteLine(sampleAssembly.GetName().Version.ToString());
               Console.ReadLine();
           }
       }
   }
   ```

   ```vb
   Imports System.Reflection
   Imports TypeEquivalenceInterface

   Module Module1

       Sub Main()
           Dim sampleAssembly = Assembly.Load("TypeEquivalenceRuntime")
           Dim sampleClass As ISampleInterface = CType( _
               sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass"), ISampleInterface)
           sampleClass.GetUserInput()
           Console.WriteLine(sampleClass.UserInput)
           Console.WriteLine(sampleAssembly.GetName().Version)
           Console.ReadLine()
       End Sub

   End Module
   ```

1. <span data-ttu-id="dcff9-203">Выберите **Файл** > **Сохранить все** или нажмите клавиши **CTRL**+**SHIFT**+**S** для сохранения файлов и проекта.</span><span class="sxs-lookup"><span data-stu-id="dcff9-203">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="dcff9-204">Нажмите клавиши **CTRL**+**F5**, чтобы собрать и запустить программу.</span><span class="sxs-lookup"><span data-stu-id="dcff9-204">Press **Ctrl**+**F5** to build and run the program.</span></span> <span data-ttu-id="dcff9-205">Обратите внимание, что выходные данные консоли возвращают версию сборки **1.0.0.0**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-205">Note that the console output returns the assembly version **1.0.0.0**.</span></span>

## <a name="modify-the-interface"></a><span data-ttu-id="dcff9-206">Изменение интерфейса</span><span class="sxs-lookup"><span data-stu-id="dcff9-206">Modify the interface</span></span>

<span data-ttu-id="dcff9-207">Теперь измените сборку интерфейса и смените ее версию.</span><span class="sxs-lookup"><span data-stu-id="dcff9-207">Now, modify the interface assembly, and change its version.</span></span>

1. <span data-ttu-id="dcff9-208">В Visual Studio выберите **Файл** > **Открыть** > **Проект/решение** и откройте проект **TypeEquivalenceInterface**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-208">In Visual Studio, select **File** > **Open** > **Project/Solution**, and open the **TypeEquivalenceInterface** project.</span></span>

1. <span data-ttu-id="dcff9-209">В **обозревателе решений** щелкните правой кнопкой мыши проект **TypeEquivalenceInterface** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-209">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Properties**.</span></span>

1. <span data-ttu-id="dcff9-210">Выберите **Приложение** в левой области экрана **Свойства** и элемент **Сведения о сборке**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-210">Select **Application** on the left pane of the **Properties** screen, and then select **Assembly Information**.</span></span>

1. <span data-ttu-id="dcff9-211">В диалоговом окне **Сведения о сборке** измените значения **Версия сборки** и **Версия файла** на *2.0.0.0* и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-211">In the **Assembly Information** dialog box, change the **Assembly version** and **File version** values to *2.0.0.0*, and then select **OK**.</span></span>

1. <span data-ttu-id="dcff9-212">Откройте файл *SampleInterface.cs* или *SampleInterface.vb* и добавьте в интерфейс `ISampleInterface` следующую строку кода:</span><span class="sxs-lookup"><span data-stu-id="dcff9-212">Open the *SampleInterface.cs* or *SampleInterface.vb* file, and add the following line of code to the `ISampleInterface` interface:</span></span>

   ```csharp
   DateTime GetDate();
   ```

   ```vb
   Function GetDate() As Date
   ```

1. <span data-ttu-id="dcff9-213">Выберите **Файл** > **Сохранить все** или нажмите клавиши **CTRL**+**SHIFT**+**S** для сохранения файлов и проекта.</span><span class="sxs-lookup"><span data-stu-id="dcff9-213">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="dcff9-214">В **обозревателе решений** щелкните правой кнопкой мыши проект **TypeEquivalenceInterface** и выберите пункт **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-214">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Build**.</span></span> <span data-ttu-id="dcff9-215">Новая версия DLL-файла библиотеки классов компилируется и сохраняется по пути вывода сборки.</span><span class="sxs-lookup"><span data-stu-id="dcff9-215">A new version of the class library DLL file is compiled and saved to the build output path.</span></span>

## <a name="modify-the-runtime-class"></a><span data-ttu-id="dcff9-216">Изменение класса среды выполнения</span><span class="sxs-lookup"><span data-stu-id="dcff9-216">Modify the runtime class</span></span>

<span data-ttu-id="dcff9-217">Также измените класс среды выполнения и обновите его версию.</span><span class="sxs-lookup"><span data-stu-id="dcff9-217">Also modify the runtime class and update its version.</span></span>

1. <span data-ttu-id="dcff9-218">В Visual Studio выберите **Файл** > **Открыть** > **Проект/решение** и откройте проект **TypeEquivalenceRuntime**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-218">In Visual Studio, select **File** > **Open** > **Project/Solution**, and open the **TypeEquivalenceRuntime** project.</span></span>

1. <span data-ttu-id="dcff9-219">В **обозревателе решений** щелкните проект **TypeEquivalenceRuntime** правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-219">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Properties**.</span></span>

1. <span data-ttu-id="dcff9-220">Выберите **Приложение** в левой области экрана **Свойства** и элемент **Сведения о сборке**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-220">Select **Application** on the left pane of the **Properties** screen, and then select **Assembly Information**.</span></span>

1. <span data-ttu-id="dcff9-221">В диалоговом окне **Сведения о сборке** измените значения **Версия сборки** и **Версия файла** на *2.0.0.0* и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-221">In the **Assembly Information** dialog box, change the **Assembly version** and **File version** values to *2.0.0.0*, and then select **OK**.</span></span>

1. <span data-ttu-id="dcff9-222">Откройте файл *SampleClass.cs* или *SampleClass.vb* и добавьте в класс `SampleClass` следующий код:</span><span class="sxs-lookup"><span data-stu-id="dcff9-222">Open the *SampleClass.cs* or *SampleClass.vb* file, and add the following code to the `SampleClass` class:</span></span>

   ```csharp
    public DateTime GetDate()
    {
        return DateTime.Now;
    }
   ```

   ```vb
   Public Function GetDate() As DateTime Implements ISampleInterface.GetDate
       Return Now
   End Function
   ```

1. <span data-ttu-id="dcff9-223">Выберите **Файл** > **Сохранить все** или нажмите клавиши **CTRL**+**SHIFT**+**S** для сохранения файлов и проекта.</span><span class="sxs-lookup"><span data-stu-id="dcff9-223">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="dcff9-224">В **обозревателе решений** щелкните проект **TypeEquivalenceRuntime** правой кнопкой мыши и выберите **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="dcff9-224">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Build**.</span></span> <span data-ttu-id="dcff9-225">Новая версия DLL-файла библиотеки классов компилируется и сохраняется по пути вывода сборки.</span><span class="sxs-lookup"><span data-stu-id="dcff9-225">A new version of the class library DLL file is compiled and saved to the build output path.</span></span>

## <a name="run-the-updated-client-program"></a><span data-ttu-id="dcff9-226">Запуск обновленной клиентской программы</span><span class="sxs-lookup"><span data-stu-id="dcff9-226">Run the updated client program</span></span>

<span data-ttu-id="dcff9-227">Перейдите в папку вывода сборки и запустите *TypeEquivalenceClient.exe*.</span><span class="sxs-lookup"><span data-stu-id="dcff9-227">Go to the build output folder location and run *TypeEquivalenceClient.exe*.</span></span> <span data-ttu-id="dcff9-228">Обратите внимание, что выходные данные консоли теперь отражают новую версию сборки `TypeEquivalenceRuntime` — *2.0.0.0* — без повторной компиляции программы.</span><span class="sxs-lookup"><span data-stu-id="dcff9-228">Note that the console output now reflects the new version of the `TypeEquivalenceRuntime` assembly, *2.0.0.0*, without the program being recompiled.</span></span>

## <a name="see-also"></a><span data-ttu-id="dcff9-229">См. также</span><span class="sxs-lookup"><span data-stu-id="dcff9-229">See also</span></span>

- [<span data-ttu-id="dcff9-230">-link (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="dcff9-230">-link (C# Compiler Options)</span></span>](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [<span data-ttu-id="dcff9-231">-link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dcff9-231">-link (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/link.md)
- [<span data-ttu-id="dcff9-232">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="dcff9-232">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="dcff9-233">Основные понятия программирования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dcff9-233">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="dcff9-234">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="dcff9-234">Assemblies in .NET</span></span>](index.md)
