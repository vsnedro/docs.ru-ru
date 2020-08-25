---
title: Интерактивные параметры
description: Сведения о параметрах командной строки, поддерживаемых F# Interactive, fsi.exe.
ms.date: 08/15/2020
ms.openlocfilehash: adc8dc86f14366720e1acbf35115d4e318a76aef
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88810537"
---
# <a name="f-interactive-options"></a><span data-ttu-id="c02c3-103">Параметры F# Interactive</span><span class="sxs-lookup"><span data-stu-id="c02c3-103">F# Interactive options</span></span>

<span data-ttu-id="c02c3-104">В этой статье описываются параметры командной строки, поддерживаемые F# Interactive `fsi.exe` .</span><span class="sxs-lookup"><span data-stu-id="c02c3-104">This article describes the command-line options supported by F# Interactive, `fsi.exe`.</span></span> <span data-ttu-id="c02c3-105">F# Interactive принимает многие из тех же параметров командной строки, что и компилятор F #, но также принимает некоторые дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="c02c3-105">F# Interactive accepts many of the same command-line options as the F# compiler, but also accepts some additional options.</span></span>

## <a name="use-f-interactive-for-scripting"></a><span data-ttu-id="c02c3-106">Использование F# Interactive для создания сценариев</span><span class="sxs-lookup"><span data-stu-id="c02c3-106">Use F# Interactive for scripting</span></span>

<span data-ttu-id="c02c3-107">F# Interactive, `dotnet fsi` , можно запустить в интерактивном режиме или запустить из командной строки, чтобы выполнить сценарий.</span><span class="sxs-lookup"><span data-stu-id="c02c3-107">F# Interactive, `dotnet fsi`, can be launched interactively, or it can be launched from the command line to run a script.</span></span> <span data-ttu-id="c02c3-108">Синтаксис командной строки</span><span class="sxs-lookup"><span data-stu-id="c02c3-108">The command-line syntax is</span></span>

```dotnetcli
dotnet fsi [options] [ script-file [arguments] ]
```

<span data-ttu-id="c02c3-109">Расширение файла для файлов скриптов F #: `.fsx` .</span><span class="sxs-lookup"><span data-stu-id="c02c3-109">The file extension for F# script files is `.fsx`.</span></span>

## <a name="table-of-f-interactive-options"></a><span data-ttu-id="c02c3-110">Таблица параметров F# Interactive</span><span class="sxs-lookup"><span data-stu-id="c02c3-110">Table of F# Interactive Options</span></span>

<span data-ttu-id="c02c3-111">В следующей таблице перечислены параметры, поддерживаемые F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="c02c3-111">The following table summarizes the options supported by F# Interactive.</span></span> <span data-ttu-id="c02c3-112">Эти параметры можно задать в командной строке или в интегрированной среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c02c3-112">You can set these options on the command line or through the Visual Studio IDE.</span></span> <span data-ttu-id="c02c3-113">Чтобы задать эти параметры в интегрированной среде разработки Visual Studio, откройте меню **Сервис** , выберите **Параметры**, разверните узел **инструменты F #** и выберите **F# Interactive**.</span><span class="sxs-lookup"><span data-stu-id="c02c3-113">To set these options in the Visual Studio IDE, open the **Tools** menu, select **Options**, expand the **F# Tools** node, and then select **F# Interactive**.</span></span>

<span data-ttu-id="c02c3-114">Когда списки отображаются в аргументах параметров F# Interactive, элементы списка разделяются точкой с запятой ( `;` ).</span><span class="sxs-lookup"><span data-stu-id="c02c3-114">Where lists appear in F# Interactive option arguments, list elements are separated by semicolons (`;`).</span></span>

|<span data-ttu-id="c02c3-115">Параметр</span><span class="sxs-lookup"><span data-stu-id="c02c3-115">Option</span></span>|<span data-ttu-id="c02c3-116">Описание</span><span class="sxs-lookup"><span data-stu-id="c02c3-116">Description</span></span>|
|------|-----------|
|**--**|<span data-ttu-id="c02c3-117">Используется для указания F# Interactive рассматривать оставшиеся аргументы как аргументы командной строки для программы или скрипта F #, доступ к которым можно получить в коде с помощью списка **FSI. CommandLineArgs**.</span><span class="sxs-lookup"><span data-stu-id="c02c3-117">Used to instruct F# Interactive to treat remaining arguments as command-line arguments to the F# program or script, which you can access in code by using the list **fsi.CommandLineArgs**.</span></span>|
|<span data-ttu-id="c02c3-118">**--checked**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c02c3-118">**--checked**[**+**&#124;**-**]</span></span>|<span data-ttu-id="c02c3-119">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c02c3-119">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c02c3-120">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c02c3-120">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c02c3-121">**--codepage: &lt; int&gt;**</span><span class="sxs-lookup"><span data-stu-id="c02c3-121">**--codepage:&lt;int&gt;**</span></span>|<span data-ttu-id="c02c3-122">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c02c3-122">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c02c3-123">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c02c3-123">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c02c3-124">**--консолеколорс**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c02c3-124">**--consolecolors**[**+**&#124;**-**]</span></span>|<span data-ttu-id="c02c3-125">Выводит предупреждения и сообщения об ошибках в цвете.</span><span class="sxs-lookup"><span data-stu-id="c02c3-125">Outputs warning and error messages in color.</span></span>|
|<span data-ttu-id="c02c3-126">**--кроссоптимизе**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c02c3-126">**--crossoptimize**[**+**&#124;**-**]</span></span>|<span data-ttu-id="c02c3-127">Включает или отключает оптимизацию между модулями.</span><span class="sxs-lookup"><span data-stu-id="c02c3-127">Enable or disable cross-module optimizations.</span></span>|
|<span data-ttu-id="c02c3-128">**--Debug**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c02c3-128">**--debug**[**+**&#124;**-**]</span></span><br /><br /><span data-ttu-id="c02c3-129">**--Debug:**[**полный**&#124;**pdbonly**&#124;**переносимый**&#124;**Embedded**]</span><span class="sxs-lookup"><span data-stu-id="c02c3-129">**--debug:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]</span></span><br /><br /><span data-ttu-id="c02c3-130">**-g**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c02c3-130">**-g**[**+**&#124;**-**]</span></span><br /><br /><span data-ttu-id="c02c3-131">**-g:**[**полный**&#124;**pdbonly**&#124;**переносимый**&#124;**Embedded**]</span><span class="sxs-lookup"><span data-stu-id="c02c3-131">**-g:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]</span></span>|<span data-ttu-id="c02c3-132">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c02c3-132">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c02c3-133">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c02c3-133">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c02c3-134">**--define: &lt; строка&gt;**</span><span class="sxs-lookup"><span data-stu-id="c02c3-134">**--define:&lt;string&gt;**</span></span>|<span data-ttu-id="c02c3-135">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c02c3-135">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c02c3-136">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c02c3-136">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c02c3-137">**--детерминированный**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c02c3-137">**--deterministic**[**+**&#124;**-**]</span></span>|<span data-ttu-id="c02c3-138">Создает детерминированную сборку (включая GUID версии модуля и метку времени).</span><span class="sxs-lookup"><span data-stu-id="c02c3-138">Produces a deterministic assembly (including module version GUID and timestamp).</span></span>|
|<span data-ttu-id="c02c3-139">**--Exec**</span><span class="sxs-lookup"><span data-stu-id="c02c3-139">**--exec**</span></span>|<span data-ttu-id="c02c3-140">Инструктирует F # Interactive для выхода после загрузки файлов или запуска файла скрипта, заданного в командной строке.</span><span class="sxs-lookup"><span data-stu-id="c02c3-140">Instructs F# interactive to exit after loading the files or running the script file given on the command line.</span></span>|
|<span data-ttu-id="c02c3-141">**--fullpaths**</span><span class="sxs-lookup"><span data-stu-id="c02c3-141">**--fullpaths**</span></span>|<span data-ttu-id="c02c3-142">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c02c3-142">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c02c3-143">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c02c3-143">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c02c3-144">**--GUI**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c02c3-144">**--gui**[**+**&#124;**-**]</span></span>|<span data-ttu-id="c02c3-145">Включает или отключает цикл обработки событий Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c02c3-145">Enables or disables the Windows Forms event loop.</span></span> <span data-ttu-id="c02c3-146">По умолчанию этот параметр включен.</span><span class="sxs-lookup"><span data-stu-id="c02c3-146">The default is enabled.</span></span>|
|<span data-ttu-id="c02c3-147">**--Справка**</span><span class="sxs-lookup"><span data-stu-id="c02c3-147">**--help**</span></span><br /><br /><span data-ttu-id="c02c3-148">**-?**</span><span class="sxs-lookup"><span data-stu-id="c02c3-148">**-?**</span></span>|<span data-ttu-id="c02c3-149">Используется для вывода синтаксиса командной строки и краткого описания каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="c02c3-149">Used to display the command-line syntax and a brief description of each option.</span></span>|
|<span data-ttu-id="c02c3-150">**--lib: &lt; Папка-список&gt;**</span><span class="sxs-lookup"><span data-stu-id="c02c3-150">**--lib:&lt;folder-list&gt;**</span></span><br /><br /><span data-ttu-id="c02c3-151">**-I: &lt; Папка-список&gt;**</span><span class="sxs-lookup"><span data-stu-id="c02c3-151">**-I:&lt;folder-list&gt;**</span></span>|<span data-ttu-id="c02c3-152">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c02c3-152">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c02c3-153">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c02c3-153">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c02c3-154">**--Load: &lt; имя файла&gt;**</span><span class="sxs-lookup"><span data-stu-id="c02c3-154">**--load:&lt;filename&gt;**</span></span>|<span data-ttu-id="c02c3-155">Компилирует заданный исходный код при запуске и загружает скомпилированные конструкции F # в сеанс.</span><span class="sxs-lookup"><span data-stu-id="c02c3-155">Compiles the given source code at startup and loads the compiled F# constructs into the session.</span></span>|
|<span data-ttu-id="c02c3-156">**--млкомпатибилити**</span><span class="sxs-lookup"><span data-stu-id="c02c3-156">**--mlcompatibility**</span></span>|<span data-ttu-id="c02c3-157">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c02c3-157">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c02c3-158">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c02c3-158">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c02c3-159">**--.NET Framework**</span><span class="sxs-lookup"><span data-stu-id="c02c3-159">**--noframework**</span></span>|<span data-ttu-id="c02c3-160">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c02c3-160">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c02c3-161">Дополнительные сведения см. в разделе [параметры компилятора](compiler-options.md) .</span><span class="sxs-lookup"><span data-stu-id="c02c3-161">For more information, see [Compiler Options](compiler-options.md)</span></span>|
|<span data-ttu-id="c02c3-162">**--Эмблема**</span><span class="sxs-lookup"><span data-stu-id="c02c3-162">**--nologo**</span></span>|<span data-ttu-id="c02c3-163">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c02c3-163">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c02c3-164">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c02c3-164">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c02c3-165">**--warn: &lt; warning-List&gt;**</span><span class="sxs-lookup"><span data-stu-id="c02c3-165">**--nowarn:&lt;warning-list&gt;**</span></span>|<span data-ttu-id="c02c3-166">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c02c3-166">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c02c3-167">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c02c3-167">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c02c3-168">**--optimize**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c02c3-168">**--optimize**[**+**&#124;**-**]</span></span>|<span data-ttu-id="c02c3-169">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c02c3-169">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c02c3-170">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c02c3-170">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c02c3-171">**--preferreduilang: &lt; lang&gt;**</span><span class="sxs-lookup"><span data-stu-id="c02c3-171">**--preferreduilang:&lt;lang&gt;**</span></span>| <span data-ttu-id="c02c3-172">Указывает предпочтительное имя языка и региональных параметров на языке вывода (например, ES-ES, ja-JP).</span><span class="sxs-lookup"><span data-stu-id="c02c3-172">Specifies the preferred output language culture name (for example, es-ES, ja-JP).</span></span> |
|<span data-ttu-id="c02c3-173">**--quiet**</span><span class="sxs-lookup"><span data-stu-id="c02c3-173">**--quiet**</span></span>|<span data-ttu-id="c02c3-174">Подавление вывода F# Interactive в поток **stdout** .</span><span class="sxs-lookup"><span data-stu-id="c02c3-174">Suppress F# Interactive's output to the **stdout** stream.</span></span>|
|<span data-ttu-id="c02c3-175">**--предложения-Отладка**</span><span class="sxs-lookup"><span data-stu-id="c02c3-175">**--quotations-debug**</span></span>|<span data-ttu-id="c02c3-176">Указывает, что необходимо создавать дополнительные отладочные данные для выражений, которые являются производными от литералов в кавычках F # и отраженными определениями.</span><span class="sxs-lookup"><span data-stu-id="c02c3-176">Specifies that extra debugging information should be emitted for expressions that are derived from F# quotation literals and reflected definitions.</span></span> <span data-ttu-id="c02c3-177">Отладочная информация добавляется к пользовательским атрибутам узла дерева выражений F #.</span><span class="sxs-lookup"><span data-stu-id="c02c3-177">The debug information is added to the custom attributes of an F# expression tree node.</span></span> <span data-ttu-id="c02c3-178">См. раздел [цитирование кода](code-quotations.md) и [выражение expr. CustomAttributes](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html#CustomAttributes).</span><span class="sxs-lookup"><span data-stu-id="c02c3-178">See [Code Quotations](code-quotations.md) and [Expr.CustomAttributes](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html#CustomAttributes).</span></span>|
|<span data-ttu-id="c02c3-179">**--ReadLine**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c02c3-179">**--readline**[**+**&#124;**-**]</span></span>|<span data-ttu-id="c02c3-180">Включение или отключение заполнения нажатием клавиши TAB в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="c02c3-180">Enable or disable tab completion in interactive mode.</span></span>|
|<span data-ttu-id="c02c3-181">**--Reference: &lt; имя файла&gt;**</span><span class="sxs-lookup"><span data-stu-id="c02c3-181">**--reference:&lt;filename&gt;**</span></span><br /><br /><span data-ttu-id="c02c3-182">**-r: &lt; имя файла&gt;**</span><span class="sxs-lookup"><span data-stu-id="c02c3-182">**-r:&lt;filename&gt;**</span></span>|<span data-ttu-id="c02c3-183">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c02c3-183">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c02c3-184">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c02c3-184">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c02c3-185">**--таилкаллс**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c02c3-185">**--tailcalls**[**+**&#124;**-**]</span></span>|<span data-ttu-id="c02c3-186">Включение или выключение использования инструкции IL, которая приводит к повторному использованию кадра стека для заключительных рекурсивных функций.</span><span class="sxs-lookup"><span data-stu-id="c02c3-186">Enable or disable the use of the tail IL instruction, which causes the stack frame to be reused for tail recursive functions.</span></span> <span data-ttu-id="c02c3-187">Этот параметр по умолчанию включен.</span><span class="sxs-lookup"><span data-stu-id="c02c3-187">This option is enabled by default.</span></span>|
|<span data-ttu-id="c02c3-188">**--targetprofile: &lt; строка&gt;**</span><span class="sxs-lookup"><span data-stu-id="c02c3-188">**--targetprofile:&lt;string&gt;**</span></span>|<span data-ttu-id="c02c3-189">Указывает профиль целевой платформы для этой сборки.</span><span class="sxs-lookup"><span data-stu-id="c02c3-189">Specifies target framework profile of this assembly.</span></span> <span data-ttu-id="c02c3-190">Допустимые значения: `mscorlib`, `netcore` или `netstandard`.</span><span class="sxs-lookup"><span data-stu-id="c02c3-190">Valid values are `mscorlib`, `netcore`, or `netstandard`.</span></span> <span data-ttu-id="c02c3-191">Значение по умолчанию — `mscorlib`.</span><span class="sxs-lookup"><span data-stu-id="c02c3-191">The default is `mscorlib`.</span></span>|
|<span data-ttu-id="c02c3-192">**--использовать: &lt; имя файла&gt;**</span><span class="sxs-lookup"><span data-stu-id="c02c3-192">**--use:&lt;filename&gt;**</span></span>|<span data-ttu-id="c02c3-193">Указывает интерпретатору использовать заданный файл при запуске в качестве начального ввода.</span><span class="sxs-lookup"><span data-stu-id="c02c3-193">Tells the interpreter to use the given file on startup as initial input.</span></span>|
|<span data-ttu-id="c02c3-194">**--utf8output**</span><span class="sxs-lookup"><span data-stu-id="c02c3-194">**--utf8output**</span></span>|<span data-ttu-id="c02c3-195">То же, что и параметр компилятора fsc.exe.</span><span class="sxs-lookup"><span data-stu-id="c02c3-195">Same as the fsc.exe compiler option.</span></span> <span data-ttu-id="c02c3-196">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c02c3-196">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c02c3-197">**--warn: &lt; уровень предупреждения&gt;**</span><span class="sxs-lookup"><span data-stu-id="c02c3-197">**--warn:&lt;warning-level&gt;**</span></span>|<span data-ttu-id="c02c3-198">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c02c3-198">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c02c3-199">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c02c3-199">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c02c3-200">**--warnaserror**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="c02c3-200">**--warnaserror**[**+**&#124;**-**]</span></span>|<span data-ttu-id="c02c3-201">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c02c3-201">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c02c3-202">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c02c3-202">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="c02c3-203">**--warnaserror**[ **+**&#124;**-** ]:\*\* &lt; int-List &gt; \*\*</span><span class="sxs-lookup"><span data-stu-id="c02c3-203">**--warnaserror**[**+**&#124;**-**]:**&lt;int-list&gt;**</span></span>|<span data-ttu-id="c02c3-204">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="c02c3-204">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="c02c3-205">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="c02c3-205">For more information, see [Compiler Options](compiler-options.md).</span></span>|

## <a name="f-interactive-structured-printing"></a><span data-ttu-id="c02c3-206">F# Interactive структурированной печати</span><span class="sxs-lookup"><span data-stu-id="c02c3-206">F# Interactive structured printing</span></span>

<span data-ttu-id="c02c3-207">F# Interactive ( `dotnet fsi` ) использует расширенную версию [структурированного форматирования обычного текста](plaintext-formatting.md) для передачи значений.</span><span class="sxs-lookup"><span data-stu-id="c02c3-207">F# Interactive (`dotnet fsi`) uses an extended version of [structured plain text formatting](plaintext-formatting.md) to report values.</span></span>

1. <span data-ttu-id="c02c3-208">`%A`Поддерживаются все функции форматирования обычного текста, некоторые из которых также можно настроить.</span><span class="sxs-lookup"><span data-stu-id="c02c3-208">All features of `%A` plain text formatting are supported, and some are additionally customizable.</span></span>

2. <span data-ttu-id="c02c3-209">Печать выводится цветом, если в консоли вывода поддерживаются цвета.</span><span class="sxs-lookup"><span data-stu-id="c02c3-209">Printing is colorized if colors are supported by the output console.</span></span>

3. <span data-ttu-id="c02c3-210">Ограничение размещается на отображаемой длине строк, если только вы явно не Вычислите эту строку.</span><span class="sxs-lookup"><span data-stu-id="c02c3-210">A limit is placed on the length of strings shown, unless you explicitly evaluate that string.</span></span>

4. <span data-ttu-id="c02c3-211">Набор определяемых пользователем параметров доступен через `fsi` объект.</span><span class="sxs-lookup"><span data-stu-id="c02c3-211">A set of user-definable settings is available via the `fsi` object.</span></span>

<span data-ttu-id="c02c3-212">Доступные параметры для настройки печати в виде обычного текста для сообщаемых значений:</span><span class="sxs-lookup"><span data-stu-id="c02c3-212">The available settings to customize plain text printing for reported values are:</span></span>

```fsharp
open System.Globalization

fsi.FormatProvider <- CultureInfo("de-DE")  // control the default culture for primitives

fsi.PrintWidth <- 120        // Control the width used for structured printing

fsi.PrintDepth <- 10         // Control the maximum depth of nested printing

fsi.PrintLength <- 10        // Control the length of lists and arrays

fsi.PrintSize <- 100         // Control the maximum overall object count

fsi.ShowProperties <- false  // Control whether properties of .NET objects are shown by default

fsi.ShowIEnumerable <- false // Control whether sequence values are expanded by default

fsi.ShowDeclarationValues <- false // Control whether values are shown for declaration outputs
```

### <a name="customize-with-addprinter-and-addprinttransformer"></a><span data-ttu-id="c02c3-213">Настройка с помощью `AddPrinter` и `AddPrintTransformer`</span><span class="sxs-lookup"><span data-stu-id="c02c3-213">Customize with `AddPrinter` and `AddPrintTransformer`</span></span>

<span data-ttu-id="c02c3-214">Печать в F# Interactive выходных данных может быть настроена с помощью `fsi.AddPrinter` и `fsi.AddPrintTransformer` .</span><span class="sxs-lookup"><span data-stu-id="c02c3-214">Printing in F# Interactive outputs can be customized by using `fsi.AddPrinter` and `fsi.AddPrintTransformer`.</span></span>
<span data-ttu-id="c02c3-215">Первая функция предоставляет текст для замены печати объекта.</span><span class="sxs-lookup"><span data-stu-id="c02c3-215">The first function gives text to replace the printing of an object.</span></span> <span data-ttu-id="c02c3-216">Вторая функция возвращает суррогатный объект для вывода вместо этого.</span><span class="sxs-lookup"><span data-stu-id="c02c3-216">The second function returns a surrogate object to display instead.</span></span> <span data-ttu-id="c02c3-217">Например, рассмотрим следующий код F #:</span><span class="sxs-lookup"><span data-stu-id="c02c3-217">For example, consider the following F# code:</span></span>

```fsharp
open System

fsi.AddPrinter<DateTime>(fun dt -> dt.ToString("s"))

type DateAndLabel =
    { Date: DateTime
      Label: string  }

let newYearsDay1999 =
    { Date = DateTime(1999, 1, 1)
      Label = "New Year" }
```

<span data-ttu-id="c02c3-218">Если выполнить пример в F# Interactive, он выводится на основе набора параметров форматирования.</span><span class="sxs-lookup"><span data-stu-id="c02c3-218">If you execute the example in F# Interactive, it outputs based on the formatting option set.</span></span> <span data-ttu-id="c02c3-219">В этом случае это влияет на форматирование даты и времени:</span><span class="sxs-lookup"><span data-stu-id="c02c3-219">In this case, it affects the formatting of date and time:</span></span>

```console
type DateAndLabel =
  { Date: DateTime
    Label: string }
val newYearsDay1999 : DateAndLabel = { Date = 1999-01-01T00:00:00
                                       Label = "New Year" }
```

<span data-ttu-id="c02c3-220">`fsi.AddPrintTransformer` можно использовать, чтобы предоставить суррогатный объект для печати:</span><span class="sxs-lookup"><span data-stu-id="c02c3-220">`fsi.AddPrintTransformer` can be used to give a surrogate object for printing:</span></span>

```fsharp
type MyList(values: int list) =
    member _.Values = values

fsi.AddPrintTransformer(fun (x:MyList) -> box x.Values)

let x = MyList([1..10])
```

<span data-ttu-id="c02c3-221">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c02c3-221">This outputs:</span></span>

```console
val x : MyList = [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
```

<span data-ttu-id="c02c3-222">Если функция преобразователь `fsi.AddPrintTransformer` , передаваемая `null` , возвращает, то преобразователь печати игнорируется.</span><span class="sxs-lookup"><span data-stu-id="c02c3-222">If the transformer function passed to `fsi.AddPrintTransformer` returns `null`, then the print transformer is ignored.</span></span>
<span data-ttu-id="c02c3-223">Это можно использовать для фильтрации любого входного значения, начиная с Type `obj` .</span><span class="sxs-lookup"><span data-stu-id="c02c3-223">This can be used to filter any input value by starting with type `obj`.</span></span>  <span data-ttu-id="c02c3-224">Пример:</span><span class="sxs-lookup"><span data-stu-id="c02c3-224">For example:</span></span>

```fsharp
fsi.AddPrintTransformer(fun (x:obj) ->
    match x with
    | :? string as s when s = "beep" -> box ["quack"; "quack"; "quack"]
    | _ -> null)

let y = "beep"
```

<span data-ttu-id="c02c3-225">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c02c3-225">This outputs:</span></span>

```console
val y : string = ["quack"; "quack"; "quack"]
```

## <a name="related-topics"></a><span data-ttu-id="c02c3-226">См. также</span><span class="sxs-lookup"><span data-stu-id="c02c3-226">Related topics</span></span>

|<span data-ttu-id="c02c3-227">Заголовок</span><span class="sxs-lookup"><span data-stu-id="c02c3-227">Title</span></span>|<span data-ttu-id="c02c3-228">Описание</span><span class="sxs-lookup"><span data-stu-id="c02c3-228">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="c02c3-229">Параметры компилятора</span><span class="sxs-lookup"><span data-stu-id="c02c3-229">Compiler Options</span></span>](compiler-options.md)|<span data-ttu-id="c02c3-230">Описывает параметры командной строки, доступные для компилятора F # **fsc.exe**.</span><span class="sxs-lookup"><span data-stu-id="c02c3-230">Describes command-line options available for the F# compiler, **fsc.exe**.</span></span>|
