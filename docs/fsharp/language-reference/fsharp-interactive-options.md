---
title: Интерактивные параметры
description: Сведения о параметрах командной строки, поддерживаемых F# Interactive, fsi.exe.
ms.date: 07/22/2020
ms.openlocfilehash: f9932cac24fad187c332306968fb13981912e80a
ms.sourcegitcommit: 09bad6ec0cbf18be7cd7f62e77286d305a18b607
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87795467"
---
# <a name="f-interactive-options"></a><span data-ttu-id="b3bcd-103">Параметры F# Interactive</span><span class="sxs-lookup"><span data-stu-id="b3bcd-103">F# Interactive options</span></span>

<span data-ttu-id="b3bcd-104">В этой статье описываются параметры командной строки, поддерживаемые F# Interactive `fsi.exe` .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-104">This article describes the command-line options supported by F# Interactive, `fsi.exe`.</span></span> <span data-ttu-id="b3bcd-105">F# Interactive принимает многие из тех же параметров командной строки, что и компилятор F #, но также принимает некоторые дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-105">F# Interactive accepts many of the same command line options as the F# compiler, but also accepts some additional options.</span></span>

## <a name="use-f-interactive-for-scripting"></a><span data-ttu-id="b3bcd-106">Использование F# Interactive для создания сценариев</span><span class="sxs-lookup"><span data-stu-id="b3bcd-106">Use F# Interactive for scripting</span></span>

<span data-ttu-id="b3bcd-107">F# Interactive, `dotnet fsi` , можно запустить в интерактивном режиме или запустить из командной строки, чтобы выполнить сценарий.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-107">F# Interactive, `dotnet fsi`, can be launched interactively, or it can be launched from the command line to run a script.</span></span> <span data-ttu-id="b3bcd-108">Синтаксис командной строки:</span><span class="sxs-lookup"><span data-stu-id="b3bcd-108">The command line syntax is</span></span>

```dotnetcli
dotnet fsi [options] [ script-file [arguments] ]
```

<span data-ttu-id="b3bcd-109">Расширение файла для файлов скриптов F #: `.fsx` .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-109">The file extension for F# script files is `.fsx`.</span></span>

## <a name="table-of-f-interactive-options"></a><span data-ttu-id="b3bcd-110">Таблица параметров F# Interactive</span><span class="sxs-lookup"><span data-stu-id="b3bcd-110">Table of F# Interactive Options</span></span>

<span data-ttu-id="b3bcd-111">В следующей таблице перечислены параметры, поддерживаемые F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-111">The following table summarizes the options supported by F# Interactive.</span></span> <span data-ttu-id="b3bcd-112">Эти параметры можно задать в командной строке или в интегрированной среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-112">You can set these options on the command-line or through the Visual Studio IDE.</span></span> <span data-ttu-id="b3bcd-113">Чтобы задать эти параметры в интегрированной среде разработки Visual Studio, откройте меню **Сервис** , выберите **Параметры...**, а затем разверните узел **инструменты F #** и выберите **F# Interactive**.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-113">To set these options in the Visual Studio IDE, open the **Tools** menu, select **Options...**, then expand the **F# Tools** node and select **F# Interactive**.</span></span>

<span data-ttu-id="b3bcd-114">Когда списки отображаются в аргументах параметров F# Interactive, элементы списка разделяются точкой с запятой ( `;` ).</span><span class="sxs-lookup"><span data-stu-id="b3bcd-114">Where lists appear in F# Interactive option arguments, list elements are separated by semicolons (`;`).</span></span>

|<span data-ttu-id="b3bcd-115">Параметр</span><span class="sxs-lookup"><span data-stu-id="b3bcd-115">Option</span></span>|<span data-ttu-id="b3bcd-116">Описание</span><span class="sxs-lookup"><span data-stu-id="b3bcd-116">Description</span></span>|
|------|-----------|
|**--**|<span data-ttu-id="b3bcd-117">Используется для указания F# Interactive рассматривать оставшиеся аргументы как аргументы командной строки для программы или скрипта F #, доступ к которым можно получить в коде с помощью списка **FSI. CommandLineArgs**.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-117">Used to instruct F# Interactive to treat remaining arguments as command line arguments to the F# program or script, which you can access in code by using the list **fsi.CommandLineArgs**.</span></span>|
|<span data-ttu-id="b3bcd-118">**--checked**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b3bcd-118">**--checked**[**+**&#124;**-**]</span></span>|<span data-ttu-id="b3bcd-119">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-119">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b3bcd-120">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="b3bcd-120">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b3bcd-121">**--codepage: &lt; int&gt;**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-121">**--codepage:&lt;int&gt;**</span></span>|<span data-ttu-id="b3bcd-122">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-122">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b3bcd-123">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="b3bcd-123">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b3bcd-124">**--консолеколорс**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b3bcd-124">**--consolecolors**[**+**&#124;**-**]</span></span>|<span data-ttu-id="b3bcd-125">Выводит предупреждения и сообщения об ошибках в цвете.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-125">Outputs warning and error messages in color.</span></span>|
|<span data-ttu-id="b3bcd-126">**--кроссоптимизе**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b3bcd-126">**--crossoptimize**[**+**&#124;**-**]</span></span>|<span data-ttu-id="b3bcd-127">Включает или отключает оптимизацию между модулями.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-127">Enable or disable cross-module optimizations.</span></span>|
|<span data-ttu-id="b3bcd-128">**--Debug**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b3bcd-128">**--debug**[**+**&#124;**-**]</span></span><br /><br /><span data-ttu-id="b3bcd-129">**--Debug:**[**полный**&#124;**pdbonly**&#124;**переносимый**&#124;**Embedded**]</span><span class="sxs-lookup"><span data-stu-id="b3bcd-129">**--debug:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]</span></span><br /><br /><span data-ttu-id="b3bcd-130">**-g**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b3bcd-130">**-g**[**+**&#124;**-**]</span></span><br /><br /><span data-ttu-id="b3bcd-131">**-g:**[**полный**&#124;**pdbonly**&#124;**переносимый**&#124;**Embedded**]</span><span class="sxs-lookup"><span data-stu-id="b3bcd-131">**-g:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]</span></span>|<span data-ttu-id="b3bcd-132">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-132">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b3bcd-133">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="b3bcd-133">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b3bcd-134">**--define: &lt; строка&gt;**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-134">**--define:&lt;string&gt;**</span></span>|<span data-ttu-id="b3bcd-135">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-135">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b3bcd-136">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="b3bcd-136">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b3bcd-137">**--детерминированный**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b3bcd-137">**--deterministic**[**+**&#124;**-**]</span></span>|<span data-ttu-id="b3bcd-138">Создает детерминированную сборку (включая GUID версии модуля и метку времени).</span><span class="sxs-lookup"><span data-stu-id="b3bcd-138">Produces a deterministic assembly (including module version GUID and timestamp).</span></span>|
|<span data-ttu-id="b3bcd-139">**--Exec**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-139">**--exec**</span></span>|<span data-ttu-id="b3bcd-140">Инструктирует F # Interactive для выхода после загрузки файлов или запуска файла скрипта, заданного в командной строке.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-140">Instructs F# interactive to exit after loading the files or running the script file given on the command line.</span></span>|
|<span data-ttu-id="b3bcd-141">**--fullpaths**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-141">**--fullpaths**</span></span>|<span data-ttu-id="b3bcd-142">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-142">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b3bcd-143">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="b3bcd-143">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b3bcd-144">**--GUI**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b3bcd-144">**--gui**[**+**&#124;**-**]</span></span>|<span data-ttu-id="b3bcd-145">Включает или отключает цикл обработки событий Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-145">Enables or disables the Windows Forms event loop.</span></span> <span data-ttu-id="b3bcd-146">По умолчанию этот параметр включен.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-146">The default is enabled.</span></span>|
|<span data-ttu-id="b3bcd-147">**--Справка**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-147">**--help**</span></span><br /><br /><span data-ttu-id="b3bcd-148">**-?**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-148">**-?**</span></span>|<span data-ttu-id="b3bcd-149">Используется для вывода синтаксиса командной строки и краткого описания каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-149">Used to display the command line syntax and a brief description of each option.</span></span>|
|<span data-ttu-id="b3bcd-150">**--lib: &lt; Папка-список&gt;**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-150">**--lib:&lt;folder-list&gt;**</span></span><br /><br /><span data-ttu-id="b3bcd-151">**-I: &lt; Папка-список&gt;**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-151">**-I:&lt;folder-list&gt;**</span></span>|<span data-ttu-id="b3bcd-152">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-152">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b3bcd-153">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="b3bcd-153">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b3bcd-154">**--Load: &lt; имя файла&gt;**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-154">**--load:&lt;filename&gt;**</span></span>|<span data-ttu-id="b3bcd-155">Компилирует заданный исходный код при запуске и загружает скомпилированные конструкции F # в сеанс.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-155">Compiles the given source code at startup and loads the compiled F# constructs into the session.</span></span> <span data-ttu-id="b3bcd-156">Если целевой источник содержит директивы скрипта, такие как **#use** или **#load**, необходимо использовать параметр **--use** или **#use** вместо **--Load** или **#load**.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-156">If the target source contains scripting directives such as **#use** or **#load**, then you must use **--use** or **#use** instead of **--load** or **#load**.</span></span>|
|<span data-ttu-id="b3bcd-157">**--млкомпатибилити**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-157">**--mlcompatibility**</span></span>|<span data-ttu-id="b3bcd-158">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-158">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b3bcd-159">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="b3bcd-159">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b3bcd-160">**--.NET Framework**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-160">**--noframework**</span></span>|<span data-ttu-id="b3bcd-161">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-161">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b3bcd-162">Дополнительные сведения см. в разделе [параметры компилятора](compiler-options.md) .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-162">For more information, see [Compiler Options](compiler-options.md)</span></span>|
|<span data-ttu-id="b3bcd-163">**--Эмблема**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-163">**--nologo**</span></span>|<span data-ttu-id="b3bcd-164">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-164">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b3bcd-165">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="b3bcd-165">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b3bcd-166">**--warn: &lt; warning-List&gt;**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-166">**--nowarn:&lt;warning-list&gt;**</span></span>|<span data-ttu-id="b3bcd-167">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-167">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b3bcd-168">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="b3bcd-168">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b3bcd-169">**--optimize**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b3bcd-169">**--optimize**[**+**&#124;**-**]</span></span>|<span data-ttu-id="b3bcd-170">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-170">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b3bcd-171">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="b3bcd-171">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b3bcd-172">**--preferreduilang: &lt; lang&gt;**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-172">**--preferreduilang:&lt;lang&gt;**</span></span>| <span data-ttu-id="b3bcd-173">Указывает предпочтительное имя языка и региональных параметров на языке вывода (например, ES-ES, ja-JP).</span><span class="sxs-lookup"><span data-stu-id="b3bcd-173">Specifies the preferred output language culture name (for example, es-ES, ja-JP).</span></span> |
|<span data-ttu-id="b3bcd-174">**--quiet**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-174">**--quiet**</span></span>|<span data-ttu-id="b3bcd-175">Подавление вывода F# Interactive в поток **stdout** .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-175">Suppress F# Interactive's output to the **stdout** stream.</span></span>|
|<span data-ttu-id="b3bcd-176">**--предложения-Отладка**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-176">**--quotations-debug**</span></span>|<span data-ttu-id="b3bcd-177">Указывает, что необходимо создавать дополнительные отладочные данные для выражений, которые являются производными от литералов в кавычках F # и отраженными определениями.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-177">Specifies that extra debugging information should be emitted for expressions that are derived from F# quotation literals and reflected definitions.</span></span> <span data-ttu-id="b3bcd-178">Отладочная информация добавляется к пользовательским атрибутам узла дерева выражений F #.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-178">The debug information is added to the custom attributes of an F# expression tree node.</span></span> <span data-ttu-id="b3bcd-179">См. раздел [цитирование кода](code-quotations.md) и [выражение expr. CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).</span><span class="sxs-lookup"><span data-stu-id="b3bcd-179">See [Code Quotations](code-quotations.md) and [Expr.CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).</span></span>|
|<span data-ttu-id="b3bcd-180">**--ReadLine**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b3bcd-180">**--readline**[**+**&#124;**-**]</span></span>|<span data-ttu-id="b3bcd-181">Включение или отключение заполнения нажатием клавиши TAB в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-181">Enable or disable tab completion in interactive mode.</span></span>|
|<span data-ttu-id="b3bcd-182">**--Reference: &lt; имя файла&gt;**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-182">**--reference:&lt;filename&gt;**</span></span><br /><br /><span data-ttu-id="b3bcd-183">**-r: &lt; имя файла&gt;**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-183">**-r:&lt;filename&gt;**</span></span>|<span data-ttu-id="b3bcd-184">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-184">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b3bcd-185">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="b3bcd-185">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b3bcd-186">**--таилкаллс**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b3bcd-186">**--tailcalls**[**+**&#124;**-**]</span></span>|<span data-ttu-id="b3bcd-187">Включение или выключение использования инструкции IL, которая приводит к повторному использованию кадра стека для заключительных рекурсивных функций.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-187">Enable or disable the use of the tail IL instruction, which causes the stack frame to be reused for tail recursive functions.</span></span> <span data-ttu-id="b3bcd-188">Этот параметр по умолчанию включен.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-188">This option is enabled by default.</span></span>|
|<span data-ttu-id="b3bcd-189">**--targetprofile: &lt; строка&gt;**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-189">**--targetprofile:&lt;string&gt;**</span></span>|<span data-ttu-id="b3bcd-190">Указывает профиль целевой платформы для этой сборки.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-190">Specifies target framework profile of this assembly.</span></span> <span data-ttu-id="b3bcd-191">Допустимые значения: mscorlib, netcore или netstandard.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-191">Valid values are mscorlib, netcore or netstandard.</span></span>  <span data-ttu-id="b3bcd-192">Значение по умолчанию — mscorlib.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-192">The default is mscorlib.</span></span>|
|<span data-ttu-id="b3bcd-193">**--использовать: &lt; имя файла&gt;**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-193">**--use:&lt;filename&gt;**</span></span>|<span data-ttu-id="b3bcd-194">Указывает интерпретатору использовать заданный файл при запуске в качестве начального ввода.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-194">Tells the interpreter to use the given file on startup as initial input.</span></span>|
|<span data-ttu-id="b3bcd-195">**--utf8output**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-195">**--utf8output**</span></span>|<span data-ttu-id="b3bcd-196">То же, что и параметр компилятора fsc.exe.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-196">Same as the fsc.exe compiler option.</span></span> <span data-ttu-id="b3bcd-197">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="b3bcd-197">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b3bcd-198">**--warn: &lt; уровень предупреждения&gt;**</span><span class="sxs-lookup"><span data-stu-id="b3bcd-198">**--warn:&lt;warning-level&gt;**</span></span>|<span data-ttu-id="b3bcd-199">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-199">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b3bcd-200">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="b3bcd-200">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b3bcd-201">**--warnaserror**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b3bcd-201">**--warnaserror**[**+**&#124;**-**]</span></span>|<span data-ttu-id="b3bcd-202">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-202">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b3bcd-203">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="b3bcd-203">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b3bcd-204">**--warnaserror**[ **+**&#124;**-** ]:\*\* &lt; int-List &gt; \*\*</span><span class="sxs-lookup"><span data-stu-id="b3bcd-204">**--warnaserror**[**+**&#124;**-**]:**&lt;int-list&gt;**</span></span>|<span data-ttu-id="b3bcd-205">То же, что и параметр компилятора **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-205">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b3bcd-206">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="b3bcd-206">For more information, see [Compiler Options](compiler-options.md).</span></span>|

## <a name="f-interactive-structured-printing"></a><span data-ttu-id="b3bcd-207">F# Interactive структурированной печати</span><span class="sxs-lookup"><span data-stu-id="b3bcd-207">F# Interactive structured printing</span></span>

<span data-ttu-id="b3bcd-208">F# Interactive ( `dotnet fsi` ) использует расширенную версию [структурированного форматирования обычного текста](plaintext-formatting.md) для передачи значений.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-208">F# Interactive (`dotnet fsi`) uses an extended version of [structured plain text formatting](plaintext-formatting.md) to report values.</span></span>

1. <span data-ttu-id="b3bcd-209">`%A`Поддерживаются все функции форматирования обычного текста, некоторые из которых также можно настроить.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-209">All features of `%A` plain text formatting are supported, and some are additionally customizable.</span></span>

2. <span data-ttu-id="b3bcd-210">Печать выводится цветом, если в консоли вывода поддерживаются цвета.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-210">Printing is colorized if colors are supported by the output console.</span></span>

3. <span data-ttu-id="b3bcd-211">Ограничение размещается на отображаемой длине строк, если только вы явно не Вычислите эту строку.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-211">A limit is placed on the length of strings shown, unless you explicitly evaluate that string.</span></span>

4. <span data-ttu-id="b3bcd-212">Набор определяемых пользователем параметров доступен через `fsi` объект.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-212">A set of user-definable settings are available via the `fsi` object.</span></span>

<span data-ttu-id="b3bcd-213">Доступные параметры для настройки печати в виде обычного текста для сообщаемых значений:</span><span class="sxs-lookup"><span data-stu-id="b3bcd-213">The available settings to customize plain text printing for reported values are:</span></span>

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

### <a name="customize-with-addprinter-and-addprinttransformer"></a><span data-ttu-id="b3bcd-214">Настройка с помощью `AddPrinter` и`AddPrintTransformer`</span><span class="sxs-lookup"><span data-stu-id="b3bcd-214">Customize with `AddPrinter` and `AddPrintTransformer`</span></span>

<span data-ttu-id="b3bcd-215">Печать в F# Interactive выходных данных может быть настроена с помощью `fsi.AddPrinter` и `fsi.AddPrintTransformer` .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-215">Printing in F# Interactive outputs can be customized by using `fsi.AddPrinter` and `fsi.AddPrintTransformer`.</span></span>
<span data-ttu-id="b3bcd-216">Первая функция предоставляет текст для замены печати объекта.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-216">The first function gives text to replace the printing of an object.</span></span> <span data-ttu-id="b3bcd-217">Вторая функция возвращает суррогатный объект для вывода вместо этого.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-217">The second function returns a surrogate object to display instead.</span></span> <span data-ttu-id="b3bcd-218">Например, рассмотрим следующий код F #:</span><span class="sxs-lookup"><span data-stu-id="b3bcd-218">For example, consider the following F# code:</span></span>

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

<span data-ttu-id="b3bcd-219">Если выполнить пример в F# Interactive, он выводится на основе набора параметров форматирования.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-219">If you execute the example in F# Interactive, it outputs based on the formatting option set.</span></span> <span data-ttu-id="b3bcd-220">В этом случае это влияет на форматирование даты и времени:</span><span class="sxs-lookup"><span data-stu-id="b3bcd-220">In this case, it affects the formatting of date and time:</span></span>

```console
type DateAndLabel =
  { Date: DateTime
    Label: string }
val newYearsDay1999 : DateAndLabel = { Date = 1999-01-01T00:00:00
                                       Label = "New Year" }
```

<span data-ttu-id="b3bcd-221">`fsi.AddPrintTransformer`можно использовать, чтобы предоставить суррогатный объект для печати:</span><span class="sxs-lookup"><span data-stu-id="b3bcd-221">`fsi.AddPrintTransformer` can be used to give a surrogate object for printing:</span></span>

```fsharp
type MyList(values: int list) =
    member _.Values = values

fsi.AddPrintTransformer(fun (x:MyList) -> box x.Values)

let x = MyList([1..10])
```

<span data-ttu-id="b3bcd-222">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="b3bcd-222">This outputs:</span></span>

```console
val x : MyList = [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
```

<span data-ttu-id="b3bcd-223">Если функция преобразователь `fsi.AddPrintTransformer` , передаваемая `null` , возвращает, то преобразователь печати игнорируется.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-223">If the transformer function passed to `fsi.AddPrintTransformer` returns `null`, then the print transformer is ignored.</span></span>
<span data-ttu-id="b3bcd-224">Это можно использовать для фильтрации любого входного значения, начиная с Type `obj` .</span><span class="sxs-lookup"><span data-stu-id="b3bcd-224">This can be used to filter any input value by starting with type `obj`.</span></span>  <span data-ttu-id="b3bcd-225">Пример:</span><span class="sxs-lookup"><span data-stu-id="b3bcd-225">For example:</span></span>

```fsharp
fsi.AddPrintTransformer(fun (x:obj) ->
    match x with
    | :? string as s when s = "beep" -> box ["quack"; "quack"; "quack"]
    | _ -> null)

let y = "beep"
```

<span data-ttu-id="b3bcd-226">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="b3bcd-226">This outputs:</span></span>

```console
val y : string = ["quack"; "quack"; "quack"]
```

## <a name="related-topics"></a><span data-ttu-id="b3bcd-227">См. также</span><span class="sxs-lookup"><span data-stu-id="b3bcd-227">Related topics</span></span>

|<span data-ttu-id="b3bcd-228">Заголовок</span><span class="sxs-lookup"><span data-stu-id="b3bcd-228">Title</span></span>|<span data-ttu-id="b3bcd-229">Описание</span><span class="sxs-lookup"><span data-stu-id="b3bcd-229">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="b3bcd-230">Параметры компилятора</span><span class="sxs-lookup"><span data-stu-id="b3bcd-230">Compiler Options</span></span>](compiler-options.md)|<span data-ttu-id="b3bcd-231">Описывает параметры командной строки, доступные для компилятора F #, **fsc.exe**.</span><span class="sxs-lookup"><span data-stu-id="b3bcd-231">Describes command line options available for the F# compiler, **fsc.exe**.</span></span>|
