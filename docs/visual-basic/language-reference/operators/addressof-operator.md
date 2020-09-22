---
title: Оператор AddressOf
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: edce7d4a2268bd311045ea4972672fe8fd2600ea
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874885"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="d541f-102">Оператор AddressOf (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d541f-102">AddressOf Operator (Visual Basic)</span></span>

<span data-ttu-id="d541f-103">Создает экземпляр делегата, который ссылается на определенную процедуру.</span><span class="sxs-lookup"><span data-stu-id="d541f-103">Creates a delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d541f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d541f-104">Syntax</span></span>  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="d541f-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="d541f-105">Parts</span></span>  

 `procedurename`  
 <span data-ttu-id="d541f-106">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d541f-106">Required.</span></span> <span data-ttu-id="d541f-107">Задает процедуру, на которую ссылается только что созданный делегат.</span><span class="sxs-lookup"><span data-stu-id="d541f-107">Specifies the procedure to be referenced by the newly created delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d541f-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="d541f-108">Remarks</span></span>  

 <span data-ttu-id="d541f-109">`AddressOf`Оператор создает делегат, указывающий на подпрограмму или функцию, заданную параметром `procedurename` .</span><span class="sxs-lookup"><span data-stu-id="d541f-109">The `AddressOf` operator creates a delegate that points to the sub or function specified by `procedurename`.</span></span> <span data-ttu-id="d541f-110">Если указанная процедура является методом экземпляра, то делегат ссылается на экземпляр и метод.</span><span class="sxs-lookup"><span data-stu-id="d541f-110">When the specified procedure is an instance method then the delegate refers to both the instance and the method.</span></span> <span data-ttu-id="d541f-111">Затем при вызове делегата вызывается указанный метод указанного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d541f-111">Then, when the  delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="d541f-112">`AddressOf`Оператор можно использовать в качестве операнда конструктора делегата или его можно использовать в контексте, в котором тип делегата может быть определен компилятором.</span><span class="sxs-lookup"><span data-stu-id="d541f-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d541f-113">Пример</span><span class="sxs-lookup"><span data-stu-id="d541f-113">Example</span></span>  

 <span data-ttu-id="d541f-114">В этом примере `AddressOf` оператор используется для обозначения делегата, обрабатывающего `Click` событие кнопки.</span><span class="sxs-lookup"><span data-stu-id="d541f-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="d541f-115">Пример</span><span class="sxs-lookup"><span data-stu-id="d541f-115">Example</span></span>  

 <span data-ttu-id="d541f-116">В следующем примере оператор используется `AddressOf` для назначения функции Startup для потока.</span><span class="sxs-lookup"><span data-stu-id="d541f-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="d541f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="d541f-117">See also</span></span>

- [<span data-ttu-id="d541f-118">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="d541f-118">Declare Statement</span></span>](../statements/declare-statement.md)
- [<span data-ttu-id="d541f-119">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="d541f-119">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="d541f-120">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="d541f-120">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="d541f-121">Делегаты</span><span class="sxs-lookup"><span data-stu-id="d541f-121">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
