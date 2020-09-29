---
title: -optionexplicit
ms.date: 07/20/2015
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
ms.openlocfilehash: 65cc3fb1b2fa9daa04013caa2b93a3949d0a15b9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91098940"
---
# <a name="-optionexplicit"></a><span data-ttu-id="c4122-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="c4122-102">-optionexplicit</span></span>

<span data-ttu-id="c4122-103">Заставляет компилятор сообщать об ошибках, если переменные не объявляются до их использования.</span><span class="sxs-lookup"><span data-stu-id="c4122-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4122-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4122-104">Syntax</span></span>  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c4122-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c4122-105">Arguments</span></span>  

 <span data-ttu-id="c4122-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="c4122-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="c4122-107">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="c4122-107">Optional.</span></span> <span data-ttu-id="c4122-108">Чтобы сделать явное объявление переменных обязательным, укажите `-optionexplicit+`.</span><span class="sxs-lookup"><span data-stu-id="c4122-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="c4122-109">Параметр `-optionexplicit+` используется по умолчанию и аналогичен параметру `-optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="c4122-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="c4122-110">Используйте параметр `-optionexplicit-`, чтобы разрешить неявное объявление переменных.</span><span class="sxs-lookup"><span data-stu-id="c4122-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4122-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="c4122-111">Remarks</span></span>  

 <span data-ttu-id="c4122-112">Если файл исходного кода содержит [оператор Option Explicit](../../language-reference/statements/option-explicit-statement.md), этот оператор переопределяет параметр компилятора командной строки `-optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="c4122-112">If the source code file contains an [Option Explicit statement](../../language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="c4122-113">Как задать параметр -optionexplicit в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c4122-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="c4122-114">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="c4122-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c4122-115">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c4122-115">On the **Project** menu, click **Properties**.</span></span>
  
2. <span data-ttu-id="c4122-116">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="c4122-116">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="c4122-117">Измените значение в поле **Option Explicit**.</span><span class="sxs-lookup"><span data-stu-id="c4122-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4122-118">Пример</span><span class="sxs-lookup"><span data-stu-id="c4122-118">Example</span></span>  

 <span data-ttu-id="c4122-119">Следующий код компилируется, когда используется параметр `-optionexplicit-`.</span><span class="sxs-lookup"><span data-stu-id="c4122-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="c4122-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c4122-120">See also</span></span>

- [<span data-ttu-id="c4122-121">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="c4122-121">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="c4122-122">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="c4122-122">-optioncompare</span></span>](optioncompare.md)
- [<span data-ttu-id="c4122-123">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="c4122-123">-optionstrict</span></span>](optionstrict.md)
- [<span data-ttu-id="c4122-124">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="c4122-124">-optioninfer</span></span>](optioninfer.md)
- [<span data-ttu-id="c4122-125">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="c4122-125">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="c4122-126">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="c4122-126">Option Explicit Statement</span></span>](../../language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="c4122-127">Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"</span><span class="sxs-lookup"><span data-stu-id="c4122-127">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
