---
title: -optioncompare
ms.date: 07/20/2015
f1_keywords:
- /optioncompare
- -optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
ms.openlocfilehash: ed9adc7cddd9eb204937b9819e4eeff176821e95
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400566"
---
# <a name="-optioncompare"></a><span data-ttu-id="e32bb-102">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="e32bb-102">-optioncompare</span></span>

<span data-ttu-id="e32bb-103">Задает способ сравнения строк.</span><span class="sxs-lookup"><span data-stu-id="e32bb-103">Specifies how string comparisons are made.</span></span>

## <a name="syntax"></a><span data-ttu-id="e32bb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e32bb-104">Syntax</span></span>

```console
-optioncompare:{binary | text}
```

## <a name="remarks"></a><span data-ttu-id="e32bb-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="e32bb-105">Remarks</span></span>

<span data-ttu-id="e32bb-106">Вы можете определить `-optioncompare` в одной из двух форм: `-optioncompare:binary`, чтобы использовать сравнения двоичных строк, и `-optioncompare:text`, чтобы использовать сравнения текстовых строк.</span><span class="sxs-lookup"><span data-stu-id="e32bb-106">You can specify `-optioncompare` in one of two forms: `-optioncompare:binary` to use binary string comparisons, and `-optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="e32bb-107">По умолчанию компилятор использует `-optioncompare:binary`.</span><span class="sxs-lookup"><span data-stu-id="e32bb-107">By default, the compiler uses `-optioncompare:binary`.</span></span>

<span data-ttu-id="e32bb-108">В Microsoft Windows текущая кодовая страница определяет порядок сортировки двоичных строк.</span><span class="sxs-lookup"><span data-stu-id="e32bb-108">In Microsoft Windows, the current code page determines the binary sort order.</span></span> <span data-ttu-id="e32bb-109">Типичный порядок сортировки двоичных строк выглядит так:</span><span class="sxs-lookup"><span data-stu-id="e32bb-109">A typical binary sort order is as follows:</span></span>

`A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

<span data-ttu-id="e32bb-110">Сравнение текстовых строк основано на порядке сортировки текста без учета регистра, что определяется языковым стандартом системы.</span><span class="sxs-lookup"><span data-stu-id="e32bb-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="e32bb-111">Типичный порядок сортировки текстовых строк выглядит так:</span><span class="sxs-lookup"><span data-stu-id="e32bb-111">A typical text sort order is as follows:</span></span>

`(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`

### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="e32bb-112">Чтобы определить параметр -optioncompare в среде Visual Studio IDE, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e32bb-112">To set -optioncompare in the Visual Studio IDE</span></span>

1. <span data-ttu-id="e32bb-113">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="e32bb-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e32bb-114">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e32bb-114">On the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="e32bb-115">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="e32bb-115">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="e32bb-116">Измените значение поля **Сравнение параметров**.</span><span class="sxs-lookup"><span data-stu-id="e32bb-116">Modify the value in the **Option Compare** box.</span></span>

### <a name="to-set--optioncompare-programmatically"></a><span data-ttu-id="e32bb-117">Чтобы определить параметр-optioncompare программными средствами, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e32bb-117">To set -optioncompare programmatically</span></span>

<span data-ttu-id="e32bb-118">См. сведения об [операторе Option Compare](../../language-reference/statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e32bb-118">See [Option Compare Statement](../../language-reference/statements/option-compare-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="e32bb-119">Пример</span><span class="sxs-lookup"><span data-stu-id="e32bb-119">Example</span></span>

<span data-ttu-id="e32bb-120">Следующий код компилирует `ProjFile.vb` и использует сравнение двоичных строк.</span><span class="sxs-lookup"><span data-stu-id="e32bb-120">The following code compiles `ProjFile.vb` and uses binary string comparisons.</span></span>

```console
vbc -optioncompare:binary projFile.vb
```

## <a name="see-also"></a><span data-ttu-id="e32bb-121">См. также</span><span class="sxs-lookup"><span data-stu-id="e32bb-121">See also</span></span>

- [<span data-ttu-id="e32bb-122">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="e32bb-122">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="e32bb-123">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="e32bb-123">-optionexplicit</span></span>](optionexplicit.md)
- [<span data-ttu-id="e32bb-124">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="e32bb-124">-optionstrict</span></span>](optionstrict.md)
- [<span data-ttu-id="e32bb-125">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="e32bb-125">-optioninfer</span></span>](optioninfer.md)
- [<span data-ttu-id="e32bb-126">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="e32bb-126">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="e32bb-127">Оператор Option Compare</span><span class="sxs-lookup"><span data-stu-id="e32bb-127">Option Compare Statement</span></span>](../../language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="e32bb-128">Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"</span><span class="sxs-lookup"><span data-stu-id="e32bb-128">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
