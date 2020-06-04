---
title: Практическое руководство. Сворачивание и скрытие частей кода
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: c11affe9c4dd4251ba8ff4b87029d314970b5fcb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404853"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="e3bda-102">Практическое руководство. Сворачивание и скрытие частей кода (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3bda-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>

<span data-ttu-id="e3bda-103">`#Region`Директива позволяет сворачивать и скрывать разделы кода в файлах Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e3bda-103">The `#Region` directive enables you to collapse and hide sections of code in Visual Basic files.</span></span> <span data-ttu-id="e3bda-104">`#Region`Директива позволяет указать блок кода, который можно развернуть или свернуть при использовании редактора кода Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e3bda-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the Visual Studio code editor.</span></span> <span data-ttu-id="e3bda-105">Возможность скрывать код выборочно делает файлы более управляемыми и удобочитаемыми.</span><span class="sxs-lookup"><span data-stu-id="e3bda-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="e3bda-106">Дополнительные сведения см. в разделе [Структура](/visualstudio/ide/outlining).</span><span class="sxs-lookup"><span data-stu-id="e3bda-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>

<span data-ttu-id="e3bda-107">`#Region`директивы поддерживают семантику блока кода, такую как `#If...#End If` .</span><span class="sxs-lookup"><span data-stu-id="e3bda-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="e3bda-108">Это означает, что они не могут начинаться в одном блоке и заканчиваться другим; Начало и конец должны находиться в одном блоке.</span><span class="sxs-lookup"><span data-stu-id="e3bda-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="e3bda-109">`#Region`директивы не поддерживаются в функциях.</span><span class="sxs-lookup"><span data-stu-id="e3bda-109">`#Region` directives are not supported within functions.</span></span>

## <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="e3bda-110">Сворачивание и скрытие раздела кода</span><span class="sxs-lookup"><span data-stu-id="e3bda-110">To collapse and hide a section of code</span></span>

<span data-ttu-id="e3bda-111">Поместите раздел кода между `#Region` `#End Region` операторами и, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e3bda-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>

[!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]

<span data-ttu-id="e3bda-112">Этот `#Region` блок можно использовать несколько раз в файле кода, поэтому пользователи могут определять собственные блоки процедур и классов, которые, в свою очередь, могут быть свернуты.</span><span class="sxs-lookup"><span data-stu-id="e3bda-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="e3bda-113">`#Region`блоки также могут быть вложены в другие `#Region` блоки.</span><span class="sxs-lookup"><span data-stu-id="e3bda-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>

> [!NOTE]
> <span data-ttu-id="e3bda-114">Скрытие кода не мешает его компиляции и не влияет на `#If...#End If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="e3bda-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3bda-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e3bda-115">See also</span></span>

- [<span data-ttu-id="e3bda-116">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="e3bda-116">Conditional Compilation</span></span>](conditional-compilation.md)
- [<span data-ttu-id="e3bda-117">Директива #Region</span><span class="sxs-lookup"><span data-stu-id="e3bda-117">#Region Directive</span></span>](../../language-reference/directives/region-directive.md)
- [<span data-ttu-id="e3bda-118">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="e3bda-118">#If...Then...#Else Directives</span></span>](../../language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="e3bda-119">Структура</span><span class="sxs-lookup"><span data-stu-id="e3bda-119">Outlining</span></span>](/visualstudio/ide/outlining)
