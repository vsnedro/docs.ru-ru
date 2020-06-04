---
title: '#Директива Region'
ms.date: 07/20/2015
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
ms.openlocfilehash: cd53a6079c1564a8c73a0a1a6273fc166d18d3e6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409948"
---
# <a name="region-directive"></a><span data-ttu-id="dad96-102">Директива #Region</span><span class="sxs-lookup"><span data-stu-id="dad96-102">#Region Directive</span></span>

<span data-ttu-id="dad96-103">Сворачивает и скрывает разделы кода в файлах Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="dad96-103">Collapses and hides sections of code in Visual Basic files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dad96-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dad96-104">Syntax</span></span>  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a><span data-ttu-id="dad96-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="dad96-105">Parts</span></span>  
  
|<span data-ttu-id="dad96-106">Термин</span><span class="sxs-lookup"><span data-stu-id="dad96-106">Term</span></span>|<span data-ttu-id="dad96-107">Определение</span><span class="sxs-lookup"><span data-stu-id="dad96-107">Definition</span></span>|  
|---|---|  
|`identifier_string`|<span data-ttu-id="dad96-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="dad96-108">Required.</span></span> <span data-ttu-id="dad96-109">Строка, которая выступает в качестве заголовка области, если он свернут.</span><span class="sxs-lookup"><span data-stu-id="dad96-109">String that acts as the title of a region when it is collapsed.</span></span> <span data-ttu-id="dad96-110">По умолчанию области свернуты.</span><span class="sxs-lookup"><span data-stu-id="dad96-110">Regions are collapsed by default.</span></span>|  
|`#End Region`|<span data-ttu-id="dad96-111">Завершает блок `#Region`.</span><span class="sxs-lookup"><span data-stu-id="dad96-111">Terminates the `#Region` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dad96-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="dad96-112">Remarks</span></span>  

 <span data-ttu-id="dad96-113">Используйте директиву `#Region`, чтобы указать блок кода, который можно разворачивать и сворачивать с помощью функции структурирования в редакторе кода Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dad96-113">Use the `#Region` directive to specify a block of code to expand or collapse when using the outlining feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="dad96-114">Вы можете разместить или *вложить*области внутри других регионов, чтобы сгруппировать похожие регионы.</span><span class="sxs-lookup"><span data-stu-id="dad96-114">You can place, or *nest*, regions within other regions to group similar regions together.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dad96-115">Пример</span><span class="sxs-lookup"><span data-stu-id="dad96-115">Example</span></span>  

 <span data-ttu-id="dad96-116">В этом примере используется директива `#Region`.</span><span class="sxs-lookup"><span data-stu-id="dad96-116">This example uses the `#Region` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="dad96-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dad96-117">See also</span></span>

- [<span data-ttu-id="dad96-118">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="dad96-118">#If...Then...#Else Directives</span></span>](if-then-else-directives.md)
- [<span data-ttu-id="dad96-119">Структура</span><span class="sxs-lookup"><span data-stu-id="dad96-119">Outlining</span></span>](/visualstudio/ide/outlining)
- [<span data-ttu-id="dad96-120">Практическое руководство. Сворачивание и скрытие частей кода</span><span class="sxs-lookup"><span data-stu-id="dad96-120">How to: Collapse and Hide Sections of Code</span></span>](../../programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
