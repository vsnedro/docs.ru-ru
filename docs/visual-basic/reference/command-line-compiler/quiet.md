---
title: -quiet
ms.date: 07/20/2015
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
ms.openlocfilehash: 6e773c60469e8426956c92a5aa377741ba5af4d3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005279"
---
# <a name="-quiet"></a><span data-ttu-id="93b62-102">-quiet</span><span class="sxs-lookup"><span data-stu-id="93b62-102">-quiet</span></span>

<span data-ttu-id="93b62-103">Запрещает компилятору показывать код синтаксических ошибок и предупреждений.</span><span class="sxs-lookup"><span data-stu-id="93b62-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>

## <a name="syntax"></a><span data-ttu-id="93b62-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93b62-104">Syntax</span></span>

```console
-quiet
```

## <a name="remarks"></a><span data-ttu-id="93b62-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="93b62-105">Remarks</span></span>

<span data-ttu-id="93b62-106">По умолчанию `-quiet` не действует.</span><span class="sxs-lookup"><span data-stu-id="93b62-106">By default, `-quiet` is not in effect.</span></span> <span data-ttu-id="93b62-107">Когда компилятор сообщает об ошибке или предупреждении, связанных с синтаксисом, он также выводит соответствующую строку из исходного кода.</span><span class="sxs-lookup"><span data-stu-id="93b62-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="93b62-108">Для приложений, анализирующих выходные данные компилятора, может быть удобнее, чтобы компилятор выводил только текстовую часть диагностической информации.</span><span class="sxs-lookup"><span data-stu-id="93b62-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>

<span data-ttu-id="93b62-109">В следующем примере `Module1` выводит ошибку, включающую в себя исходный код, при компиляции без `-quiet`.</span><span class="sxs-lookup"><span data-stu-id="93b62-109">In the following example, `Module1` outputs an error that includes source code when compiled without `-quiet`.</span></span>

```vb
Module Module1
    Sub Main()
        x()
    End Sub
End Module
```

<span data-ttu-id="93b62-110">Результат</span><span class="sxs-lookup"><span data-stu-id="93b62-110">Output:</span></span>

```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
```

<span data-ttu-id="93b62-111">При компиляции с `-quiet` компилятор выводит только следующие данные:</span><span class="sxs-lookup"><span data-stu-id="93b62-111">Compiled with `-quiet`, the compiler outputs only the following:</span></span>

```console
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> <span data-ttu-id="93b62-112">Параметр `-quiet` недоступен в среде разработки Visual Studio. Он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="93b62-112">The `-quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="93b62-113">Пример</span><span class="sxs-lookup"><span data-stu-id="93b62-113">Example</span></span>

<span data-ttu-id="93b62-114">Следующий код компилирует `T2.vb` и не отображает код для диагностической информации компилятора, связанной с синтаксисом:</span><span class="sxs-lookup"><span data-stu-id="93b62-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>

```console
vbc -quiet t2.vb
```

## <a name="see-also"></a><span data-ttu-id="93b62-115">См. также</span><span class="sxs-lookup"><span data-stu-id="93b62-115">See also</span></span>

- [<span data-ttu-id="93b62-116">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="93b62-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="93b62-117">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="93b62-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
