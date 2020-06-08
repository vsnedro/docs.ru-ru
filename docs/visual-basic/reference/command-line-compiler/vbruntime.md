---
title: -vbruntime
ms.date: 03/13/2018
f1_keywords:
- vbruntime
- -vbruntime
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
ms.openlocfilehash: 31b719fb7e43cdd6ac44424b359999410dd608a5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403048"
---
# <a name="-vbruntime"></a><span data-ttu-id="c37d2-102">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="c37d2-102">-vbruntime</span></span>
<span data-ttu-id="c37d2-103">Указывает, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic или со ссылкой на конкретную библиотеку времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="c37d2-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c37d2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c37d2-104">Syntax</span></span>  
  
```console  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="c37d2-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c37d2-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="c37d2-106">Компиляция без ссылки на библиотеку среды выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c37d2-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="c37d2-107">Компиляция со ссылкой на библиотеку среды выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c37d2-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="c37d2-108">Компиляция без ссылки на библиотеку среды выполнения Visual Basic и внедрение основных функции из этой библиотеки в сборку.</span><span class="sxs-lookup"><span data-stu-id="c37d2-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="c37d2-109">Компиляция со ссылкой на определенную библиотеку (DLL).</span><span class="sxs-lookup"><span data-stu-id="c37d2-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c37d2-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="c37d2-110">Remarks</span></span>  
 <span data-ttu-id="c37d2-111">Параметр компилятора `-vbruntime` позволяет указать, что компилятор должен выполнять компиляцию без ссылки на библиотеку среды выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c37d2-111">The `-vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="c37d2-112">В таком случае ошибки или предупреждения записываются для строк кода или языковых конструкций, которые выполняют вызов к вспомогательной функции среды выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c37d2-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="c37d2-113">(*Вспомогательная функция среды выполнения Visual Basic* — это функция, определенная в Microsoft.VisualBasic.dll, которая вызывается во время выполнения для реализации определенной семантики языка.)</span><span class="sxs-lookup"><span data-stu-id="c37d2-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="c37d2-114">Если параметр `-vbruntime+` не указан, поведение будет таким же, как и при указании параметра `-vbruntime`.</span><span class="sxs-lookup"><span data-stu-id="c37d2-114">The `-vbruntime+` option produces the same behavior that occurs if no `-vbruntime` switch is specified.</span></span> <span data-ttu-id="c37d2-115">Параметр `-vbruntime+` можно использовать для переопределения предыдущих параметров `-vbruntime`.</span><span class="sxs-lookup"><span data-stu-id="c37d2-115">You can use the `-vbruntime+` option to override previous `-vbruntime` switches.</span></span>  
  
 <span data-ttu-id="c37d2-116">Большинство объектов с типом `My` недоступны при использовании параметра `-vbruntime-` или `-vbruntime:path`.</span><span class="sxs-lookup"><span data-stu-id="c37d2-116">Most objects of the `My` type are unavailable when you use the `-vbruntime-` or `-vbruntime:path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="c37d2-117">Реализация основных функций среды выполнения Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c37d2-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="c37d2-118">Параметр `-vbruntime*` позволяет выполнять компиляцию без ссылки на библиотеку среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c37d2-118">The `-vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="c37d2-119">Вместо этого основные функции из библиотеки среды выполнения Visual Basic внедряются в пользовательскую сборку.</span><span class="sxs-lookup"><span data-stu-id="c37d2-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="c37d2-120">Этот параметр можно использовать, если приложение выполняется на платформах без среды выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c37d2-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="c37d2-121">Внедряются следующие элементы среды выполнения:</span><span class="sxs-lookup"><span data-stu-id="c37d2-121">The following runtime members are embedded:</span></span>  
  
- <span data-ttu-id="c37d2-122">Класс <xref:Microsoft.VisualBasic.CompilerServices.Conversions></span><span class="sxs-lookup"><span data-stu-id="c37d2-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
- <span data-ttu-id="c37d2-123">Метод <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29></span><span class="sxs-lookup"><span data-stu-id="c37d2-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
- <span data-ttu-id="c37d2-124">Метод <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="c37d2-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
- <span data-ttu-id="c37d2-125">Метод <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29></span><span class="sxs-lookup"><span data-stu-id="c37d2-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
- <span data-ttu-id="c37d2-126">константа <xref:Microsoft.VisualBasic.Constants.vbBack>;</span><span class="sxs-lookup"><span data-stu-id="c37d2-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
- <span data-ttu-id="c37d2-127">константа <xref:Microsoft.VisualBasic.Constants.vbCr>;</span><span class="sxs-lookup"><span data-stu-id="c37d2-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
- <span data-ttu-id="c37d2-128">константа <xref:Microsoft.VisualBasic.Constants.vbCrLf>;</span><span class="sxs-lookup"><span data-stu-id="c37d2-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
- <span data-ttu-id="c37d2-129">константа <xref:Microsoft.VisualBasic.Constants.vbFormFeed>;</span><span class="sxs-lookup"><span data-stu-id="c37d2-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
- <span data-ttu-id="c37d2-130">константа <xref:Microsoft.VisualBasic.Constants.vbLf>;</span><span class="sxs-lookup"><span data-stu-id="c37d2-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
- <span data-ttu-id="c37d2-131">константа <xref:Microsoft.VisualBasic.Constants.vbNewLine>;</span><span class="sxs-lookup"><span data-stu-id="c37d2-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
- <span data-ttu-id="c37d2-132">константа <xref:Microsoft.VisualBasic.Constants.vbNullChar>;</span><span class="sxs-lookup"><span data-stu-id="c37d2-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
- <span data-ttu-id="c37d2-133">константа <xref:Microsoft.VisualBasic.Constants.vbNullString>;</span><span class="sxs-lookup"><span data-stu-id="c37d2-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
- <span data-ttu-id="c37d2-134">константа <xref:Microsoft.VisualBasic.Constants.vbTab>;</span><span class="sxs-lookup"><span data-stu-id="c37d2-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
- <span data-ttu-id="c37d2-135">константа <xref:Microsoft.VisualBasic.Constants.vbVerticalTab>;</span><span class="sxs-lookup"><span data-stu-id="c37d2-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
- <span data-ttu-id="c37d2-136">некоторые объекты с типом `My`.</span><span class="sxs-lookup"><span data-stu-id="c37d2-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="c37d2-137">Если компиляция выполняется с параметром `-vbruntime*` и код ссылается на элемент из библиотеки среды выполнения Visual Basic, который не внедрен в основные функции, компилятор возвращает ошибку, указывающую на недоступность элемента.</span><span class="sxs-lookup"><span data-stu-id="c37d2-137">If you compile using the `-vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="c37d2-138">Использование ссылки на определенную библиотеку</span><span class="sxs-lookup"><span data-stu-id="c37d2-138">Referencing a specified library</span></span>  
 <span data-ttu-id="c37d2-139">Вы можете использовать аргумент `path` для компиляции со ссылкой на пользовательскую библиотеку среды выполнения вместо стандартной библиотеки среды выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c37d2-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="c37d2-140">Если в качестве значения аргумента `path` указан полный путь к библиотеке DLL, компилятор будет использовать этот файл как библиотеку среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c37d2-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="c37d2-141">Если значение аргумента `path` не является полным путем к DLL, компилятор Visual Basic сначала выполнит поиск определенной библиотеки DLL в текущей папке.</span><span class="sxs-lookup"><span data-stu-id="c37d2-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="c37d2-142">Затем он выполнит поиск в папке, которую вы указали с помощью параметра компилятора [-sdkpath](sdkpath.md).</span><span class="sxs-lookup"><span data-stu-id="c37d2-142">It will then search in the path that you have specified by using the [-sdkpath](sdkpath.md) compiler option.</span></span> <span data-ttu-id="c37d2-143">Если параметр компилятора `-sdkpath` не используется, компилятор выполнит поиск определенной библиотеки DLL в папке .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span><span class="sxs-lookup"><span data-stu-id="c37d2-143">If the `-sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c37d2-144">Пример</span><span class="sxs-lookup"><span data-stu-id="c37d2-144">Example</span></span>  
 <span data-ttu-id="c37d2-145">В следующем примере показано, как использовать параметр `-vbruntime` для компиляции со ссылкой на пользовательскую библиотеку.</span><span class="sxs-lookup"><span data-stu-id="c37d2-145">The following example shows how to use the `-vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="c37d2-146">См. также</span><span class="sxs-lookup"><span data-stu-id="c37d2-146">See also</span></span>

- [<span data-ttu-id="c37d2-147">Visual Basic Core — новый режим компиляции в Visual Studio 2010 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="c37d2-147">Visual Basic Core – New compilation mode in Visual Studio 2010 SP1</span></span>](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [<span data-ttu-id="c37d2-148">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="c37d2-148">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="c37d2-149">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="c37d2-149">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="c37d2-150">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="c37d2-150">-sdkpath</span></span>](sdkpath.md)
