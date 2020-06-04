---
title: ReDim не может изменять размерность
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: b2404927c2faf30d1d058d2163fd5d67e1a52e1e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84358171"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a><span data-ttu-id="00875-102">ReDim не может изменять размерность</span><span class="sxs-lookup"><span data-stu-id="00875-102">'ReDim' cannot change the number of dimensions</span></span>
<span data-ttu-id="00875-103">Предпринята попытка использования оператора `ReDim` для изменения ранга (размерности) массива.</span><span class="sxs-lookup"><span data-stu-id="00875-103">An operation attempts to use the `ReDim` statement to change the rank (number of dimensions) of an array.</span></span> <span data-ttu-id="00875-104">Оператор`ReDim` может изменять размер одного или нескольких измерений массива, который уже был формально объявлен, но он не может изменить ранг массива.</span><span class="sxs-lookup"><span data-stu-id="00875-104">`ReDim` can change the size of one or more dimensions of an array that has already been formally declared, but it cannot change an array's rank.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="00875-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="00875-105">To correct this error</span></span>  
  
- <span data-ttu-id="00875-106">Убедитесь, что требуется изменить ранг, а не размеры массива, и по возможности используйте `Dim` для объявления нового массива с нужным рангом.</span><span class="sxs-lookup"><span data-stu-id="00875-106">Ensure that you intend to change the array's rank and not the sizes of its dimensions, and if possible, use `Dim` to declare a new array with the desired rank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00875-107">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="00875-107">See also</span></span>

- [<span data-ttu-id="00875-108">Массивы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="00875-108">Arrays in Visual Basic</span></span>](../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="00875-109">Размеры массива в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="00875-109">Array dimensions in Visual Basic</span></span>](../programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="00875-110">Оператор reDim</span><span class="sxs-lookup"><span data-stu-id="00875-110">ReDim Statement</span></span>](../language-reference/statements/redim-statement.md)
- [<span data-ttu-id="00875-111">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="00875-111">Dim Statement</span></span>](../language-reference/statements/dim-statement.md)
