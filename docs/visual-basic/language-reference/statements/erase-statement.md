---
title: Оператор Erase
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 33d88b5ce71ceab8d4b4b59d356c53a804c360be
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873288"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="d43e5-102">Оператор Erase (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d43e5-102">Erase Statement (Visual Basic)</span></span>

<span data-ttu-id="d43e5-103">Используется для высвобождения переменных массива и освобождения памяти, используемой для их элементов.</span><span class="sxs-lookup"><span data-stu-id="d43e5-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d43e5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d43e5-104">Syntax</span></span>  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="d43e5-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="d43e5-105">Parts</span></span>  

 `arraylist`  
 <span data-ttu-id="d43e5-106">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d43e5-106">Required.</span></span> <span data-ttu-id="d43e5-107">Список переменных массива для удаления.</span><span class="sxs-lookup"><span data-stu-id="d43e5-107">List of array variables to be erased.</span></span> <span data-ttu-id="d43e5-108">Переменные разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="d43e5-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d43e5-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="d43e5-109">Remarks</span></span>  

 <span data-ttu-id="d43e5-110">`Erase`Инструкция может использоваться только на уровне процедуры.</span><span class="sxs-lookup"><span data-stu-id="d43e5-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="d43e5-111">Это означает, что массивы можно освобождать внутри процедуры, но не на уровне класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="d43e5-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="d43e5-112">`Erase`Оператор эквивалентен присвоению `Nothing` каждой переменной массива.</span><span class="sxs-lookup"><span data-stu-id="d43e5-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d43e5-113">Пример</span><span class="sxs-lookup"><span data-stu-id="d43e5-113">Example</span></span>  

 <span data-ttu-id="d43e5-114">В следующем примере инструкция используется `Erase` для очистки двух массивов и освобождения памяти (1000 и 100, соответственно).</span><span class="sxs-lookup"><span data-stu-id="d43e5-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="d43e5-115">`ReDim`Затем оператор присваивает новый экземпляр массива трехмерному массиву.</span><span class="sxs-lookup"><span data-stu-id="d43e5-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="d43e5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d43e5-116">See also</span></span>

- [<span data-ttu-id="d43e5-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="d43e5-117">Nothing</span></span>](../nothing.md)
- [<span data-ttu-id="d43e5-118">Оператор reDim</span><span class="sxs-lookup"><span data-stu-id="d43e5-118">ReDim Statement</span></span>](redim-statement.md)
