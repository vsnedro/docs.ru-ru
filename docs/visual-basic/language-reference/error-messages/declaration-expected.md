---
title: Ожидается объявление
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: ee8f1f9ec26dc6c938f0b412dfe30832e3cfe165
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874530"
---
# <a name="declaration-expected"></a><span data-ttu-id="402f8-102">Ожидается объявление</span><span class="sxs-lookup"><span data-stu-id="402f8-102">Declaration expected</span></span>

<span data-ttu-id="402f8-103">Недекларативный оператор, такой как оператор присваивания или цикла, происходит вне любой процедуры.</span><span class="sxs-lookup"><span data-stu-id="402f8-103">A nondeclarative statement, such as an assignment or loop statement, occurs outside any procedure.</span></span> <span data-ttu-id="402f8-104">За пределами процедур разрешены только объявления.</span><span class="sxs-lookup"><span data-stu-id="402f8-104">Only declarations are allowed outside procedures.</span></span>  
  
 <span data-ttu-id="402f8-105">Кроме того, программный элемент объявляется без ключевого слова объявления, такого как `Dim` или `Const` .</span><span class="sxs-lookup"><span data-stu-id="402f8-105">Alternatively, a programming element is declared without a declaration keyword such as `Dim` or `Const`.</span></span>  
  
 <span data-ttu-id="402f8-106">**Идентификатор ошибки:** BC30188</span><span class="sxs-lookup"><span data-stu-id="402f8-106">**Error ID:** BC30188</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="402f8-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="402f8-107">To correct this error</span></span>  
  
- <span data-ttu-id="402f8-108">Переместите недекларативный оператор в тело процедуры.</span><span class="sxs-lookup"><span data-stu-id="402f8-108">Move the nondeclarative statement to the body of a procedure.</span></span>  
  
- <span data-ttu-id="402f8-109">Начните объявление с помощью соответствующего ключевого слова объявления.</span><span class="sxs-lookup"><span data-stu-id="402f8-109">Begin the declaration with an appropriate declaration keyword.</span></span>  
  
- <span data-ttu-id="402f8-110">Убедитесь, что ключевое слово объявления написано неправильно.</span><span class="sxs-lookup"><span data-stu-id="402f8-110">Ensure that a declaration keyword is not misspelled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="402f8-111">См. также</span><span class="sxs-lookup"><span data-stu-id="402f8-111">See also</span></span>

- [<span data-ttu-id="402f8-112">Процедуры</span><span class="sxs-lookup"><span data-stu-id="402f8-112">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="402f8-113">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="402f8-113">Dim Statement</span></span>](../statements/dim-statement.md)
