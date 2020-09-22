---
title: Оператор For Each для типа <typename> неоднозначен, поскольку тип реализует несколько экземпляров System.Collections.Generic.IEnumerable (Of T)
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: d04a77291ecf09f88ad189667540e9e353246f28
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874080"
---
# <a name="for-each-on-type-typename-is-ambiguous-because-the-type-implements-multiple-instantiations-of-systemcollectionsgenericienumerableof-t"></a><span data-ttu-id="6de3a-102">Оператор For Each для типа \<typename> неоднозначен, поскольку тип реализует несколько экземпляров System.Collections.Generic.IEnumerable (Of T)</span><span class="sxs-lookup"><span data-stu-id="6de3a-102">'For Each' on type '\<typename>' is ambiguous because the type implements multiple instantiations of 'System.Collections.Generic.IEnumerable(Of T)'</span></span>

<span data-ttu-id="6de3a-103">`For Each`Оператор указывает переменную-итератор, имеющую более одного <xref:System.Collections.IEnumerable.GetEnumerator%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="6de3a-103">A `For Each` statement specifies an iterator variable that has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span>  
  
 <span data-ttu-id="6de3a-104">Переменная итератора должна иметь тип, реализующий <xref:System.Collections.IEnumerable?displayProperty=nameWithType> <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> интерфейс или в одном из `Collections` пространств имен .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6de3a-104">The iterator variable must be of a type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface in one of the `Collections` namespaces of the .NET Framework.</span></span> <span data-ttu-id="6de3a-105">Класс может реализовывать несколько сконструированных универсальных интерфейсов, используя разные аргументы типа для каждой конструкции.</span><span class="sxs-lookup"><span data-stu-id="6de3a-105">It is possible for a class to implement more than one constructed generic interface, using a different type argument for each construction.</span></span> <span data-ttu-id="6de3a-106">Если класс, который выполняет это, используется для переменной-итератора, эта переменная имеет более одного <xref:System.Collections.IEnumerable.GetEnumerator%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="6de3a-106">If a class that does this is used for the iterator variable, that variable has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="6de3a-107">В этом случае Visual Basic не может выбрать метод для вызова.</span><span class="sxs-lookup"><span data-stu-id="6de3a-107">In such a case, Visual Basic cannot choose which method to call.</span></span>  
  
 <span data-ttu-id="6de3a-108">**Идентификатор ошибки:** BC32096</span><span class="sxs-lookup"><span data-stu-id="6de3a-108">**Error ID:** BC32096</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6de3a-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6de3a-109">To correct this error</span></span>  
  
- <span data-ttu-id="6de3a-110">Используйте [Оператор DirectCast](../operators/directcast-operator.md) или [Оператор TryCast](../operators/trycast-operator.md) для приведения типа переменной итератора к интерфейсу, определяющему <xref:System.Collections.IEnumerable.GetEnumerator%2A> метод, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="6de3a-110">Use [DirectCast Operator](../operators/directcast-operator.md) or [TryCast Operator](../operators/trycast-operator.md) to cast the iterator variable type to the interface defining the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6de3a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="6de3a-111">See also</span></span>

- [<span data-ttu-id="6de3a-112">Оператор For Each…Next</span><span class="sxs-lookup"><span data-stu-id="6de3a-112">For Each...Next Statement</span></span>](../statements/for-each-next-statement.md)
- [<span data-ttu-id="6de3a-113">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="6de3a-113">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
