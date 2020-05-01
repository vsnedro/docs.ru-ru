---
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
ms.openlocfilehash: 7f14ce07a2928f4dbffd3aa57f8cdd514b75694c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716712"
---
# <a name="-netcf"></a><span data-ttu-id="23018-102">-netcf</span><span class="sxs-lookup"><span data-stu-id="23018-102">-netcf</span></span>

<span data-ttu-id="23018-103">Задает для компилятора нацеливание на .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="23018-103">Sets the compiler to target the .NET Compact Framework.</span></span>

## <a name="syntax"></a><span data-ttu-id="23018-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="23018-104">Syntax</span></span>

```console
-netcf
```

## <a name="remarks"></a><span data-ttu-id="23018-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="23018-105">Remarks</span></span>

<span data-ttu-id="23018-106">Параметр `-netcf` указывает компилятору Visual Basic, что нужно нацеливать сборку на .NET Compact Framework вместо полной версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="23018-106">The `-netcf` option causes the Visual Basic compiler to target the .NET Compact Framework rather than the full .NET Framework.</span></span> <span data-ttu-id="23018-107">Все функции языка, которые присутствуют только в полной версии .NET Framework, при этом отключаются.</span><span class="sxs-lookup"><span data-stu-id="23018-107">Language functionality that is present only in the full .NET Framework is disabled.</span></span>

<span data-ttu-id="23018-108">Параметр `-netcf` предназначен для использования с [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span><span class="sxs-lookup"><span data-stu-id="23018-108">The `-netcf` option is designed to be used with [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="23018-109">Параметр `-netcf` позволяет отключить те же функции языка, которые отсутствуют в файлах с нацеливанием на `-sdkpath`.</span><span class="sxs-lookup"><span data-stu-id="23018-109">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>

> [!NOTE]
> <span data-ttu-id="23018-110">Параметр `-netcf` недоступен в среде разработки Visual Studio. Он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="23018-110">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="23018-111">Параметр `-netcf` задается, когда загружается проект устройства Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="23018-111">The `-netcf` option is set when a Visual Basic device project is loaded.</span></span>

<span data-ttu-id="23018-112">Параметр `-netcf` изменяет следующие функции языка:</span><span class="sxs-lookup"><span data-stu-id="23018-112">The `-netcf` option changes the following language features:</span></span>

- <span data-ttu-id="23018-113">Блокируется ключевое слово [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md), которое завершает выполнение программы.</span><span class="sxs-lookup"><span data-stu-id="23018-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="23018-114">Следующая программа будет успешно скомпилирована и выполнена без `-netcf`, но возвратит ошибку во время компиляции с параметром `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="23018-114">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- <span data-ttu-id="23018-115">Блокируется позднее связывание во всех его проявлениях.</span><span class="sxs-lookup"><span data-stu-id="23018-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="23018-116">При обнаружении любых сценариев позднего связывания создаются ошибки времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="23018-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="23018-117">Следующая программа будет успешно скомпилирована и выполнена без `-netcf`, но возвратит ошибку во время компиляции с параметром `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="23018-117">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- <span data-ttu-id="23018-118">Блокируются модификаторы [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md) и [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md).</span><span class="sxs-lookup"><span data-stu-id="23018-118">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="23018-119">Синтаксис [инструкции Declare](../../../visual-basic/language-reference/statements/declare-statement.md) изменяется на `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span><span class="sxs-lookup"><span data-stu-id="23018-119">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="23018-120">В следующем коде показано влияние параметра `-netcf` на процесс компиляции.</span><span class="sxs-lookup"><span data-stu-id="23018-120">The following code shows the effect of `-netcf` on a compilation.</span></span>

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- <span data-ttu-id="23018-121">Использование ключевых слов Visual Basic 6.0, которые были удалены из Visual Basic, приводит к созданию другой ошибки, если используется параметр `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="23018-121">Using Visual Basic 6.0 keywords that were removed from Visual Basic generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="23018-122">Это влияет на сообщения об ошибках для следующих ключевых слов:</span><span class="sxs-lookup"><span data-stu-id="23018-122">This affects the error messages for the following keywords:</span></span>

  - `Open`

  - `Close`

  - `Put`

  - `Print`

  - `Write`

  - `Input`

  - `Lock`

  - `Unlock`

  - `Seek`

  - `Width`

  - `Name`

  - `FreeFile`

  - `EOF`

  - `Loc`

  - `LOF`

  - `Line`

## <a name="example"></a><span data-ttu-id="23018-123">Пример</span><span class="sxs-lookup"><span data-stu-id="23018-123">Example</span></span>

<span data-ttu-id="23018-124">В следующем примере кода выполняется компиляция `Myfile.vb` в .NET Compact Framework с использованием версий библиотек mscorlib.dll и Microsoft.VisualBasic.dll, которые находятся в каталоге установки .NET Compact Framework по умолчанию на диске C.</span><span class="sxs-lookup"><span data-stu-id="23018-124">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="23018-125">Как правило, следует использовать самую последнюю версию .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="23018-125">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a><span data-ttu-id="23018-126">См. также</span><span class="sxs-lookup"><span data-stu-id="23018-126">See also</span></span>

- [<span data-ttu-id="23018-127">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="23018-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="23018-128">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="23018-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="23018-129">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="23018-129">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
