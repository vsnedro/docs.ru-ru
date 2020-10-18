---
title: Ожидается объявление
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: 2755f5afcb96ca7a6c4d140908649390dd66d571
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162704"
---
# <a name="bc30188-declaration-expected"></a><span data-ttu-id="1e79f-102">BC30188: ожидается объявление</span><span class="sxs-lookup"><span data-stu-id="1e79f-102">BC30188: Declaration expected</span></span>

<span data-ttu-id="1e79f-103">Недекларативный оператор, такой как оператор присваивания или цикла, происходит вне любой процедуры.</span><span class="sxs-lookup"><span data-stu-id="1e79f-103">A nondeclarative statement, such as an assignment or loop statement, occurs outside any procedure.</span></span> <span data-ttu-id="1e79f-104">За пределами процедур разрешены только объявления.</span><span class="sxs-lookup"><span data-stu-id="1e79f-104">Only declarations are allowed outside procedures.</span></span>

 <span data-ttu-id="1e79f-105">Кроме того, программный элемент объявляется без ключевого слова объявления, такого как `Dim` или `Const` .</span><span class="sxs-lookup"><span data-stu-id="1e79f-105">Alternatively, a programming element is declared without a declaration keyword such as `Dim` or `Const`.</span></span>

 <span data-ttu-id="1e79f-106">**Идентификатор ошибки:** BC30188</span><span class="sxs-lookup"><span data-stu-id="1e79f-106">**Error ID:** BC30188</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="1e79f-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="1e79f-107">To correct this error</span></span>

- <span data-ttu-id="1e79f-108">Переместите недекларативный оператор в тело процедуры.</span><span class="sxs-lookup"><span data-stu-id="1e79f-108">Move the nondeclarative statement to the body of a procedure.</span></span>

- <span data-ttu-id="1e79f-109">Начните объявление с помощью соответствующего ключевого слова объявления.</span><span class="sxs-lookup"><span data-stu-id="1e79f-109">Begin the declaration with an appropriate declaration keyword.</span></span>

- <span data-ttu-id="1e79f-110">Убедитесь, что ключевое слово объявления написано неправильно.</span><span class="sxs-lookup"><span data-stu-id="1e79f-110">Ensure that a declaration keyword is not misspelled.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e79f-111">См. также</span><span class="sxs-lookup"><span data-stu-id="1e79f-111">See also</span></span>

- [<span data-ttu-id="1e79f-112">Процедуры</span><span class="sxs-lookup"><span data-stu-id="1e79f-112">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="1e79f-113">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="1e79f-113">Dim Statement</span></span>](../statements/dim-statement.md)
