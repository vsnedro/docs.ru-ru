---
title: Справочник по F# Interactive (dotnet)
description: Узнайте, как F# Interactive (dotnet fsi) используется для интерактивного запуска кода F# в консоли или выполнения скриптов F#.
ms.date: 10/31/2020
f1_keywords:
- VS.ToolsOptionsPages.F#_Tools.F#_Interactive
ms.openlocfilehash: b535cb03d76909043ca192ed5a9d2078f9343795
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099439"
---
# <a name="interactive-programming-with-f"></a><span data-ttu-id="04ae0-103">Интерактивное программирование с помощью F\#</span><span class="sxs-lookup"><span data-stu-id="04ae0-103">Interactive programming with F\#</span></span>

<span data-ttu-id="04ae0-104">F# Interactive (dotnet fsi) используется для интерактивного запуска кода F# в консоли или выполнения скриптов F#.</span><span class="sxs-lookup"><span data-stu-id="04ae0-104">F# Interactive (dotnet fsi) is used to run F# code interactively at the console, or to execute F# scripts.</span></span> <span data-ttu-id="04ae0-105">Другими словами, F# interactive выполняет команду REPL (чтение, оценка, цикл печати) для языка F#.</span><span class="sxs-lookup"><span data-stu-id="04ae0-105">In other words, F# interactive executes a REPL (Read, Evaluate, Print Loop) for the F# language.</span></span>

<span data-ttu-id="04ae0-106">Чтобы открыть F# Interactive из консоли, запустите `dotnet fsi`.</span><span class="sxs-lookup"><span data-stu-id="04ae0-106">To run F# Interactive from the console, run `dotnet fsi`.</span></span> <span data-ttu-id="04ae0-107">`dotnet fsi` предоставляется в любом пакете SDK для .NET.</span><span class="sxs-lookup"><span data-stu-id="04ae0-107">You will find `dotnet fsi` in any .NET SDK.</span></span>

<span data-ttu-id="04ae0-108">Дополнительные сведения о доступных параметрах командной строки см. в статье [Параметры F# Interactive](../../language-reference/fsharp-interactive-options.md).</span><span class="sxs-lookup"><span data-stu-id="04ae0-108">For information about available command-line options, see [F# Interactive Options](../../language-reference/fsharp-interactive-options.md).</span></span>

## <a name="executing-code-directly-in-f-interactive"></a><span data-ttu-id="04ae0-109">Прямое выполнение кода в F# Interactive</span><span class="sxs-lookup"><span data-stu-id="04ae0-109">Executing code directly in F# Interactive</span></span>

<span data-ttu-id="04ae0-110">Так как F# Interactive — это REPL (read-eval-print loop), вы можете выполнять код в этом средстве в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="04ae0-110">Because F# Interactive is a REPL (read-eval-print loop), you can execute code interactively in it.</span></span> <span data-ttu-id="04ae0-111">Ниже приведен пример интерактивного сеанса после выполнения `dotnet fsi` из командной строки:</span><span class="sxs-lookup"><span data-stu-id="04ae0-111">Here is an example of an interactive session after executing `dotnet fsi` from the command line:</span></span>

```console
Microsoft (R) F# Interactive version 11.0.0.0 for F# 5.0
Copyright (c) Microsoft Corporation. All Rights Reserved.

For help type #help;;

> let square x = x *  x;;
val square : x:int -> int

> square 12;;
val it : int = 144

> printfn "Hello, FSI!"
- ;;
Hello, FSI!
val it : unit = ()
```

<span data-ttu-id="04ae0-112">Вы заметите две основных вещи:</span><span class="sxs-lookup"><span data-stu-id="04ae0-112">You'll notice two main things:</span></span>

1. <span data-ttu-id="04ae0-113">Весь оцениваемый код должен завершаться двумя точками с запятой (`;;`).</span><span class="sxs-lookup"><span data-stu-id="04ae0-113">All code must be terminated with a double semicolon (`;;`) to be evaluated</span></span>
2. <span data-ttu-id="04ae0-114">Код вычисляется и сохраняется в значении `it`.</span><span class="sxs-lookup"><span data-stu-id="04ae0-114">Code is evaluated and stored in an `it` value.</span></span> <span data-ttu-id="04ae0-115">Вы можете ссылаться на `it` в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="04ae0-115">You can reference `it` interactively.</span></span>

<span data-ttu-id="04ae0-116">F# Interactive также поддерживает многострочный ввод.</span><span class="sxs-lookup"><span data-stu-id="04ae0-116">F# Interactive also supports multi-line input.</span></span> <span data-ttu-id="04ae0-117">Необходимо просто указать в конце две точки с запятой (`;;`).</span><span class="sxs-lookup"><span data-stu-id="04ae0-117">You just need to terminate your submission with a double semicolon (`;;`).</span></span> <span data-ttu-id="04ae0-118">Рассмотрим следующий фрагмент кода, вставленный и оцениваемый в F# Interactive:</span><span class="sxs-lookup"><span data-stu-id="04ae0-118">Consider the following snippet that has been pasted into and evaluated by F# Interactive:</span></span>

```console
> let getOddSquares xs =
-     xs
-     |> List.filter (fun x -> x % 2 <> 0)
-     |> List.map (fun x -> x * x)
-
- printfn "%A" (getOddSquares [1..10]);;
[1; 9; 25; 49; 81]
val getOddSquares : xs:int list -> int list
val it : unit = ()

>
```

<span data-ttu-id="04ae0-119">Форматирование кода сохраняется, и ввод завершает две точки с запятой (`;;`).</span><span class="sxs-lookup"><span data-stu-id="04ae0-119">The code's formatting is preserved, and there is a double semicolon (`;;`) terminating the input.</span></span> <span data-ttu-id="04ae0-120">Затем F# Interactive оценивает код и выводит результаты.</span><span class="sxs-lookup"><span data-stu-id="04ae0-120">F# Interactive then evaluated the code and printed the results!</span></span>

## <a name="scripting-with-f"></a><span data-ttu-id="04ae0-121">Создание скриптов с использованием F\#</span><span class="sxs-lookup"><span data-stu-id="04ae0-121">Scripting with F\#</span></span>

<span data-ttu-id="04ae0-122">Интерактивная оценка кода в F# Interactive может быть отличным средством обучения. Но вы быстро обнаружите, что это не так эффективно, как написание кода в стандартном редакторе.</span><span class="sxs-lookup"><span data-stu-id="04ae0-122">Evaluating code interactively in F# Interactive can be a great learning tool, but you'll quickly find that it's not as productive as writing code in a normal editor.</span></span> <span data-ttu-id="04ae0-123">Чтобы использовать возможности обычного редактирования кода, можно писать скрипты F#.</span><span class="sxs-lookup"><span data-stu-id="04ae0-123">To support normal code editing, you can write F# scripts.</span></span>

<span data-ttu-id="04ae0-124">Для скриптов используется расширение файла **.fsx**.</span><span class="sxs-lookup"><span data-stu-id="04ae0-124">Scripts use the file extension **.fsx**.</span></span> <span data-ttu-id="04ae0-125">Вместо компиляции исходного кода и последующего выполнения скомпилированной сборки можно просто запустить **dotnet fsi** и указать имя файла скрипта исходного кода F#, а F# Interactive считает и выполнит код в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="04ae0-125">Instead of compiling source code and then later running the compiled assembly, you can just run **dotnet fsi** and specify the filename of the script of F# source code, and F# interactive reads the code and executes it in real time.</span></span> <span data-ttu-id="04ae0-126">Например, рассмотрим следующий скрипт с именем `Script.fsx`:</span><span class="sxs-lookup"><span data-stu-id="04ae0-126">For example, consider the following script called `Script.fsx`:</span></span>

```fsharp
let getOddSquares xs =
    xs
    |> List.filter (fun x -> x % 2 <> 0)
    |> List.map (fun x -> x * x)

printfn "%A" (getOddSquares [1..10])
```

<span data-ttu-id="04ae0-127">При создании этого файла на компьютере можно запустить его с использованием `dotnet fsi` и просмотреть выходные данные непосредственно в окне терминала:</span><span class="sxs-lookup"><span data-stu-id="04ae0-127">When this file is created in your machine, you can run it with `dotnet fsi` and see the output directly in your terminal window:</span></span>

```console
dotnet fsi Script.fsx
[1; 9; 25; 49; 81]
```

<span data-ttu-id="04ae0-128">Возможность написания скриптов F# изначально поддерживается в [Visual Studio](../../get-started/get-started-visual-studio.md), [Visual Studio Code](../../get-started/get-started-vscode.md) и [Visual Studio для Mac](../../get-started/get-started-with-visual-studio-for-mac.md).</span><span class="sxs-lookup"><span data-stu-id="04ae0-128">F# scripting is natively supported in [Visual Studio](../../get-started/get-started-visual-studio.md), [Visual Studio Code](../../get-started/get-started-vscode.md), and [Visual Studio for Mac](../../get-started/get-started-with-visual-studio-for-mac.md).</span></span>

## <a name="referencing-packages-in-f-interactive"></a><span data-ttu-id="04ae0-129">Создание ссылок на пакеты в F# Interactive</span><span class="sxs-lookup"><span data-stu-id="04ae0-129">Referencing packages in F# Interactive</span></span>

<span data-ttu-id="04ae0-130">F# Interactive позволяет создавать ссылки на пакеты NuGet с помощью синтаксиса `#r "nuget:"` и дополнительной версии:</span><span class="sxs-lookup"><span data-stu-id="04ae0-130">F# Interactive supports referencing NuGet packages with the `#r "nuget:"` syntax and an optional version:</span></span>

```fsharp
#r "nuget: Newtonsoft.Json"
open Newtonsoft.Json

let data = {| Name = "Don Syme"; Occupation = "F# Creator" |}
JsonConvert.SerializeObject(data)
```

<span data-ttu-id="04ae0-131">Если версия не указана, используется последний доступный пакет, не являющийся предварительной версией.</span><span class="sxs-lookup"><span data-stu-id="04ae0-131">If a version is not specified, the highest available non-preview package is taken.</span></span> <span data-ttu-id="04ae0-132">Чтобы создать ссылку на определенную версию, необходимо указать ее с помощью запятой.</span><span class="sxs-lookup"><span data-stu-id="04ae0-132">To reference a specific version, introduce the version via a comma.</span></span> <span data-ttu-id="04ae0-133">Это может быть удобно при обращении к предварительной версии пакета.</span><span class="sxs-lookup"><span data-stu-id="04ae0-133">This can be handy when referencing a preview version of a package.</span></span> <span data-ttu-id="04ae0-134">Например, рассмотрим этот скрипт, используя предварительную версию [DiffSharp](https://diffsharp.github.io/):</span><span class="sxs-lookup"><span data-stu-id="04ae0-134">For example, consider this script using a preview version of [DiffSharp](https://diffsharp.github.io/):</span></span>

```fsharp
#r "nuget: DiffSharp-lite, 1.0.0-preview-328097867"
open DiffSharp

// A 1D tensor
let t1 = dsharp.tensor [ 0.0 .. 0.2 .. 1.0 ]

// A 2x2 tensor
let t2 = dsharp.tensor [ [ 0; 1 ]; [ 2; 2 ] ]

// Define a scalar-to-scalar function
let f (x: Tensor) = sin (sqrt x)

printfn "%A" (f (dsharp.tensor 1.2))
```

<span data-ttu-id="04ae0-135">В скрипте можно указать любое количество ссылок на пакет.</span><span class="sxs-lookup"><span data-stu-id="04ae0-135">You can specify as many package references as you like in a script.</span></span>

> [!NOTE]
> <span data-ttu-id="04ae0-136">В настоящее время существует ограничение для скриптов, использующих ссылки на платформы (например, `Microsoft.NET.Sdk.Web` или `Microsoft.NET.Sdk.WindowsDesktop`).</span><span class="sxs-lookup"><span data-stu-id="04ae0-136">There's currently a limitation for scripts that use framework references (e.g.`Microsoft.NET.Sdk.Web` or  `Microsoft.NET.Sdk.WindowsDesktop`).</span></span> <span data-ttu-id="04ae0-137">Такие пакеты, как Saturn, Giraffe, WinForms, недоступны.</span><span class="sxs-lookup"><span data-stu-id="04ae0-137">Packages like Saturn, Giraffe, WinForms are not available.</span></span> <span data-ttu-id="04ae0-138">Для решения создана соответствующая проблема [9417](https://github.com/dotnet/fsharp/issues/9417).</span><span class="sxs-lookup"><span data-stu-id="04ae0-138">This is being tracked in issue [#9417](https://github.com/dotnet/fsharp/issues/9417).</span></span>

## <a name="referencing-assemblies-on-disk-with-f-interactive"></a><span data-ttu-id="04ae0-139">Создание ссылок на сборки на диске в F# Interactive</span><span class="sxs-lookup"><span data-stu-id="04ae0-139">Referencing assemblies on disk with F# interactive</span></span>

<span data-ttu-id="04ae0-140">Сходным образом, если у вас есть сборка на диске и вам нужно создать ссылку на нее в скрипте, вы можете использовать синтаксис `#r` для указания сборки.</span><span class="sxs-lookup"><span data-stu-id="04ae0-140">Alternatively, if you have an assembly on disk and wish to reference that in a script, you can use the `#r` syntax to specify an assembly.</span></span> <span data-ttu-id="04ae0-141">Рассмотрим следующий код в проекте, скомпилированном в `MyAssembly.dll`:</span><span class="sxs-lookup"><span data-stu-id="04ae0-141">Consider the following code in a project compiled into `MyAssembly.dll`:</span></span>

```fsharp
// MyAssembly.fs
module MyAssembly
let myFunction x y = x + 2 * y
```

<span data-ttu-id="04ae0-142">После компиляции можно создать ссылку в файле с именем `Script.fsx` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="04ae0-142">One compiled, you can reference it in a file called `Script.fsx` like so:</span></span>

```fsharp
#r "path/to/MyAssembly.dll"

printfn "%A" (MyAssembly.myFunction 10 40)
```

<span data-ttu-id="04ae0-143">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="04ae0-143">The output is as follows:</span></span>

```console
dotnet fsi Script.fsx
90
```

<span data-ttu-id="04ae0-144">В скрипте можно указать любое количество ссылок на сборку.</span><span class="sxs-lookup"><span data-stu-id="04ae0-144">You can specify as many assembly references as you like in a script.</span></span>

## <a name="loading-other-scripts"></a><span data-ttu-id="04ae0-145">Загрузка других скриптов</span><span class="sxs-lookup"><span data-stu-id="04ae0-145">Loading other scripts</span></span>

<span data-ttu-id="04ae0-146">При создании скриптов часто бывает полезно использовать разные сценарии для разных задач.</span><span class="sxs-lookup"><span data-stu-id="04ae0-146">When scripting, it can often be helpful to use different scripts for different tasks.</span></span> <span data-ttu-id="04ae0-147">Иногда может потребоваться повторно использовать код из одного скрипта в другом.</span><span class="sxs-lookup"><span data-stu-id="04ae0-147">Sometimes you may want to reuse code from on script in another.</span></span> <span data-ttu-id="04ae0-148">Вместо копирования и вставки содержимого в файл можно просто загрузить и оценить его с помощью `#load`.</span><span class="sxs-lookup"><span data-stu-id="04ae0-148">Rather than copy-pasting its contents into your file, you can simple load and evaluate it with `#load`.</span></span>

<span data-ttu-id="04ae0-149">Рассмотрим следующий пример с `Script1.fsx`:</span><span class="sxs-lookup"><span data-stu-id="04ae0-149">Consider the following `Script1.fsx`:</span></span>

```fsharp
let square x = x * x
```

<span data-ttu-id="04ae0-150">Используемый файл `Script2.fsx`:</span><span class="sxs-lookup"><span data-stu-id="04ae0-150">And the consuming file, `Script2.fsx`:</span></span>

```fsharp
#load "Script1.fsx"
open Script1

printfn "%d" (square 12)
```

<span data-ttu-id="04ae0-151">Обратите внимание, что требуется объявление `open Script1`.</span><span class="sxs-lookup"><span data-stu-id="04ae0-151">Note that the `open Script1` declaration is required.</span></span> <span data-ttu-id="04ae0-152">Это обусловлено тем, что конструкции в скрипте F# компилируются в модуль верхнего уровня, являющийся именем файла скрипта, в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="04ae0-152">This is because constructs in an F# script are compiled into a top-level module that is the name of the script file it is in.</span></span>

<span data-ttu-id="04ae0-153">Вы можете оценить `Script2.fsx` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="04ae0-153">You can evaluate `Script2.fsx` like so:</span></span>

```console
dotnet fsi Script2.fsx
144
```

<span data-ttu-id="04ae0-154">В скрипте можно указать любое количество директив `#load`.</span><span class="sxs-lookup"><span data-stu-id="04ae0-154">You can specify as many `#load` directives as you like in a script.</span></span>

## <a name="using-the-fsi-object-in-f-code"></a><span data-ttu-id="04ae0-155">Использование объекта `fsi` в коде F#</span><span class="sxs-lookup"><span data-stu-id="04ae0-155">Using the `fsi` object in F# code</span></span>

<span data-ttu-id="04ae0-156">Скрипты F# имеют доступ к пользовательскому объекту `fsi`, который представляет сеанс F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="04ae0-156">F# scripts have access to a custom `fsi` object that represents the F# Interactive session.</span></span> <span data-ttu-id="04ae0-157">Это, среди прочего, позволяет настраивать форматирование вывода.</span><span class="sxs-lookup"><span data-stu-id="04ae0-157">It allows you to customize things like output formatting.</span></span> <span data-ttu-id="04ae0-158">Кроме того, вы можете получить доступ к аргументам командной строки.</span><span class="sxs-lookup"><span data-stu-id="04ae0-158">It is also how you can access command-line arguments.</span></span>

<span data-ttu-id="04ae0-159">В следующем примере показано, как получить и использовать аргументы командной строки:</span><span class="sxs-lookup"><span data-stu-id="04ae0-159">The following example shows how to get and use command-line arguments:</span></span>

```fsharp
let args = fsi.CommandLineArgs

for arg in args do
    printfn "%s" arg
```

<span data-ttu-id="04ae0-160">При оценке выводятся все аргументы.</span><span class="sxs-lookup"><span data-stu-id="04ae0-160">When evaluated, it prints all arguments.</span></span> <span data-ttu-id="04ae0-161">Первым аргументом всегда является имя вычисляемого скрипта:</span><span class="sxs-lookup"><span data-stu-id="04ae0-161">The first argument is always the name of the script that is evaluated:</span></span>

```dotnet
dotnet fsi Script1.fsx hello world from fsi
Script1.fsx
hello
world
from
fsi
```

<span data-ttu-id="04ae0-162">Кроме того, для доступа к одним и тем же аргументам вы можете использовать `System.Environment.GetCommandLineArgs()`.</span><span class="sxs-lookup"><span data-stu-id="04ae0-162">You can also use `System.Environment.GetCommandLineArgs()` to access the same arguments.</span></span>

## <a name="f-interactive-directive-reference"></a><span data-ttu-id="04ae0-163">Справочник по директивам F# Interactive</span><span class="sxs-lookup"><span data-stu-id="04ae0-163">F# Interactive directive reference</span></span>

<span data-ttu-id="04ae0-164">Ранее упомянутые директивы `#r` и `#load` доступны только в F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="04ae0-164">The `#r` and `#load` directives seen previously are only available in F# Interactive.</span></span> <span data-ttu-id="04ae0-165">Есть несколько директив, доступных только в F# Interactive:</span><span class="sxs-lookup"><span data-stu-id="04ae0-165">There are several directives only available in F# Interactive:</span></span>

|<span data-ttu-id="04ae0-166">Директива</span><span class="sxs-lookup"><span data-stu-id="04ae0-166">Directive</span></span>|<span data-ttu-id="04ae0-167">Описание</span><span class="sxs-lookup"><span data-stu-id="04ae0-167">Description</span></span>|
|---------|-----------|
|`#r "nuget:..."`|<span data-ttu-id="04ae0-168">Ссылается на пакет из NuGet</span><span class="sxs-lookup"><span data-stu-id="04ae0-168">References a package from NuGet</span></span>|
|`#r "assembly-name.dll"`|<span data-ttu-id="04ae0-169">Ссылается на сборку на диске</span><span class="sxs-lookup"><span data-stu-id="04ae0-169">References an assembly on disk</span></span>|
|`#load "file-name.fsx"`|<span data-ttu-id="04ae0-170">Читает исходный файл, компилирует и запускает его.</span><span class="sxs-lookup"><span data-stu-id="04ae0-170">Reads a source file, compiles it, and runs it.</span></span>|
|`#help`|<span data-ttu-id="04ae0-171">Отображает сведения о доступных директивах.</span><span class="sxs-lookup"><span data-stu-id="04ae0-171">Displays information about available directives.</span></span>|
|`#I`|<span data-ttu-id="04ae0-172">Задает путь поиска сборок в кавычках.</span><span class="sxs-lookup"><span data-stu-id="04ae0-172">Specifies an assembly search path in quotation marks.</span></span>|
|`#quit`|<span data-ttu-id="04ae0-173">Завершает сеанс F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="04ae0-173">Terminates an F# Interactive session.</span></span>|
|<span data-ttu-id="04ae0-174">`#time "on"` или `#time "off"`</span><span class="sxs-lookup"><span data-stu-id="04ae0-174">`#time "on"` or `#time "off"`</span></span>|<span data-ttu-id="04ae0-175">Сама по себе директива `#time` позволяет включить или отключить отображение сведений о производительности.</span><span class="sxs-lookup"><span data-stu-id="04ae0-175">By itself, `#time` toggles whether to display performance information.</span></span> <span data-ttu-id="04ae0-176">Когда она включена (`"on"`), F# Interactive измеряет реальное время, время ЦП и сведения о сборке мусора для каждого интерпретированного и выполненного раздела кода.</span><span class="sxs-lookup"><span data-stu-id="04ae0-176">When it is `"on"`, F# Interactive measures real time, CPU time, and garbage collection information for each section of code that is interpreted and executed.</span></span>|

<span data-ttu-id="04ae0-177">При указании файлов или путей в F# Interactive ожидается строковый литерал.</span><span class="sxs-lookup"><span data-stu-id="04ae0-177">When you specify files or paths in F# Interactive, a string literal is expected.</span></span> <span data-ttu-id="04ae0-178">Следовательно, файлы и пути должны быть заключены в кавычки; можно использовать обычные escape-символы.</span><span class="sxs-lookup"><span data-stu-id="04ae0-178">Therefore, files and paths must be in quotation marks, and the usual escape characters apply.</span></span> <span data-ttu-id="04ae0-179">Кроме того, можно использовать символ `@`, чтобы строка, содержащая путь, интерпретировалась в F# Interactive как буквальная строка.</span><span class="sxs-lookup"><span data-stu-id="04ae0-179">You can use the `@` character to cause F# Interactive to interpret a string that contains a path as a verbatim string.</span></span> <span data-ttu-id="04ae0-180">В этом случае F# Interactive игнорирует все escape-символы.</span><span class="sxs-lookup"><span data-stu-id="04ae0-180">This causes F# Interactive to ignore any escape characters.</span></span>

## <a name="interactive-and-compiled-preprocessor-directives"></a><span data-ttu-id="04ae0-181">Интерактивные и скомпилированные директивы препроцессора</span><span class="sxs-lookup"><span data-stu-id="04ae0-181">Interactive and compiled preprocessor directives</span></span>

<span data-ttu-id="04ae0-182">При компиляции кода в F# Interactive независимо от того, запущен ли он интерактивно или с использованием скрипта, определяется символ **INTERACTIVE**.</span><span class="sxs-lookup"><span data-stu-id="04ae0-182">When you compile code in F# Interactive, whether you are running interactively or running a script, the symbol **INTERACTIVE** is defined.</span></span> <span data-ttu-id="04ae0-183">При компиляции кода в компиляторе определяется символ **COMPILED**.</span><span class="sxs-lookup"><span data-stu-id="04ae0-183">When you compile code in the compiler, the symbol **COMPILED** is defined.</span></span> <span data-ttu-id="04ae0-184">Таким образом, если код в режиме компиляции и интерактивном режиме должен быть разным, можно воспользоваться директивами препроцессора для условной компиляции. Это позволит определить, что именно использовать.</span><span class="sxs-lookup"><span data-stu-id="04ae0-184">Thus, if code needs to be different in compiled and interactive modes, you can use these preprocessor directives for conditional compilation to determine which to use.</span></span> <span data-ttu-id="04ae0-185">Пример:</span><span class="sxs-lookup"><span data-stu-id="04ae0-185">For example:</span></span>

```fsharp
#if INTERACTIVE
// Some code that executes only in FSI
// ...
#endif
```

## <a name="using-f-interactive-in-visual-studio"></a><span data-ttu-id="04ae0-186">Использование F# Interactive в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="04ae0-186">Using F# Interactive in Visual Studio</span></span>

<span data-ttu-id="04ae0-187">Чтобы запустить F# Interactive через Visual Studio, нажмите соответствующую кнопку на панели инструментов, обозначенную **F# Interactive**, или используйте сочетание клавиш **CTRL+ALT+F**.</span><span class="sxs-lookup"><span data-stu-id="04ae0-187">To run F# Interactive through Visual Studio, you can click the appropriate toolbar button labeled **F# Interactive**, or use the keys **Ctrl+Alt+F**.</span></span> <span data-ttu-id="04ae0-188">После этого откроется интерактивное окно — окно инструментов с запущенным сеансом F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="04ae0-188">Doing this will open the interactive window, a tool window running an F# Interactive session.</span></span> <span data-ttu-id="04ae0-189">Вы также можете выбрать код, который нужно запустить в интерактивном окне, и нажать клавиши **ALT+ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="04ae0-189">You can also select some code that you want to run in the interactive window and hit the key combination **Alt+Enter**.</span></span> <span data-ttu-id="04ae0-190">F# Interactive откроется в окне инструментов **F# Interactive**.</span><span class="sxs-lookup"><span data-stu-id="04ae0-190">F# Interactive starts in a tool window labeled **F# Interactive**.</span></span> <span data-ttu-id="04ae0-191">При использовании этого сочетания клавиш, убедитесь, что фокус находится в редактора.</span><span class="sxs-lookup"><span data-stu-id="04ae0-191">When you use this key combination, make sure that the editor window has the focus.</span></span>

<span data-ttu-id="04ae0-192">Независимо от того, пользуетесь вы консолью или Visual Studio, появится командная строка и интерпретатор будет ждать ввода данных.</span><span class="sxs-lookup"><span data-stu-id="04ae0-192">Whether you are using the console or Visual Studio, a command prompt appears and the interpreter awaits your input.</span></span> <span data-ttu-id="04ae0-193">Можно ввести код так же, как это делается в файле кода.</span><span class="sxs-lookup"><span data-stu-id="04ae0-193">You can enter code just as you would in a code file.</span></span> <span data-ttu-id="04ae0-194">Для компиляции и выполнения кода введите две точки с запятой (**;;**), чтобы разграничить одну или несколько строк входных данных.</span><span class="sxs-lookup"><span data-stu-id="04ae0-194">To compile and execute the code, enter two semicolons (**;;**) to terminate a line or several lines of input.</span></span>

<span data-ttu-id="04ae0-195">F# Interactive попытается скомпилировать код и, в случае успеха, выполняет код и напечатает сигнатуру типов и значений, которые он скомпилировал.</span><span class="sxs-lookup"><span data-stu-id="04ae0-195">F# Interactive attempts to compile the code and, if successful, it executes the code and prints the signature of the types and values that it compiled.</span></span> <span data-ttu-id="04ae0-196">В случае ошибки интерпретатор напечатает сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="04ae0-196">If errors occur, the interpreter prints the error messages.</span></span>

<span data-ttu-id="04ae0-197">Код, введенный в том же сеансе имеет доступ ко всем конструкциям, введенным прежде, так что вы можете надстраивать программы.</span><span class="sxs-lookup"><span data-stu-id="04ae0-197">Code entered in the same session has access to any constructs entered previously, so you can build up programs.</span></span> <span data-ttu-id="04ae0-198">В случае необходимости благодаря значительному объему буфера в окне инструментов можно скопировать код в файл.</span><span class="sxs-lookup"><span data-stu-id="04ae0-198">An extensive buffer in the tool window allows you to copy the code into a file if needed.</span></span>

<span data-ttu-id="04ae0-199">При запуске в Visual Studio F# Interactive работает независимо от проекта, поэтому, например, использовать определенные в проекте конструкции в F# Interactive можно, только если скопировать код функции в интерактивное окно.</span><span class="sxs-lookup"><span data-stu-id="04ae0-199">When run in Visual Studio, F# Interactive runs independently of your project, so, for example, you cannot use constructs defined in your project in F# Interactive unless you copy the code for the function into the interactive window.</span></span>

<span data-ttu-id="04ae0-200">Управлять аргументами (параметрами) командной строки F# Interactive можно путем корректировки значений параметров.</span><span class="sxs-lookup"><span data-stu-id="04ae0-200">You can control the F# Interactive command-line arguments (options) by adjusting the settings.</span></span> <span data-ttu-id="04ae0-201">В меню **Сервис** выберите пункт **Параметры...**, а затем разверните узел **Инструменты F#**.</span><span class="sxs-lookup"><span data-stu-id="04ae0-201">On the **Tools** menu, select **Options...**, and then expand **F# Tools**.</span></span> <span data-ttu-id="04ae0-202">Двумя параметрами, которые можно изменить, являются параметры F# Interactive и параметр **F# Interactive, 64-разрядная версия**, который используется только в том случае, если F# Interactive выполняется на 64-разрядном компьютере.</span><span class="sxs-lookup"><span data-stu-id="04ae0-202">The two settings that you can change are the F# Interactive options and the **64-bit F# Interactive** setting, which is relevant only if you are running F# Interactive on a 64-bit machine.</span></span> <span data-ttu-id="04ae0-203">Этот параметр указывает, следует ли выполнять выделенную 64-разрядную версию **fsi.exe** или **fsianycpu.exe**, которая использует архитектуру компьютера для определения типа выполняемого процесса — 32- или 64-разрядного.</span><span class="sxs-lookup"><span data-stu-id="04ae0-203">This setting determines whether you want to run the dedicated 64-bit version of **fsi.exe** or **fsianycpu.exe**, which uses the machine architecture to determine whether to run as a 32-bit or 64-bit process.</span></span>

## <a name="related-articles"></a><span data-ttu-id="04ae0-204">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="04ae0-204">Related articles</span></span>

|<span data-ttu-id="04ae0-205">Заголовок</span><span class="sxs-lookup"><span data-stu-id="04ae0-205">Title</span></span>|<span data-ttu-id="04ae0-206">Описание:</span><span class="sxs-lookup"><span data-stu-id="04ae0-206">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="04ae0-207">Параметры F# Interactive</span><span class="sxs-lookup"><span data-stu-id="04ae0-207">F# Interactive Options</span></span>](../../language-reference/fsharp-interactive-options.md)|<span data-ttu-id="04ae0-208">Описание синтаксиса команд и параметров для F# Interactive, fsi.exe.</span><span class="sxs-lookup"><span data-stu-id="04ae0-208">Describes command-line syntax and options for the F# Interactive, fsi.exe.</span></span>|
