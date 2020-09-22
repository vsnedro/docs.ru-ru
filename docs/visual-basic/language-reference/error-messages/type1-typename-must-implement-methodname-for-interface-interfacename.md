---
title: <type1>Тип <typename> должен реализовать <methodname> для интерфейса <interfacename>
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 8bf8872277ec901e066a8b950aaf3e61babfcc48
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872103"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="764a3-102">\<type1>Тип \<typename> должен реализовать \<methodname> для интерфейса \<interfacename></span><span class="sxs-lookup"><span data-stu-id="764a3-102">\<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>

<span data-ttu-id="764a3-103">Класс или структура требует реализации интерфейса, но не реализует процедуру, определенную интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="764a3-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="764a3-104">Каждый член интерфейса должен быть реализован.</span><span class="sxs-lookup"><span data-stu-id="764a3-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="764a3-105">**Идентификатор ошибки:** BC30149</span><span class="sxs-lookup"><span data-stu-id="764a3-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="764a3-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="764a3-106">To correct this error</span></span>  
  
1. <span data-ttu-id="764a3-107">Объявите процедуру с тем же именем и сигнатурой, как определено в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="764a3-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="764a3-108">Обязательно включите по крайней мере `End Function` оператор или `End Sub` .</span><span class="sxs-lookup"><span data-stu-id="764a3-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="764a3-109">Добавьте `Implements` предложение в конец `Function` `Sub` оператора или.</span><span class="sxs-lookup"><span data-stu-id="764a3-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="764a3-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="764a3-110">For example:</span></span>  
  
    ```vb  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="764a3-111">См. также</span><span class="sxs-lookup"><span data-stu-id="764a3-111">See also</span></span>

- [<span data-ttu-id="764a3-112">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="764a3-112">Implements Statement</span></span>](../statements/implements-statement.md)
- [<span data-ttu-id="764a3-113">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="764a3-113">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
