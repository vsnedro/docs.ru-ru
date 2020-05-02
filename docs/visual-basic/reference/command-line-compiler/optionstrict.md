---
title: -optionstrict
ms.date: 07/20/2015
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
ms.openlocfilehash: 469e22aef9d746fc55e04ba884d17d60d8baa85a
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583073"
---
# <a name="-optionstrict"></a><span data-ttu-id="7d009-102">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="7d009-102">-optionstrict</span></span>

<span data-ttu-id="7d009-103">Применяет строгую семантику типа, чтобы ограничить неявные преобразования типов.</span><span class="sxs-lookup"><span data-stu-id="7d009-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>

## <a name="syntax"></a><span data-ttu-id="7d009-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d009-104">Syntax</span></span>

```console
-optionstrict[+ | -]
-optionstrict[:custom]
```

## <a name="arguments"></a><span data-ttu-id="7d009-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="7d009-105">Arguments</span></span>

<span data-ttu-id="7d009-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="7d009-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="7d009-107">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7d009-107">Optional.</span></span> <span data-ttu-id="7d009-108">Параметр `-optionstrict+` ограничивает неявное преобразование типов.</span><span class="sxs-lookup"><span data-stu-id="7d009-108">The `-optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="7d009-109">Значение этого параметра по умолчанию равно `-optionstrict-`.</span><span class="sxs-lookup"><span data-stu-id="7d009-109">The default for this option is `-optionstrict-`.</span></span> <span data-ttu-id="7d009-110">Параметр `-optionstrict+` совпадает с `-optionstrict`.</span><span class="sxs-lookup"><span data-stu-id="7d009-110">The `-optionstrict+` option is the same as `-optionstrict`.</span></span> <span data-ttu-id="7d009-111">Для нестрогой семантики типов можно использовать и тот, и другой.</span><span class="sxs-lookup"><span data-stu-id="7d009-111">You can use both for permissive type semantics.</span></span>

`custom`  
<span data-ttu-id="7d009-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="7d009-112">Required.</span></span> <span data-ttu-id="7d009-113">Предупреждать, когда не накладывается ограничение на строгую семантику языка.</span><span class="sxs-lookup"><span data-stu-id="7d009-113">Warn when strict language semantics are not respected.</span></span>

## <a name="remarks"></a><span data-ttu-id="7d009-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="7d009-114">Remarks</span></span>

<span data-ttu-id="7d009-115">Если применяется `-optionstrict+`, только расширяющие преобразования типов могут быть выполнены неявно.</span><span class="sxs-lookup"><span data-stu-id="7d009-115">When `-optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="7d009-116">Неявные сужающие преобразования типов, такие как назначение объекта типа `Decimal` объекту целочисленного типа, регистрируются как ошибки.</span><span class="sxs-lookup"><span data-stu-id="7d009-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>

<span data-ttu-id="7d009-117">Чтобы создать предупреждения для неявных сужающих преобразований типов, используйте `-optionstrict:custom`.</span><span class="sxs-lookup"><span data-stu-id="7d009-117">To generate warnings for implicit narrowing type conversions, use `-optionstrict:custom`.</span></span> <span data-ttu-id="7d009-118">Используйте `-nowarn:numberlist`, чтобы пропускать определенные предупреждения, и `-warnaserror:numberlist`, чтобы обрабатывать определенные предупреждения как ошибки.</span><span class="sxs-lookup"><span data-stu-id="7d009-118">Use `-nowarn:numberlist` to ignore particular warnings and `-warnaserror:numberlist` to treat particular warnings as errors.</span></span>

### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="7d009-119">Порядок задания параметра -optionstrict в среде Visual Studio IDE</span><span class="sxs-lookup"><span data-stu-id="7d009-119">To set -optionstrict in the Visual Studio IDE</span></span>

1. <span data-ttu-id="7d009-120">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="7d009-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="7d009-121">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7d009-121">On the **Project** menu, click **Properties.**</span></span>

2. <span data-ttu-id="7d009-122">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="7d009-122">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="7d009-123">Измените значение в поле **Option Strict**.</span><span class="sxs-lookup"><span data-stu-id="7d009-123">Modify the value in the **Option Strict** box.</span></span>

### <a name="to-set--optionstrict-programmatically"></a><span data-ttu-id="7d009-124">Порядок задания параметра -optionstrict программным образом</span><span class="sxs-lookup"><span data-stu-id="7d009-124">To set -optionstrict programmatically</span></span>

<span data-ttu-id="7d009-125">См. раздел [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7d009-125">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="7d009-126">Пример</span><span class="sxs-lookup"><span data-stu-id="7d009-126">Example</span></span>

<span data-ttu-id="7d009-127">Следующий код компилирует `Test.vb` с использованием строгой семантики типов.</span><span class="sxs-lookup"><span data-stu-id="7d009-127">The following code compiles `Test.vb` using strict type semantics.</span></span>

```console
vbc -optionstrict+ test.vb
```

## <a name="see-also"></a><span data-ttu-id="7d009-128">См. также</span><span class="sxs-lookup"><span data-stu-id="7d009-128">See also</span></span>

- [<span data-ttu-id="7d009-129">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="7d009-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="7d009-130">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="7d009-130">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="7d009-131">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="7d009-131">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="7d009-132">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="7d009-132">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="7d009-133">-nowarn</span><span class="sxs-lookup"><span data-stu-id="7d009-133">-nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [<span data-ttu-id="7d009-134">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d009-134">-warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [<span data-ttu-id="7d009-135">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="7d009-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="7d009-136">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="7d009-136">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="7d009-137">Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"</span><span class="sxs-lookup"><span data-stu-id="7d009-137">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
