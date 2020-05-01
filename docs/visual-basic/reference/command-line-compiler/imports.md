---
title: -imports
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 2a1dd19189ff65413255b9bc137e1a7f0227bbe1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716650"
---
# <a name="-imports-visual-basic"></a><span data-ttu-id="93b05-102">-imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93b05-102">-imports (Visual Basic)</span></span>
<span data-ttu-id="93b05-103">Импортирует пространства имен из указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="93b05-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93b05-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93b05-104">Syntax</span></span>  
  
```console  
-imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="93b05-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="93b05-105">Arguments</span></span>  
  
|<span data-ttu-id="93b05-106">Термин</span><span class="sxs-lookup"><span data-stu-id="93b05-106">Term</span></span>|<span data-ttu-id="93b05-107">Определение</span><span class="sxs-lookup"><span data-stu-id="93b05-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="93b05-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="93b05-108">Required.</span></span> <span data-ttu-id="93b05-109">Разделенный запятыми список пространств имен для импорта.</span><span class="sxs-lookup"><span data-stu-id="93b05-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93b05-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="93b05-110">Remarks</span></span>  
 <span data-ttu-id="93b05-111">Параметр `-imports` импортирует любое пространство имен, определенное в текущем наборе исходных файлов или любой связанной сборке.</span><span class="sxs-lookup"><span data-stu-id="93b05-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="93b05-112">Элементы в пространстве имен, заданном с помощью `-imports`, доступны для всех файлов исходного кода в компиляции.</span><span class="sxs-lookup"><span data-stu-id="93b05-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="93b05-113">Используйте [оператор Imports (пространство имен и тип .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md), чтобы использовать пространство имен в одном файле исходного кода.</span><span class="sxs-lookup"><span data-stu-id="93b05-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="93b05-114">Настройка параметра -imports в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="93b05-114">To set -imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="93b05-115">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="93b05-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="93b05-116">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="93b05-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="93b05-117">2.  Перейдите на вкладку **Ссылки**.</span><span class="sxs-lookup"><span data-stu-id="93b05-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="93b05-118">3.  Введите имя пространства имен в поле рядом с кнопкой **Добавить пользовательский импорт**.</span><span class="sxs-lookup"><span data-stu-id="93b05-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="93b05-119">4.  Нажмите кнопку **Добавить пользовательский импорт**.</span><span class="sxs-lookup"><span data-stu-id="93b05-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="93b05-120">Пример</span><span class="sxs-lookup"><span data-stu-id="93b05-120">Example</span></span>  
 <span data-ttu-id="93b05-121">Следующий код компилируется, когда указан параметр `-imports:system.globalization`.</span><span class="sxs-lookup"><span data-stu-id="93b05-121">The following code compiles when `-imports:system.globalization` is specified.</span></span> <span data-ttu-id="93b05-122">В противном случае для успешной компиляции требуется, чтобы инструкция `Imports System.Globalization` была включена в начало файла исходного кода или чтобы свойство было полностью определено как `System.Globalization.CultureInfo.CurrentCulture.Name`.</span><span class="sxs-lookup"><span data-stu-id="93b05-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span></span>

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a><span data-ttu-id="93b05-123">См. также</span><span class="sxs-lookup"><span data-stu-id="93b05-123">See also</span></span>

- [<span data-ttu-id="93b05-124">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="93b05-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="93b05-125">Ссылки и оператор Imports</span><span class="sxs-lookup"><span data-stu-id="93b05-125">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="93b05-126">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="93b05-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
