---
title: Оператор Option Explicit
ms.date: 07/20/2015
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
helpviewer_keywords:
- declaring variables [Visual Basic], explicit
- forced variable declaration in Option Explicit statement [Visual Basic]
- Explicit keyword
- explicit variable declaration
- Option Explicit statement [Visual Basic]
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
ms.openlocfilehash: 44bf8205ec071710ee3660968ab3c3e9af33f74d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874936"
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="caf29-102">Оператор Option Explicit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="caf29-102">Option Explicit Statement (Visual Basic)</span></span>

<span data-ttu-id="caf29-103">Заставляет явно объявлять все переменные в файле или допускает неявные объявления переменных.</span><span class="sxs-lookup"><span data-stu-id="caf29-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caf29-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="caf29-104">Syntax</span></span>  
  
```vb  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="caf29-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="caf29-105">Parts</span></span>  

 `On`  
 <span data-ttu-id="caf29-106">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="caf29-106">Optional.</span></span> <span data-ttu-id="caf29-107">Включает `Option Explicit` проверку.</span><span class="sxs-lookup"><span data-stu-id="caf29-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="caf29-108">Если параметр `On` или `Off` не указан, по умолчанию используется значение `On` .</span><span class="sxs-lookup"><span data-stu-id="caf29-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="caf29-109">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="caf29-109">Optional.</span></span> <span data-ttu-id="caf29-110">Отключает `Option Explicit` проверку.</span><span class="sxs-lookup"><span data-stu-id="caf29-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="caf29-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="caf29-111">Remarks</span></span>  

 <span data-ttu-id="caf29-112">Если `Option Explicit On` или `Option Explicit` присутствует в файле, необходимо явно объявить все переменные с помощью `Dim` `ReDim` инструкций или.</span><span class="sxs-lookup"><span data-stu-id="caf29-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="caf29-113">При попытке использовать необъявленное имя переменной во время компиляции возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="caf29-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="caf29-114">`Option Explicit Off`Оператор допускает неявное объявление переменных.</span><span class="sxs-lookup"><span data-stu-id="caf29-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="caf29-115">Если используется оператор `Option Explicit`, он должен быть указан в файле до всех прочих операторов.</span><span class="sxs-lookup"><span data-stu-id="caf29-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="caf29-116">Установка `Option Explicit` в `Off` обычно не является хорошей практикой.</span><span class="sxs-lookup"><span data-stu-id="caf29-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="caf29-117">Вы можете допустить ошибку при вводе имени переменной в одном или нескольких местах, что приведет к непредвиденным результатам при выполнении программы.</span><span class="sxs-lookup"><span data-stu-id="caf29-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="caf29-118">Если отсутствует оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="caf29-118">When an Option Explicit Statement Is Not Present</span></span>  

 <span data-ttu-id="caf29-119">Если исходный код не содержит `Option Explicit` инструкцию, то используется **параметр Explicit** на [странице Компиляция, конструктор проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) .</span><span class="sxs-lookup"><span data-stu-id="caf29-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="caf29-120">Если используется компилятор командной строки, используется параметр компилятора [-оптионексплиЦит](../../reference/command-line-compiler/optionexplicit.md) .</span><span class="sxs-lookup"><span data-stu-id="caf29-120">If the command-line compiler is used, the [-optionexplicit](../../reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="caf29-121">Установка параметра Explicit в интегрированной среде разработки</span><span class="sxs-lookup"><span data-stu-id="caf29-121">To set Option Explicit in the IDE</span></span>  
  
1. <span data-ttu-id="caf29-122">В **Обозреватель решений**выберите проект.</span><span class="sxs-lookup"><span data-stu-id="caf29-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="caf29-123">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="caf29-123">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="caf29-124">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="caf29-124">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="caf29-125">Задайте значение в **явном поле Option** .</span><span class="sxs-lookup"><span data-stu-id="caf29-125">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="caf29-126">При создании нового проекта параметр **Option Explicit** на вкладке **Компиляция** имеет значение **Option Explicit** в диалоговом окне Параметры **VB по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="caf29-126">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="caf29-127">Чтобы открыть диалоговое окно **настройки VB по умолчанию** , в меню **Сервис** выберите пункт **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="caf29-127">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="caf29-128">В диалоговом окне **Параметры** разверните узел **Проекты и решения** и выберите пункт **Параметры Visual Basic по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="caf29-128">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="caf29-129">Начальным значением по умолчанию в **VB по умолчанию** является `On` .</span><span class="sxs-lookup"><span data-stu-id="caf29-129">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="caf29-130">Установка параметра Explicit в командной строке</span><span class="sxs-lookup"><span data-stu-id="caf29-130">To set Option Explicit on the command line</span></span>  
  
- <span data-ttu-id="caf29-131">Включите параметр компилятора [-оптионексплиЦит](../../reference/command-line-compiler/optionexplicit.md) в команду **vbc** .</span><span class="sxs-lookup"><span data-stu-id="caf29-131">Include the [-optionexplicit](../../reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="caf29-132">Пример</span><span class="sxs-lookup"><span data-stu-id="caf29-132">Example</span></span>  

 <span data-ttu-id="caf29-133">В следующем примере оператор используется `Option Explicit` для принудительного явного объявления всех переменных.</span><span class="sxs-lookup"><span data-stu-id="caf29-133">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="caf29-134">Попытка использовать необъявленную переменную вызывает ошибку во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="caf29-134">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a><span data-ttu-id="caf29-135">См. также</span><span class="sxs-lookup"><span data-stu-id="caf29-135">See also</span></span>

- [<span data-ttu-id="caf29-136">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="caf29-136">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="caf29-137">Оператор reDim</span><span class="sxs-lookup"><span data-stu-id="caf29-137">ReDim Statement</span></span>](redim-statement.md)
- [<span data-ttu-id="caf29-138">Оператор Option Compare</span><span class="sxs-lookup"><span data-stu-id="caf29-138">Option Compare Statement</span></span>](option-compare-statement.md)
- [<span data-ttu-id="caf29-139">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="caf29-139">Option Strict Statement</span></span>](option-strict-statement.md)
- [<span data-ttu-id="caf29-140">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="caf29-140">-optioncompare</span></span>](../../reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="caf29-141">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="caf29-141">-optionexplicit</span></span>](../../reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="caf29-142">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="caf29-142">-optionstrict</span></span>](../../reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="caf29-143">Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"</span><span class="sxs-lookup"><span data-stu-id="caf29-143">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
