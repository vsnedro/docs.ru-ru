---
title: Слишком длинный идентификатор
ms.date: 07/20/2015
f1_keywords:
- bc30033
- vbc30033
helpviewer_keywords:
- BC30033
ms.assetid: 3d07f6d0-9a2f-49ca-94e8-1e354932e855
ms.openlocfilehash: eafcb2fdf706e12fa606a442ad577c88ed5a7427
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162860"
---
# <a name="bc30033-identifier-is-too-long"></a><span data-ttu-id="d936a-102">BC30033: слишком длинный идентификатор</span><span class="sxs-lookup"><span data-stu-id="d936a-102">BC30033: Identifier is too long</span></span>

<span data-ttu-id="d936a-103">Имя или идентификатор каждого элемента программирования ограничено 1023 символами.</span><span class="sxs-lookup"><span data-stu-id="d936a-103">The name, or identifier, of every programming element is limited to 1023 characters.</span></span> <span data-ttu-id="d936a-104">Кроме того, полное имя не может содержать более 1023 символов.</span><span class="sxs-lookup"><span data-stu-id="d936a-104">In addition, a fully qualified name cannot exceed 1023 characters.</span></span> <span data-ttu-id="d936a-105">Это означает, что длина строки идентификатора ( `<namespace>.<...>.<namespace>.<class>.<element>` ) не может превышать 1023 символов, включая символы оператора доступа к членам ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="d936a-105">This means that the entire identifier string (`<namespace>.<...>.<namespace>.<class>.<element>`) cannot be more than 1023 characters long, including the member-access operator (`.`) characters.</span></span>

 <span data-ttu-id="d936a-106">**Идентификатор ошибки:** BC30033</span><span class="sxs-lookup"><span data-stu-id="d936a-106">**Error ID:** BC30033</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d936a-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d936a-107">To correct this error</span></span>

- <span data-ttu-id="d936a-108">Уменьшите длину идентификатора.</span><span class="sxs-lookup"><span data-stu-id="d936a-108">Reduce the length of the identifier.</span></span>

## <a name="see-also"></a><span data-ttu-id="d936a-109">См. также</span><span class="sxs-lookup"><span data-stu-id="d936a-109">See also</span></span>

- [<span data-ttu-id="d936a-110">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="d936a-110">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
