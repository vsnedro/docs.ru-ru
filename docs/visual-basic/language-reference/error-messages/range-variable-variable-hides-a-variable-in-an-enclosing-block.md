---
title: Переменная диапазона <variable> скрывает переменную во включающем блоке, ранее определенную переменную диапазона или неявно объявленную переменную в выражении запроса
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: 90fed3dd27f18fe87c326cc36dfb774822fc4b21
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162353"
---
# <a name="bc36633-range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a><span data-ttu-id="a75b7-102">BC36633: переменная диапазона \<variable> скрывает переменную во внешнем блоке, ранее определенную переменную диапазона или неявно объявленную переменную в выражении запроса</span><span class="sxs-lookup"><span data-stu-id="a75b7-102">BC36633: Range variable \<variable> hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression</span></span>

<span data-ttu-id="a75b7-103">Имя переменной диапазона, указанное в `Select` `From` `Aggregate` предложении,, или, `Let` дублирует имя переменной диапазона, уже указанное ранее в запросе, или имя переменной, неявно объявленной в запросе, например имя поля или имя агрегатной функции.</span><span class="sxs-lookup"><span data-stu-id="a75b7-103">A range variable name specified in a `Select`, `From`, `Aggregate`, or `Let` clause duplicates the name of a range variable already specified previously in the query, or the name of a variable that is implicitly declared by the query, such as a field name or the name of an aggregate function.</span></span>

 <span data-ttu-id="a75b7-104">**Идентификатор ошибки:** BC36633</span><span class="sxs-lookup"><span data-stu-id="a75b7-104">**Error ID:** BC36633</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="a75b7-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="a75b7-105">To correct this error</span></span>

- <span data-ttu-id="a75b7-106">Убедитесь, что все переменные диапазона в определенной области запроса имеют уникальные имена.</span><span class="sxs-lookup"><span data-stu-id="a75b7-106">Ensure that all range variables in a particular query scope have unique names.</span></span> <span data-ttu-id="a75b7-107">Запрос можно заключить в круглые скобки, чтобы убедиться, что вложенные запросы имеют уникальную область.</span><span class="sxs-lookup"><span data-stu-id="a75b7-107">You can enclose a query in parentheses to ensure that nested queries have a unique scope.</span></span>

## <a name="see-also"></a><span data-ttu-id="a75b7-108">См. также</span><span class="sxs-lookup"><span data-stu-id="a75b7-108">See also</span></span>

- <span data-ttu-id="a75b7-109">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a75b7-109">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="a75b7-110">Предложение FROM</span><span class="sxs-lookup"><span data-stu-id="a75b7-110">From Clause</span></span>](../queries/from-clause.md)
- [<span data-ttu-id="a75b7-111">Предложение Let</span><span class="sxs-lookup"><span data-stu-id="a75b7-111">Let Clause</span></span>](../queries/let-clause.md)
- [<span data-ttu-id="a75b7-112">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="a75b7-112">Aggregate Clause</span></span>](../queries/aggregate-clause.md)
- [<span data-ttu-id="a75b7-113">Предложение SELECT</span><span class="sxs-lookup"><span data-stu-id="a75b7-113">Select Clause</span></span>](../queries/select-clause.md)
