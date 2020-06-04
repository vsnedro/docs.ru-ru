---
title: Первый оператор этого Sub New должен быть вызовом MyBase.New или MyClass.New (Нет доступного конструктора без параметров)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: 2b9d2568fb64e4af72733ad1f3dee58aaee650e5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402983"
---
# <a name="first-statement-of-this-sub-new-must-be-a-call-to-mybasenew-or-myclassnew-no-accessible-constructor-without-parameters"></a><span data-ttu-id="79e1c-102">Первый оператор этого Sub New должен быть вызовом MyBase.New или MyClass.New (Нет доступного конструктора без параметров)</span><span class="sxs-lookup"><span data-stu-id="79e1c-102">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' (No Accessible Constructor Without Parameters)</span></span>
<span data-ttu-id="79e1c-103">Первый оператор в "подnew" должен быть вызовом "MyBase. New" или "MyClass. New", так как базовый класс " \<basename> " из " \<derivedname> " не имеет доступного "подnew", который может быть вызван без аргументов.</span><span class="sxs-lookup"><span data-stu-id="79e1c-103">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' because base class '\<basename>' of '\<derivedname>' does not have an accessible 'Sub New' that can be called with no arguments.</span></span>  
  
 <span data-ttu-id="79e1c-104">В производном классе каждый конструктор должен вызывать конструктор базового класса ( `MyBase.New` ).</span><span class="sxs-lookup"><span data-stu-id="79e1c-104">In a derived class, every constructor must call a base class constructor (`MyBase.New`).</span></span> <span data-ttu-id="79e1c-105">Если базовый класс содержит конструктор без параметров, доступный для производных классов, то `MyBase.New` может вызываться автоматически.</span><span class="sxs-lookup"><span data-stu-id="79e1c-105">If the base class has a constructor with no parameters that is accessible to derived classes, `MyBase.New` can be called automatically.</span></span> <span data-ttu-id="79e1c-106">В противном случае конструктор базового класса должен вызываться с параметрами, и это не может быть сделано автоматически.</span><span class="sxs-lookup"><span data-stu-id="79e1c-106">If not, a base class constructor must be called with parameters, and this cannot be done automatically.</span></span> <span data-ttu-id="79e1c-107">В этом случае первый оператор каждого конструктора производного класса должен вызвать параметризованный конструктор для базового класса или вызвать другой конструктор в производном классе, который выполняет вызов конструктора базового класса.</span><span class="sxs-lookup"><span data-stu-id="79e1c-107">In this case, the first statement of every derived class constructor must call a parameterized constructor on the base class, or call another constructor in the derived class that makes a base class constructor call.</span></span>  
  
 <span data-ttu-id="79e1c-108">**Идентификатор ошибки:** BC30148</span><span class="sxs-lookup"><span data-stu-id="79e1c-108">**Error ID:** BC30148</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="79e1c-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="79e1c-109">To correct this error</span></span>  
  
- <span data-ttu-id="79e1c-110">Либо вызов `MyBase.New` предоставляет необходимые параметры, либо вызывает одноранговый конструктор, который выполняет такой вызов.</span><span class="sxs-lookup"><span data-stu-id="79e1c-110">Either call `MyBase.New` supplying the required parameters, or call a peer constructor that makes such a call.</span></span>  
  
     <span data-ttu-id="79e1c-111">Например, если базовый класс имеет конструктор, объявленный как `Public Sub New(ByVal index as Integer)` , то первым оператором в конструкторе производного класса может быть `MyBase.New(100)` .</span><span class="sxs-lookup"><span data-stu-id="79e1c-111">For example, if the base class has a constructor that’s declared as `Public Sub New(ByVal index as Integer)`, the first statement in the derived class constructor might be `MyBase.New(100)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79e1c-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="79e1c-112">See also</span></span>

- [<span data-ttu-id="79e1c-113">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="79e1c-113">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
