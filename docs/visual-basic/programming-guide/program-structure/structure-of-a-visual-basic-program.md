---
title: Структура программы Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], Visual Basic
- program structure [Visual Basic], Visual Basic
- procedures [Visual Basic], structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
ms.openlocfilehash: 90bc1fd62a05f670424e1fac368376401d1030c0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097778"
---
# <a name="structure-of-a-visual-basic-program"></a><span data-ttu-id="3eeb5-102">Структура программы Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3eeb5-102">Structure of a Visual Basic Program</span></span>

<span data-ttu-id="3eeb5-103">Visual Basicная программа строится на основе стандартных блоков.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-103">A Visual Basic program is built up from standard building blocks.</span></span> <span data-ttu-id="3eeb5-104">*Решение* состоит из одного или нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-104">A *solution* comprises one or more projects.</span></span> <span data-ttu-id="3eeb5-105">*Проект* , в свою очередь, может содержать одну или несколько сборок.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-105">A *project* in turn can contain one or more assemblies.</span></span> <span data-ttu-id="3eeb5-106">Каждая *Сборка* компилируется из одного или нескольких исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-106">Each *assembly* is compiled from one or more source files.</span></span> <span data-ttu-id="3eeb5-107">*Исходный файл* предоставляет определение и реализацию классов, структур, модулей и интерфейсов, которые в конечном итоге содержат весь код.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-107">A *source file* provides the definition and implementation of classes, structures, modules, and interfaces, which ultimately contain all your code.</span></span>  
  
 <span data-ttu-id="3eeb5-108">Дополнительные сведения об этих стандартных блоках Visual Basic программы см. в разделе [решения и проекты](/visualstudio/ide/solutions-and-projects-in-visual-studio) и [сборки в .NET](../../../standard/assembly/index.md).</span><span class="sxs-lookup"><span data-stu-id="3eeb5-108">For more information about these building blocks of a Visual Basic program, see [Solutions and Projects](/visualstudio/ide/solutions-and-projects-in-visual-studio) and [Assemblies in .NET](../../../standard/assembly/index.md).</span></span>  
  
## <a name="file-level-programming-elements"></a><span data-ttu-id="3eeb5-109">Элементы программирования на уровне файлов</span><span class="sxs-lookup"><span data-stu-id="3eeb5-109">File-Level Programming Elements</span></span>  

 <span data-ttu-id="3eeb5-110">При запуске проекта или файла и открытии редактора кода вы увидите, что какой-то код уже существует и в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-110">When you start a project or file and open the code editor, you see some code already in place and in the correct order.</span></span> <span data-ttu-id="3eeb5-111">Любой код, который вы пишете, должен соответствовать следующей последовательности:</span><span class="sxs-lookup"><span data-stu-id="3eeb5-111">Any code that you write should follow the following sequence:</span></span>  
  
1. <span data-ttu-id="3eeb5-112">`Option` инструкции</span><span class="sxs-lookup"><span data-stu-id="3eeb5-112">`Option` statements</span></span>  
  
2. <span data-ttu-id="3eeb5-113">`Imports` инструкции</span><span class="sxs-lookup"><span data-stu-id="3eeb5-113">`Imports` statements</span></span>  
  
3. <span data-ttu-id="3eeb5-114">`Namespace` операторы и элементы уровня пространства имен</span><span class="sxs-lookup"><span data-stu-id="3eeb5-114">`Namespace` statements and namespace-level elements</span></span>  
  
 <span data-ttu-id="3eeb5-115">При вводе инструкций в другом порядке могут возникнуть ошибки компиляции.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-115">If you enter statements in a different order, compilation errors can result.</span></span>  
  
 <span data-ttu-id="3eeb5-116">Программа также может содержать инструкции условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-116">A program can also contain conditional compilation statements.</span></span> <span data-ttu-id="3eeb5-117">Их можно отключать в исходном файле между инструкциями предыдущей последовательности.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-117">You can intersperse these in the source file among the statements of the preceding sequence.</span></span>  
  
### <a name="option-statements"></a><span data-ttu-id="3eeb5-118">Операторы Option</span><span class="sxs-lookup"><span data-stu-id="3eeb5-118">Option Statements</span></span>  

 <span data-ttu-id="3eeb5-119">`Option` инструкции устанавливают правила заземления для последующего кода, помогая предотвратить синтаксические и логические ошибки.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-119">`Option` statements establish ground rules for subsequent code, helping prevent syntax and logic errors.</span></span> <span data-ttu-id="3eeb5-120">[Оператор Option Explicit](../../language-reference/statements/option-explicit-statement.md) гарантирует, что все переменные объявляются и написаны правильно, что сокращает время отладки.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-120">The [Option Explicit Statement](../../language-reference/statements/option-explicit-statement.md) ensures that all variables are declared and spelled correctly, which reduces debugging time.</span></span> <span data-ttu-id="3eeb5-121">[Оператор Option-Statement](../../language-reference/statements/option-strict-statement.md) позволяет снизить количество логических ошибок и потери данных, которые могут возникать при работе между переменными различных типов данных.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-121">The [Option Strict Statement](../../language-reference/statements/option-strict-statement.md) helps to minimize logic errors and data loss that can occur when you work between variables of different data types.</span></span> <span data-ttu-id="3eeb5-122">[Оператор Option Compare](../../language-reference/statements/option-compare-statement.md) указывает, каким образом строки сравниваются друг с другом на основе их `Binary` `Text` значений или.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-122">The [Option Compare Statement](../../language-reference/statements/option-compare-statement.md) specifies the way strings are compared to each other, based on either their `Binary` or `Text` values.</span></span>  
  
### <a name="imports-statements"></a><span data-ttu-id="3eeb5-123">Операторы Imports</span><span class="sxs-lookup"><span data-stu-id="3eeb5-123">Imports Statements</span></span>  

 <span data-ttu-id="3eeb5-124">Можно включить [оператор Imports (пространство имен .NET и тип)](../../language-reference/statements/imports-statement-net-namespace-and-type.md) для импорта имен, определенных за пределами проекта.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-124">You can include an [Imports Statement (.NET Namespace and Type)](../../language-reference/statements/imports-statement-net-namespace-and-type.md) to import names defined outside your project.</span></span> <span data-ttu-id="3eeb5-125">`Imports`Оператор позволяет коду ссылаться на классы и другие типы, определенные в импортированном пространстве имен, без необходимости уточнять их.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-125">An `Imports` statement allows your code to refer to classes and other types defined within the imported namespace, without having to qualify them.</span></span> <span data-ttu-id="3eeb5-126">Можно использовать столько `Imports` инструкций, сколько необходимо.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-126">You can use as many `Imports` statements as appropriate.</span></span> <span data-ttu-id="3eeb5-127">Дополнительные сведения см. [в разделе ссылки и оператор Imports](references-and-the-imports-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3eeb5-127">For more information, see [References and the Imports Statement](references-and-the-imports-statement.md).</span></span>  
  
### <a name="namespace-statements"></a><span data-ttu-id="3eeb5-128">Операторы пространства имен</span><span class="sxs-lookup"><span data-stu-id="3eeb5-128">Namespace Statements</span></span>  

 <span data-ttu-id="3eeb5-129">Пространства имен помогают организовывать и классифицировать программные элементы для простоты группирования и доступа.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-129">Namespaces help you organize and classify your programming elements for ease of grouping and accessing.</span></span> <span data-ttu-id="3eeb5-130">[Оператор Namespace](../../language-reference/statements/namespace-statement.md) используется для классификации следующих операторов в определенном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-130">You use the [Namespace Statement](../../language-reference/statements/namespace-statement.md) to classify the following statements within a particular namespace.</span></span> <span data-ttu-id="3eeb5-131">Дополнительные сведения см. в разделе [Пространства имен в Visual Basic](namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="3eeb5-131">For more information, see [Namespaces in Visual Basic](namespaces.md).</span></span>  
  
### <a name="conditional-compilation-statements"></a><span data-ttu-id="3eeb5-132">Операторы условной компиляции</span><span class="sxs-lookup"><span data-stu-id="3eeb5-132">Conditional Compilation Statements</span></span>  

 <span data-ttu-id="3eeb5-133">Операторы условной компиляции могут находиться практически в любом месте исходного файла.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-133">Conditional compilation statements can appear almost anywhere in your source file.</span></span> <span data-ttu-id="3eeb5-134">Они приводят к включению или исключению частей кода во время компиляции в зависимости от определенных условий.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-134">They cause parts of your code to be included or excluded at compile time depending on certain conditions.</span></span> <span data-ttu-id="3eeb5-135">Их также можно использовать для отладки приложения, так как условный код выполняется только в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-135">You can also use them for debugging your application, because conditional code runs in debugging mode only.</span></span> <span data-ttu-id="3eeb5-136">Дополнительные сведения см. в разделе [условная компиляция](conditional-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="3eeb5-136">For more information, see [Conditional Compilation](conditional-compilation.md).</span></span>  
  
## <a name="namespace-level-programming-elements"></a><span data-ttu-id="3eeb5-137">Элементы программирования уровня пространства имен</span><span class="sxs-lookup"><span data-stu-id="3eeb5-137">Namespace-Level Programming Elements</span></span>  

 <span data-ttu-id="3eeb5-138">Классы, структуры и модули содержат весь код в исходном файле.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-138">Classes, structures, and modules contain all the code in your source file.</span></span> <span data-ttu-id="3eeb5-139">Они представляют собой элементы *уровня пространства имен* , которые могут использоваться в пространстве имен или на уровне исходного файла.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-139">They are *namespace-level* elements, which can appear within a namespace or at the source file level.</span></span> <span data-ttu-id="3eeb5-140">Они содержат объявления всех других программных элементов.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-140">They hold the declarations of all other programming elements.</span></span> <span data-ttu-id="3eeb5-141">Интерфейсы, которые определяют подписи элементов, но не предоставляют реализации, также отображаются на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-141">Interfaces, which define element signatures but provide no implementation, also appear at module level.</span></span> <span data-ttu-id="3eeb5-142">Дополнительные сведения об элементах уровня модуля см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="3eeb5-142">For more information on the module-level elements, see the following:</span></span>  
  
- [<span data-ttu-id="3eeb5-143">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="3eeb5-143">Class Statement</span></span>](../../language-reference/statements/class-statement.md)  
  
- [<span data-ttu-id="3eeb5-144">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="3eeb5-144">Structure Statement</span></span>](../../language-reference/statements/structure-statement.md)  
  
- [<span data-ttu-id="3eeb5-145">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="3eeb5-145">Module Statement</span></span>](../../language-reference/statements/module-statement.md)  
  
- [<span data-ttu-id="3eeb5-146">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="3eeb5-146">Interface Statement</span></span>](../../language-reference/statements/interface-statement.md)  
  
 <span data-ttu-id="3eeb5-147">Элементы данных на уровне пространства имен являются перечислениями и делегатами.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-147">Data elements at namespace level are enumerations and delegates.</span></span>  
  
## <a name="module-level-programming-elements"></a><span data-ttu-id="3eeb5-148">Элементы программирования уровня модуля</span><span class="sxs-lookup"><span data-stu-id="3eeb5-148">Module-Level Programming Elements</span></span>  

 <span data-ttu-id="3eeb5-149">Процедуры, операторы, свойства и события — это единственные элементы программирования, которые могут содержать исполняемый код (операторы, выполняющие действия во время выполнения).</span><span class="sxs-lookup"><span data-stu-id="3eeb5-149">Procedures, operators, properties, and events are the only programming elements that can hold executable code (statements that perform actions at run time).</span></span> <span data-ttu-id="3eeb5-150">Они являются элементами *уровня модуля* программы.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-150">They are the *module-level* elements of your program.</span></span> <span data-ttu-id="3eeb5-151">Дополнительные сведения об элементах уровня процедуры см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="3eeb5-151">For more information on the procedure-level elements, see the following:</span></span>  
  
- [<span data-ttu-id="3eeb5-152">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="3eeb5-152">Function Statement</span></span>](../../language-reference/statements/function-statement.md)  
  
- [<span data-ttu-id="3eeb5-153">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="3eeb5-153">Sub Statement</span></span>](../../language-reference/statements/sub-statement.md)  
  
- [<span data-ttu-id="3eeb5-154">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="3eeb5-154">Declare Statement</span></span>](../../language-reference/statements/declare-statement.md)  
  
- [<span data-ttu-id="3eeb5-155">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="3eeb5-155">Operator Statement</span></span>](../../language-reference/statements/operator-statement.md)  
  
- [<span data-ttu-id="3eeb5-156">Property Statement</span><span class="sxs-lookup"><span data-stu-id="3eeb5-156">Property Statement</span></span>](../../language-reference/statements/property-statement.md)  
  
- [<span data-ttu-id="3eeb5-157">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="3eeb5-157">Event Statement</span></span>](../../language-reference/statements/event-statement.md)  
  
 <span data-ttu-id="3eeb5-158">Элементы данных на уровне модуля — это переменные, константы, перечисления и делегаты.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-158">Data elements at module level are variables, constants, enumerations, and delegates.</span></span>  
  
## <a name="procedure-level-programming-elements"></a><span data-ttu-id="3eeb5-159">Элементы программирования на уровне процедур</span><span class="sxs-lookup"><span data-stu-id="3eeb5-159">Procedure-Level Programming Elements</span></span>  

 <span data-ttu-id="3eeb5-160">Большая часть содержимого элементов *уровня процедуры* — это исполняемые операторы, которые составляют код времени выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-160">Most of the contents of *procedure-level* elements are executable statements, which constitute the run-time code of your program.</span></span> <span data-ttu-id="3eeb5-161">Весь исполняемый код должен быть в некоторой процедуре ( `Function` ,,,,,, `Sub` `Operator` `Get` `Set` `AddHandler` `RemoveHandler` , `RaiseEvent` ).</span><span class="sxs-lookup"><span data-stu-id="3eeb5-161">All executable code must be in some procedure (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`).</span></span> <span data-ttu-id="3eeb5-162">Дополнительные сведения см. в разделе [Инструкции](../language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="3eeb5-162">For more information, see [Statements](../language-features/statements.md).</span></span>  
  
 <span data-ttu-id="3eeb5-163">Элементы данных на уровне процедуры ограничены локальными переменными и константами.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-163">Data elements at procedure level are limited to local variables and constants.</span></span>  
  
## <a name="the-main-procedure"></a><span data-ttu-id="3eeb5-164">Основная процедура</span><span class="sxs-lookup"><span data-stu-id="3eeb5-164">The Main Procedure</span></span>  

 <span data-ttu-id="3eeb5-165">`Main`Процедура является первым кодом, который выполняется при загрузке приложения.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-165">The `Main` procedure is the first code to run when your application has been loaded.</span></span> <span data-ttu-id="3eeb5-166">`Main` служит в качестве начальной точки и общего управления для приложения.</span><span class="sxs-lookup"><span data-stu-id="3eeb5-166">`Main` serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="3eeb5-167">Существует четыре вида `Main` :</span><span class="sxs-lookup"><span data-stu-id="3eeb5-167">There are four varieties of `Main`:</span></span>  
  
- `Sub Main()`  
  
- `Sub Main(ByVal cmdArgs() As String)`  
  
- `Function Main() As Integer`  
  
- `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 <span data-ttu-id="3eeb5-168">Наиболее распространенная часть этой процедуры — `Sub Main()` .</span><span class="sxs-lookup"><span data-stu-id="3eeb5-168">The most common variety of this procedure is `Sub Main()`.</span></span> <span data-ttu-id="3eeb5-169">Дополнительные сведения см. [в разделе Главная процедура в Visual Basic](main-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="3eeb5-169">For more information, see [Main Procedure in Visual Basic](main-procedure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eeb5-170">См. также</span><span class="sxs-lookup"><span data-stu-id="3eeb5-170">See also</span></span>

- [<span data-ttu-id="3eeb5-171">Процедура Main в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3eeb5-171">Main Procedure in Visual Basic</span></span>](main-procedure.md)
- [<span data-ttu-id="3eeb5-172">Соглашения об именах Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3eeb5-172">Visual Basic Naming Conventions</span></span>](naming-conventions.md)
- [<span data-ttu-id="3eeb5-173">Ограничения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3eeb5-173">Visual Basic Limitations</span></span>](limitations.md)
