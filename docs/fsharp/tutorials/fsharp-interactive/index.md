---
title: Справочник по F# Interactive (dotnet)
description: Узнайте, как F# Interactive (dotnet fsi) используется для интерактивного запуска кода F# в консоли или выполнения скриптов F#.
ms.date: 08/20/2020
f1_keywords:
- VS.ToolsOptionsPages.F#_Tools.F#_Interactive
ms.openlocfilehash: b1020d8ab8f2282c792fb5d00656b6d43c2c6610
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "93064123"
---
# <a name="interactive-programming-with-f"></a><span data-ttu-id="133e9-103">Интерактивное программирование с помощью F\#</span><span class="sxs-lookup"><span data-stu-id="133e9-103">Interactive programming with F\#</span></span>

<span data-ttu-id="133e9-104">F# Interactive (dotnet fsi) используется для интерактивного запуска кода F# в консоли или выполнения скриптов F#.</span><span class="sxs-lookup"><span data-stu-id="133e9-104">F# Interactive (dotnet fsi) is used to run F# code interactively at the console, or to execute F# scripts.</span></span> <span data-ttu-id="133e9-105">Другими словами, F# interactive выполняет команду REPL (чтение, оценка, цикл печати) для языка F#.</span><span class="sxs-lookup"><span data-stu-id="133e9-105">In other words, F# interactive executes a REPL (Read, Evaluate, Print Loop) for the F# language.</span></span>

<span data-ttu-id="133e9-106">Чтобы открыть F# Interactive из консоли, запустите `dotnet fsi`.</span><span class="sxs-lookup"><span data-stu-id="133e9-106">To run F# Interactive from the console, run `dotnet fsi`.</span></span> <span data-ttu-id="133e9-107">`dotnet fsi` предоставляется в любом пакете SDK для .NET.</span><span class="sxs-lookup"><span data-stu-id="133e9-107">You will find `dotnet fsi` in any .NET SDK.</span></span>

<span data-ttu-id="133e9-108">Дополнительные сведения о доступных параметрах командной строки см. в статье [Параметры F# Interactive](../../language-reference/fsharp-interactive-options.md).</span><span class="sxs-lookup"><span data-stu-id="133e9-108">For information about command line options available, see [F# Interactive Options](../../language-reference/fsharp-interactive-options.md).</span></span>

<span data-ttu-id="133e9-109">Чтобы запустить F# Interactive через Visual Studio, нажмите соответствующую кнопку на панели инструментов, обозначенную **F# Interactive** , или используйте сочетание клавиш **CTRL+ALT+F** .</span><span class="sxs-lookup"><span data-stu-id="133e9-109">To run F# Interactive through Visual Studio, you can click the appropriate toolbar button labeled **F# Interactive** , or use the keys **Ctrl+Alt+F** .</span></span> <span data-ttu-id="133e9-110">После этого откроется интерактивное окно — окно инструментов с запущенным сеансом F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="133e9-110">Doing this will open the interactive window, a tool window running an F# Interactive session.</span></span> <span data-ttu-id="133e9-111">Вы также можете выбрать код, который нужно запустить в интерактивном окне, и нажать клавиши **ALT+ВВОД** .</span><span class="sxs-lookup"><span data-stu-id="133e9-111">You can also select some code that you want to run in the interactive window and hit the key combination **Alt+Enter** .</span></span> <span data-ttu-id="133e9-112">F# Interactive откроется в окне инструментов **F# Interactive** .</span><span class="sxs-lookup"><span data-stu-id="133e9-112">F# Interactive starts in a tool window labeled **F# Interactive** .</span></span> <span data-ttu-id="133e9-113">При использовании этого сочетания клавиш, убедитесь, что фокус находится в редактора.</span><span class="sxs-lookup"><span data-stu-id="133e9-113">When you use this key combination, make sure that the editor window has the focus.</span></span>

<span data-ttu-id="133e9-114">Независимо от того, пользуетесь вы консолью или Visual Studio, появится командная строка и интерпретатор будет ждать ввода данных.</span><span class="sxs-lookup"><span data-stu-id="133e9-114">Whether you are using the console or Visual Studio, a command prompt appears and the interpreter awaits your input.</span></span> <span data-ttu-id="133e9-115">Можно ввести код так же, как это делается в файле кода.</span><span class="sxs-lookup"><span data-stu-id="133e9-115">You can enter code just as you would in a code file.</span></span> <span data-ttu-id="133e9-116">Для компиляции и выполнения кода введите две точки с запятой ( **;;** ), чтобы разграничить одну или несколько строк входных данных.</span><span class="sxs-lookup"><span data-stu-id="133e9-116">To compile and execute the code, enter two semicolons ( **;;** ) to terminate a line or several lines of input.</span></span>

<span data-ttu-id="133e9-117">F# Interactive попытается скомпилировать код и, в случае успеха, выполняет код и напечатает сигнатуру типов и значений, которые он скомпилировал.</span><span class="sxs-lookup"><span data-stu-id="133e9-117">F# Interactive attempts to compile the code and, if successful, it executes the code and prints the signature of the types and values that it compiled.</span></span> <span data-ttu-id="133e9-118">В случае ошибки интерпретатор напечатает сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="133e9-118">If errors occur, the interpreter prints the error messages.</span></span>

<span data-ttu-id="133e9-119">Код, введенный в том же сеансе имеет доступ ко всем конструкциям, введенным прежде, так что вы можете надстраивать программы.</span><span class="sxs-lookup"><span data-stu-id="133e9-119">Code entered in the same session has access to any constructs entered previously, so you can build up programs.</span></span> <span data-ttu-id="133e9-120">В случае необходимости благодаря значительному объему буфера в окне инструментов можно скопировать код в файл.</span><span class="sxs-lookup"><span data-stu-id="133e9-120">An extensive buffer in the tool window allows you to copy the code into a file if needed.</span></span>

<span data-ttu-id="133e9-121">При запуске в Visual Studio F# Interactive работает независимо от проекта, поэтому, например, использовать определенные в проекте конструкции в F# Interactive можно, только если скопировать код функции в интерактивное окно.</span><span class="sxs-lookup"><span data-stu-id="133e9-121">When run in Visual Studio, F# Interactive runs independently of your project, so, for example, you cannot use constructs defined in your project in F# Interactive unless you copy the code for the function into the interactive window.</span></span>

<span data-ttu-id="133e9-122">Если открыт проект, который ссылается на некоторые библиотеки, на эти же библиотеки можно сослаться в F# Interactive через **обозреватель решений** .</span><span class="sxs-lookup"><span data-stu-id="133e9-122">If you have a project open that references some libraries, you can reference these in F# Interactive through **Solution Explorer** .</span></span> <span data-ttu-id="133e9-123">Для ссылки на библиотеку в F# Interactive разверните узел **Ссылки** , откройте контекстное меню для библиотеки и выберите пункт **Отправить в F# Interactive** .</span><span class="sxs-lookup"><span data-stu-id="133e9-123">To reference a library in F# Interactive, expand the **References** node, open the shortcut menu for the library, and choose **Send to F# Interactive** .</span></span>

<span data-ttu-id="133e9-124">Управлять аргументами (параметрами) командной строки F# Interactive можно путем корректировки значений параметров.</span><span class="sxs-lookup"><span data-stu-id="133e9-124">You can control the F# Interactive command line arguments (options) by adjusting the settings.</span></span> <span data-ttu-id="133e9-125">В меню **Сервис** выберите пункт **Параметры...** , а затем разверните узел **Инструменты F#** .</span><span class="sxs-lookup"><span data-stu-id="133e9-125">On the **Tools** menu, select **Options...** , and then expand **F# Tools** .</span></span> <span data-ttu-id="133e9-126">Двумя параметрами, которые можно изменить, являются параметры F# Interactive и параметр **F# Interactive, 64-разрядная версия** , который используется только в том случае, если F# Interactive выполняется на 64-разрядном компьютере.</span><span class="sxs-lookup"><span data-stu-id="133e9-126">The two settings that you can change are the F# Interactive options and the **64-bit F# Interactive** setting, which is relevant only if you are running F# Interactive on a 64-bit machine.</span></span> <span data-ttu-id="133e9-127">Этот параметр указывает, следует ли выполнять выделенную 64-разрядную версию fsi.exe или fsianycpu.exe, которая использует архитектуру компьютера для определения типа выполняемого процесса — 32-разрядного или 64-разрядного.</span><span class="sxs-lookup"><span data-stu-id="133e9-127">This setting determines whether you want to run the dedicated 64-bit version of fsi.exe or fsianycpu.exe, which uses the machine architecture to determine whether to run as a 32-bit or 64-bit process.</span></span>

## <a name="scripting-with-f"></a><span data-ttu-id="133e9-128">Создание скриптов с использованием F\#</span><span class="sxs-lookup"><span data-stu-id="133e9-128">Scripting with F\#</span></span>

<span data-ttu-id="133e9-129">Для скриптов используется расширение файла **FSX** или **FSSCRIPT** .</span><span class="sxs-lookup"><span data-stu-id="133e9-129">Scripts use the file extension **.fsx** or **.fsscript** .</span></span> <span data-ttu-id="133e9-130">Вместо компиляции исходного кода и последующего выполнения скомпилированной сборки можно просто запустить **dotnet fsi** и указать имя файла скрипта исходного кода F#, а F# Interactive считает и выполнит код в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="133e9-130">Instead of compiling source code and then later running the compiled assembly, you can just run **dotnet fsi** and specify the filename of the script of F# source code, and F# interactive reads the code and executes it in real time.</span></span>

## <a name="differences-between-the-interactive-scripting-and-compiled-environments"></a><span data-ttu-id="133e9-131">Различия между интерактивной средой, средой скриптов и скомпилированной средой</span><span class="sxs-lookup"><span data-stu-id="133e9-131">Differences between the interactive, scripting, and compiled environments</span></span>

<span data-ttu-id="133e9-132">При компиляции кода в F# Interactive независимо от того, запущен он интерактивно или для выполнения скрипта, определяется символ **INTERACTIVE** .</span><span class="sxs-lookup"><span data-stu-id="133e9-132">When you are compiling code in F# Interactive, whether you are running interactively or running a script, the symbol **INTERACTIVE** is defined.</span></span> <span data-ttu-id="133e9-133">При компиляции кода в компиляторе определяется символ **COMPILED** .</span><span class="sxs-lookup"><span data-stu-id="133e9-133">When you are compiling code in the compiler, the symbol **COMPILED** is defined.</span></span> <span data-ttu-id="133e9-134">Таким образом, если код должен различаться в режиме компиляции и в интерактивном режиме, можно воспользоваться директивами препроцессора для условной компиляции, чтобы определить, что именно использовать.</span><span class="sxs-lookup"><span data-stu-id="133e9-134">Thus, if code needs to be different in compiled and interactive modes, you can use preprocessor directives for conditional compilation to determine which to use.</span></span>

<span data-ttu-id="133e9-135">Некоторые директивы, доступные при выполнении скриптов в F# Interactive, недоступны при выполнении компилятора.</span><span class="sxs-lookup"><span data-stu-id="133e9-135">Some directives are available when you are executing scripts in F# Interactive that are not available when you are executing the compiler.</span></span> <span data-ttu-id="133e9-136">В следующей таблице приведены директивы, доступные при использовании F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="133e9-136">The following table summarizes directives that are available when you are using F# Interactive.</span></span>

|<span data-ttu-id="133e9-137">Директива</span><span class="sxs-lookup"><span data-stu-id="133e9-137">Directive</span></span>|<span data-ttu-id="133e9-138">Описание</span><span class="sxs-lookup"><span data-stu-id="133e9-138">Description</span></span>|
|---------|-----------|
|<span data-ttu-id="133e9-139">**#help**</span><span class="sxs-lookup"><span data-stu-id="133e9-139">**#help**</span></span>|<span data-ttu-id="133e9-140">Отображает сведения о доступных директивах.</span><span class="sxs-lookup"><span data-stu-id="133e9-140">Displays information about available directives.</span></span>|
|<span data-ttu-id="133e9-141">**#I**</span><span class="sxs-lookup"><span data-stu-id="133e9-141">**#I**</span></span>|<span data-ttu-id="133e9-142">Задает путь поиска сборок в кавычках.</span><span class="sxs-lookup"><span data-stu-id="133e9-142">Specifies an assembly search path in quotation marks.</span></span>|
|<span data-ttu-id="133e9-143">**#load**</span><span class="sxs-lookup"><span data-stu-id="133e9-143">**#load**</span></span>|<span data-ttu-id="133e9-144">Читает исходный файл, компилирует и запускает его.</span><span class="sxs-lookup"><span data-stu-id="133e9-144">Reads a source file, compiles it, and runs it.</span></span>|
|<span data-ttu-id="133e9-145">**#quit**</span><span class="sxs-lookup"><span data-stu-id="133e9-145">**#quit**</span></span>|<span data-ttu-id="133e9-146">Завершает сеанс F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="133e9-146">Terminates an F# Interactive session.</span></span>|
|<span data-ttu-id="133e9-147">**#r**</span><span class="sxs-lookup"><span data-stu-id="133e9-147">**#r**</span></span>|<span data-ttu-id="133e9-148">Ссылается на сборку.</span><span class="sxs-lookup"><span data-stu-id="133e9-148">References an assembly.</span></span>|
|<span data-ttu-id="133e9-149">**#time ["on"&#124;"off"]**</span><span class="sxs-lookup"><span data-stu-id="133e9-149">**#time ["on"&#124;"off"]**</span></span>|<span data-ttu-id="133e9-150">Сама по себе директива **#time** включает или отключает отображение сведений о производительности.</span><span class="sxs-lookup"><span data-stu-id="133e9-150">By itself, **#time** toggles whether to display performance information.</span></span> <span data-ttu-id="133e9-151">Когда она включена, F# Interactive измеряет реальное время, время ЦП и сведения о коллекции мусора для каждого интерпретированного и выполненного код раздела.</span><span class="sxs-lookup"><span data-stu-id="133e9-151">When it is enabled, F# Interactive measures real time, CPU time, and garbage collection information for each section of code that is interpreted and executed.</span></span>|

<span data-ttu-id="133e9-152">При указании файлов или путей в F# Interactive ожидается строковый литерал.</span><span class="sxs-lookup"><span data-stu-id="133e9-152">When you specify files or paths in F# Interactive, a string literal is expected.</span></span> <span data-ttu-id="133e9-153">Следовательно, файлы и пути должны быть заключены в кавычки; можно использовать обычные escape-символы.</span><span class="sxs-lookup"><span data-stu-id="133e9-153">Therefore, files and paths must be in quotation marks, and the usual escape characters apply.</span></span> <span data-ttu-id="133e9-154">Кроме того, можно использовать символ @, чтобы чтобы строка, содержащая путь, интерпретировалась в F# Interactive как буквальная строка.</span><span class="sxs-lookup"><span data-stu-id="133e9-154">Also, you can use the @ character to cause F# Interactive to interpret a string that contains a path as a verbatim string.</span></span> <span data-ttu-id="133e9-155">В этом случае F# Interactive игнорирует все escape-символы.</span><span class="sxs-lookup"><span data-stu-id="133e9-155">This causes F# Interactive to ignore any escape characters.</span></span>

<span data-ttu-id="133e9-156">Одно из различий между скомпилированным и интерактивным режимами заключается в том, как можно получить доступ к аргументам командной строки.</span><span class="sxs-lookup"><span data-stu-id="133e9-156">One of the differences between compiled and interactive mode is the way you access command line arguments.</span></span> <span data-ttu-id="133e9-157">В скомпилированном режиме используйте **System.Environment.GetCommandLineArgs** .</span><span class="sxs-lookup"><span data-stu-id="133e9-157">In compiled mode, use **System.Environment.GetCommandLineArgs** .</span></span> <span data-ttu-id="133e9-158">В скриптах используйте **fsi.CommandLineArgs** .</span><span class="sxs-lookup"><span data-stu-id="133e9-158">In scripts, use **fsi.CommandLineArgs** .</span></span>

<span data-ttu-id="133e9-159">Следующий код показывает, как создать функцию, которая читает аргументы командной строки в скрипте, и дать ссылку на другую сборку из скрипта.</span><span class="sxs-lookup"><span data-stu-id="133e9-159">The following code illustrates how to create a function that reads the command line arguments in a script and also demonstrates how to reference another assembly from a script.</span></span> <span data-ttu-id="133e9-160">Первый файл кода, **MyAssembly.fs** , является кодом для сборки, на которую дается ссылка.</span><span class="sxs-lookup"><span data-stu-id="133e9-160">The first code file, **MyAssembly.fs** , is the code for the assembly being referenced.</span></span> <span data-ttu-id="133e9-161">Скомпилируйте этот файл с помощью командной строки: **fsc -a MyAssembly.fs** , а затем запустите второй файл в качестве скрипта с помощью командной строки: **fsi --exec file1.fsx** test</span><span class="sxs-lookup"><span data-stu-id="133e9-161">Compile this file with the command line: **fsc -a MyAssembly.fs** and then execute the second file as a script with the command line: **fsi --exec file1.fsx** test</span></span>

```fsharp
// MyAssembly.fs
module MyAssembly
let myFunction x y = x + 2 * y
```

```fsharp
// file1.fsx
#r "MyAssembly.dll"

printfn "Command line arguments: "

for arg in fsi.CommandLineArgs do
    printfn "%s" arg

printfn "%A" (MyAssembly.myFunction 10 40)
```

<span data-ttu-id="133e9-162">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="133e9-162">The output is as follows:</span></span>

```console
Command line arguments:
file1.fsx
test
90
```

## <a name="package-management-in-f-interactive"></a><span data-ttu-id="133e9-163">Управление пакетами в F# Interactive</span><span class="sxs-lookup"><span data-stu-id="133e9-163">Package Management in F# Interactive</span></span>

[!NOTE] <span data-ttu-id="133e9-164">Управление пакетами реализовано в виде предварительной версии функции в версиях `dotnet fsi`, поставляемых в `3.1.300` и более поздних версиях пакета SDK для .NET, а также во всех версиях `5.*` пакета SDK для .NET.</span><span class="sxs-lookup"><span data-stu-id="133e9-164">Package management is available as a preview feature in versions of `dotnet fsi` shipped in the `3.1.300` and greater versions of the .NET SDK, as well as all `5.*` versions of the .NET SDK.</span></span> <span data-ttu-id="133e9-165">Чтобы включить эту возможность в этом предварительном выпуске, выполните `dotnet fsi` с аргументом `--langversion:preview`.</span><span class="sxs-lookup"><span data-stu-id="133e9-165">To enable it in this preview release, run `dotnet fsi` with the `--langversion:preview` argument.</span></span>

<span data-ttu-id="133e9-166">Синтаксис `#r` для создания ссылки на библиотеку DLL в F# Interactive можно также использовать для обращения к пакету NuGet следующим образом:</span><span class="sxs-lookup"><span data-stu-id="133e9-166">The `#r` syntax for referencing a DLL in F# Interactive can also be used to reference a nuget package via the following syntax:</span></span>

```fsharp
#r "nuget: <package name>"
```

<span data-ttu-id="133e9-167">Например, чтобы указать пакет `FSharp.Data`, используйте следующую ссылку `#r`:</span><span class="sxs-lookup"><span data-stu-id="133e9-167">For example, to reference the `FSharp.Data` package, use the following `#r` reference:</span></span>

```fsharp
#r "nuget: FSharp.Data"
```

<span data-ttu-id="133e9-168">После выполнения этой строки последняя версия пакета `FSharp.Data` будет загружена в кэш NuGet и указана в текущем сеансе F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="133e9-168">After executing this line, the latest version of the `FSharp.Data` package will be downloaded to your nuget cache and referenced in the current F# Interactive session.</span></span>

<span data-ttu-id="133e9-169">Вы можете указывать не только имя пакета, но и его определенные версии, используя следующий краткий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="133e9-169">In addition to the package name, specific versions of a package can be referenced via a short syntax:</span></span>

```fsharp
#r "nuget: FSharp.Data, 3.3.2"
```

<span data-ttu-id="133e9-170">Или более явным образом:</span><span class="sxs-lookup"><span data-stu-id="133e9-170">or in a more explicit fashion:</span></span>

```fsharp
#r "nuget: FSharp.Data, Version=3.3.2"
```

## <a name="related-articles"></a><span data-ttu-id="133e9-171">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="133e9-171">Related articles</span></span>

|<span data-ttu-id="133e9-172">Заголовок</span><span class="sxs-lookup"><span data-stu-id="133e9-172">Title</span></span>|<span data-ttu-id="133e9-173">Описание:</span><span class="sxs-lookup"><span data-stu-id="133e9-173">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="133e9-174">Параметры F# Interactive</span><span class="sxs-lookup"><span data-stu-id="133e9-174">F# Interactive Options</span></span>](../../language-reference/fsharp-interactive-options.md)|<span data-ttu-id="133e9-175">Описание синтаксиса команд и параметров для F# Interactive, fsi.exe.</span><span class="sxs-lookup"><span data-stu-id="133e9-175">Describes command-line syntax and options for the F# Interactive, fsi.exe.</span></span>|
