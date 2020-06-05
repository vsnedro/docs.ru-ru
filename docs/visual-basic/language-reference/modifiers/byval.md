---
title: ByVal
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: c4cdafafa6bae3246c0512e28f94fde7e88d230b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373028"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="32eaa-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32eaa-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="32eaa-103">Указывает, что аргумент передается [по значению](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), поэтому вызываемая процедура или свойство не может изменить значение переменной, которая является базовым аргументом в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="32eaa-103">Specifies that an argument is passed [by value](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), so that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span> <span data-ttu-id="32eaa-104">Если модификатор не указан, по умолчанию используется значение ByVal.</span><span class="sxs-lookup"><span data-stu-id="32eaa-104">If no modifier is specified, ByVal is the default.</span></span>

> [!NOTE]
> <span data-ttu-id="32eaa-105">Поскольку это значение по умолчанию, нет необходимости явно указывать `ByVal` ключевое слово в сигнатурах метода.</span><span class="sxs-lookup"><span data-stu-id="32eaa-105">Because it is the default, you do not have to explicitly specify the `ByVal` keyword in method signatures.</span></span> <span data-ttu-id="32eaa-106">Он, как правило, создает шум и часто ведет к нестандартному `ByRef` ключевому слову.</span><span class="sxs-lookup"><span data-stu-id="32eaa-106">It tends to produce noisy code and often leads to the non-default `ByRef` keyword being overlooked.</span></span>

## <a name="remarks"></a><span data-ttu-id="32eaa-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="32eaa-107">Remarks</span></span>
 <span data-ttu-id="32eaa-108">Модификатор `ByVal` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="32eaa-108">The `ByVal` modifier can be used in these contexts:</span></span>

 [<span data-ttu-id="32eaa-109">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="32eaa-109">Declare Statement</span></span>](../statements/declare-statement.md)

 [<span data-ttu-id="32eaa-110">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="32eaa-110">Function Statement</span></span>](../statements/function-statement.md)
  
 [<span data-ttu-id="32eaa-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="32eaa-111">Operator Statement</span></span>](../statements/operator-statement.md)
  
 [<span data-ttu-id="32eaa-112">Property Statement</span><span class="sxs-lookup"><span data-stu-id="32eaa-112">Property Statement</span></span>](../statements/property-statement.md)
  
 [<span data-ttu-id="32eaa-113">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="32eaa-113">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="example"></a><span data-ttu-id="32eaa-114">Пример</span><span class="sxs-lookup"><span data-stu-id="32eaa-114">Example</span></span>
 <span data-ttu-id="32eaa-115">В следующем примере демонстрируется использование `ByVal` механизма передачи параметров с аргументом ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="32eaa-115">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="32eaa-116">В примере аргумент — это `c1` экземпляр класса `Class1` .</span><span class="sxs-lookup"><span data-stu-id="32eaa-116">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="32eaa-117">`ByVal`запрещает коду в процедурах изменять базовое значение ссылочного аргумента, `c1` , но не защищает доступные поля и свойства `c1` .</span><span class="sxs-lookup"><span data-stu-id="32eaa-117">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a><span data-ttu-id="32eaa-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="32eaa-118">See also</span></span>

- [<span data-ttu-id="32eaa-119">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="32eaa-119">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="32eaa-120">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="32eaa-120">Passing Arguments by Value and by Reference</span></span>](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
