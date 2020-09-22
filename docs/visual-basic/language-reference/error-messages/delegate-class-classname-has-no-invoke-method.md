---
title: В делегируемом классе <classname> отсутствует метод Invoke, поэтому выражение этого типа не может быть вызвано посредством метода
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: e6ad06262806088347c94b3040b743618a3b3695
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874500"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="ad9ba-102">В делегируемом классе \<classname> отсутствует метод Invoke, поэтому выражение этого типа не может быть вызвано посредством метода</span><span class="sxs-lookup"><span data-stu-id="ad9ba-102">Delegate class '\<classname>' has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>

<span data-ttu-id="ad9ba-103">Вызов `Invoke` через делегат завершился неудачей, поскольку `Invoke` не реализован в классе делегата.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="ad9ba-104">**Идентификатор ошибки:** BC30220</span><span class="sxs-lookup"><span data-stu-id="ad9ba-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ad9ba-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ad9ba-105">To correct this error</span></span>  
  
1. <span data-ttu-id="ad9ba-106">Убедитесь, что экземпляр класса делегата был создан с помощью `Dim` оператора и что процедура была назначена экземпляру делегата с помощью `AddressOf` оператора.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2. <span data-ttu-id="ad9ba-107">Выберите код, реализующий класс делегата, и убедитесь, что он реализует `Invoke` процедуру.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad9ba-108">См. также</span><span class="sxs-lookup"><span data-stu-id="ad9ba-108">See also</span></span>

- [<span data-ttu-id="ad9ba-109">Делегаты</span><span class="sxs-lookup"><span data-stu-id="ad9ba-109">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="ad9ba-110">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="ad9ba-110">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="ad9ba-111">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="ad9ba-111">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="ad9ba-112">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="ad9ba-112">Dim Statement</span></span>](../statements/dim-statement.md)
