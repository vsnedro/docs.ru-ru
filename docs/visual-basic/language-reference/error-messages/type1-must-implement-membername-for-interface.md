---
title: <type1>Тип <typename> должен реализовать <membername> для интерфейса <interfacename>
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 4ffe18e11c388a8c69ef0592bde1b78f5b219680
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386858"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a><span data-ttu-id="f325f-102">\<type1>Тип \<typename> должен реализовать \<membername> для интерфейса \<interfacename></span><span class="sxs-lookup"><span data-stu-id="f325f-102">\<type1>'\<typename>' must implement '\<membername>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="f325f-103">" \<typename> " должен реализовывать " \<membername> " для интерфейса " \<interfacename> ".</span><span class="sxs-lookup"><span data-stu-id="f325f-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="f325f-104">Реализация свойства должна иметь соответствующие описатели "ReadOnly"/"WriteOnly".</span><span class="sxs-lookup"><span data-stu-id="f325f-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="f325f-105">Класс или структура объявляет о необходимости реализации интерфейса, но не реализует процедуру, свойство или событие, определенные интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="f325f-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="f325f-106">Каждый член интерфейса должен быть реализован.</span><span class="sxs-lookup"><span data-stu-id="f325f-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="f325f-107">**Идентификатор ошибки:** BC30154</span><span class="sxs-lookup"><span data-stu-id="f325f-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f325f-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="f325f-108">To correct this error</span></span>  
  
1. <span data-ttu-id="f325f-109">Объявите член с таким же именем и сигнатурой, как определено в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="f325f-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="f325f-110">Обязательно включите по крайней мере `End Function` оператор, `End Sub` или `End Property` .</span><span class="sxs-lookup"><span data-stu-id="f325f-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2. <span data-ttu-id="f325f-111">Добавьте `Implements` предложение в конец `Function` оператора,, `Sub` `Property` или `Event` .</span><span class="sxs-lookup"><span data-stu-id="f325f-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="f325f-112">Пример:</span><span class="sxs-lookup"><span data-stu-id="f325f-112">For example:</span></span>  
  
    ```vb  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. <span data-ttu-id="f325f-113">При реализации свойства убедитесь, что `ReadOnly` или используется так `WriteOnly` же, как и в определении интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f325f-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4. <span data-ttu-id="f325f-114">При реализации свойства, объявите `Get` и `Set` процедуры, если это уместно.</span><span class="sxs-lookup"><span data-stu-id="f325f-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f325f-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f325f-115">See also</span></span>

- [<span data-ttu-id="f325f-116">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="f325f-116">Implements Statement</span></span>](../statements/implements-statement.md)
- [<span data-ttu-id="f325f-117">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="f325f-117">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
