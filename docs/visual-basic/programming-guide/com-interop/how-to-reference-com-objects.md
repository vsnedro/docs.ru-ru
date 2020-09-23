---
title: Практическое руководство. Ссылка на COM-объект в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
ms.openlocfilehash: 43ba068663db9f8c3816a6f731395a6682a130e6
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91083297"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a><span data-ttu-id="37d02-102">Практическое руководство. Ссылка на COM-объект в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="37d02-102">How to: Reference COM Objects from Visual Basic</span></span>

<span data-ttu-id="37d02-103">В Visual Basic добавление ссылок на COM-объекты, имеющие библиотеки типов, требует создания сборки взаимодействия для библиотеки COM.</span><span class="sxs-lookup"><span data-stu-id="37d02-103">In Visual Basic, adding references to COM objects that have type libraries requires the creation of an interop assembly for the COM library.</span></span> <span data-ttu-id="37d02-104">Ссылки на члены COM-объекта направляются в сборку взаимодействия, а затем пересылаются на фактический COM-объект.</span><span class="sxs-lookup"><span data-stu-id="37d02-104">References to the members of the COM object are routed to the interop assembly and then forwarded to the actual COM object.</span></span> <span data-ttu-id="37d02-105">Ответы от COM-объекта направляются в сборку взаимодействия и пересылаются в приложение .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="37d02-105">Responses from the COM object are routed to the interop assembly and forwarded to your .NET Framework application.</span></span>  
  
 <span data-ttu-id="37d02-106">Вы можете ссылаться на COM-объект без использования сборки взаимодействия, внедрив сведения о типе для COM-объекта в сборку .NET.</span><span class="sxs-lookup"><span data-stu-id="37d02-106">You can reference a COM object without using an interop assembly by embedding the type information for the COM object in a .NET assembly.</span></span> <span data-ttu-id="37d02-107">Чтобы внедрить сведения о типе, задайте `Embed Interop Types` для свойства значение, чтобы `True` получить ссылку на COM-объект.</span><span class="sxs-lookup"><span data-stu-id="37d02-107">To embed type information, set the `Embed Interop Types` property to `True` for the reference to the COM object.</span></span> <span data-ttu-id="37d02-108">При компиляции с помощью компилятора командной строки используйте `/link` параметр для ссылки на БИБЛИОТЕКУ com.</span><span class="sxs-lookup"><span data-stu-id="37d02-108">If you are compiling by using the command-line compiler, use the `/link` option to reference the COM library.</span></span> <span data-ttu-id="37d02-109">Дополнительные сведения см. в разделе [-Link (Visual Basic)](../../reference/command-line-compiler/link.md).</span><span class="sxs-lookup"><span data-stu-id="37d02-109">For more information, see [-link (Visual Basic)](../../reference/command-line-compiler/link.md).</span></span>  
  
 <span data-ttu-id="37d02-110">Visual Basic автоматически создает сборки взаимодействия при добавлении ссылки на библиотеку типов из интегрированной среды разработки (IDE).</span><span class="sxs-lookup"><span data-stu-id="37d02-110">Visual Basic automatically creates interop assemblies when you add a reference to a type library from the integrated development environment (IDE).</span></span> <span data-ttu-id="37d02-111">При работе из командной строки можно использовать служебную программу Tlbimp для создания сборок взаимодействия вручную.</span><span class="sxs-lookup"><span data-stu-id="37d02-111">When working from the command line, you can use the Tlbimp utility to manually create interop assemblies.</span></span>  
  
### <a name="to-add-references-to-com-objects"></a><span data-ttu-id="37d02-112">Добавление ссылок на COM-объекты</span><span class="sxs-lookup"><span data-stu-id="37d02-112">To add references to COM objects</span></span>  
  
1. <span data-ttu-id="37d02-113">В меню **проект** выберите команду **Добавить ссылку** , а затем откройте вкладку **com** в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="37d02-113">On the **Project** menu, choose **Add Reference** and then click the **COM** tab in the dialog box.</span></span>  
  
2. <span data-ttu-id="37d02-114">Выберите компонент, который вы хотите использовать, из списка COM-объектов.</span><span class="sxs-lookup"><span data-stu-id="37d02-114">Select the component you want to use from the list of COM objects.</span></span>  
  
3. <span data-ttu-id="37d02-115">Чтобы упростить доступ к сборке взаимодействия, добавьте `Imports` оператор в начало класса или модуля, в котором будет использоваться COM-объект.</span><span class="sxs-lookup"><span data-stu-id="37d02-115">To simplify access to the interop assembly, add an `Imports` statement to the top of the class or module in which you will use the COM object.</span></span> <span data-ttu-id="37d02-116">Например, в следующем примере кода выполняется импорт пространства имен `INKEDLib` для объектов, упоминаемых в `Microsoft InkEdit Control 1.0` библиотеке.</span><span class="sxs-lookup"><span data-stu-id="37d02-116">For example, the following code example imports the namespace `INKEDLib` for objects referenced in the `Microsoft InkEdit Control 1.0` library.</span></span>  
  
     [!code-vb[VbVbalrInterop#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#40)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a><span data-ttu-id="37d02-117">Создание сборки взаимодействия с помощью программы Tlbimp</span><span class="sxs-lookup"><span data-stu-id="37d02-117">To create an interop assembly using Tlbimp</span></span>  
  
1. <span data-ttu-id="37d02-118">Добавьте расположение программы Tlbimp в путь поиска, если он еще не является частью пути поиска, и вы не находитесь в каталоге, в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="37d02-118">Add the location of Tlbimp to the search path, if it is not already part of the search path and you are not currently in the directory where it is located.</span></span>  
  
2. <span data-ttu-id="37d02-119">Вызовите программу Tlbimp из командной строки, предоставив следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="37d02-119">Call Tlbimp from a command prompt, providing the following information:</span></span>  
  
    - <span data-ttu-id="37d02-120">Имя и расположение библиотеки DLL, содержащей библиотеку типов</span><span class="sxs-lookup"><span data-stu-id="37d02-120">Name and location of the DLL that contains the type library</span></span>  
  
    - <span data-ttu-id="37d02-121">Имя и расположение пространства имен, в которое следует поместить данные</span><span class="sxs-lookup"><span data-stu-id="37d02-121">Name and location of the namespace where the information should be placed</span></span>  
  
    - <span data-ttu-id="37d02-122">Имя и расположение целевой сборки взаимодействия</span><span class="sxs-lookup"><span data-stu-id="37d02-122">Name and location of the target interop assembly</span></span>  
  
     <span data-ttu-id="37d02-123">Примером является следующий код:</span><span class="sxs-lookup"><span data-stu-id="37d02-123">The following code provides an example:</span></span>  
  
    ```console  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     <span data-ttu-id="37d02-124">Программу Tlbimp можно использовать для создания сборок взаимодействия для библиотек типов, даже для незарегистрированных COM-объектов.</span><span class="sxs-lookup"><span data-stu-id="37d02-124">You can use Tlbimp to create interop assemblies for type libraries, even for unregistered COM objects.</span></span> <span data-ttu-id="37d02-125">Однако COM-объекты, на которые ссылаются сборки взаимодействия, должны быть правильно зарегистрированы на компьютере, где они будут использоваться.</span><span class="sxs-lookup"><span data-stu-id="37d02-125">However, the COM objects referred to by interop assemblies must be properly registered on the computer where they are to be used.</span></span> <span data-ttu-id="37d02-126">Вы можете зарегистрировать COM-объект с помощью служебной программы regsvr32, входящей в состав операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="37d02-126">You can register a COM object by using the Regsvr32 utility included with the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37d02-127">См. также</span><span class="sxs-lookup"><span data-stu-id="37d02-127">See also</span></span>

- [<span data-ttu-id="37d02-128">COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="37d02-128">COM Interop</span></span>](index.md)
- [<span data-ttu-id="37d02-129">Tlbimp.exe (программа экспорта библиотек типов)</span><span class="sxs-lookup"><span data-stu-id="37d02-129">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [<span data-ttu-id="37d02-130">Tlbexp.exe (программа экспорта библиотек типов)</span><span class="sxs-lookup"><span data-stu-id="37d02-130">Tlbexp.exe (Type Library Exporter)</span></span>](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [<span data-ttu-id="37d02-131">Пошаговое руководство. Реализация наследования с использованием COM-объектов</span><span class="sxs-lookup"><span data-stu-id="37d02-131">Walkthrough: Implementing Inheritance with COM Objects</span></span>](walkthrough-implementing-inheritance-with-com-objects.md)
- [<span data-ttu-id="37d02-132">Устранение неполадок взаимодействия</span><span class="sxs-lookup"><span data-stu-id="37d02-132">Troubleshooting Interoperability</span></span>](troubleshooting-interoperability.md)
- [<span data-ttu-id="37d02-133">Оператор Imports (пространство имен .NET и тип)</span><span class="sxs-lookup"><span data-stu-id="37d02-133">Imports Statement (.NET Namespace and Type)</span></span>](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
