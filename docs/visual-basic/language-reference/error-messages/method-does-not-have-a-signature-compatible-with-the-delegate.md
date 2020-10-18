---
title: Метод не имеет подписи, совместимой с делегатом
ms.date: 07/20/2015
f1_keywords:
- bc36563
- vbc36563
helpviewer_keywords:
- BC36563
ms.assetid: 3ca8b873-e98d-419b-95f2-d75bd2a9eb6c
ms.openlocfilehash: 62801552a39d29983c322e9a95a0494f155a2633
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160422"
---
# <a name="bc36563-method-does-not-have-a-signature-compatible-with-the-delegate"></a><span data-ttu-id="fe10e-102">BC36563: метод не имеет сигнатуры, совместимой с делегатом</span><span class="sxs-lookup"><span data-stu-id="fe10e-102">BC36563: Method does not have a signature compatible with the delegate</span></span>

<span data-ttu-id="fe10e-103">Существует несовместимость между сигнатурами метода и делегата, который вы пытаетесь использовать.</span><span class="sxs-lookup"><span data-stu-id="fe10e-103">There is an incompatibility between the signatures of the method and the delegate you are trying to use.</span></span> <span data-ttu-id="fe10e-104">Типы параметров и значений, возвращаемых классом делегата, определяются оператором `Delegate` .</span><span class="sxs-lookup"><span data-stu-id="fe10e-104">The `Delegate` statement defines the parameter types and return types of a delegate class.</span></span> <span data-ttu-id="fe10e-105">Для создания экземпляра этого типа делегата можно использовать любую процедуру, которая имеет соответствующие параметры совместимых типов и возвращаемых типов.</span><span class="sxs-lookup"><span data-stu-id="fe10e-105">Any procedure that has matching parameters of compatible types and return types can be used to create an instance of this delegate type.</span></span>

 <span data-ttu-id="fe10e-106">**Идентификатор ошибки:** BC36563</span><span class="sxs-lookup"><span data-stu-id="fe10e-106">**Error ID:** BC36563</span></span>

## <a name="see-also"></a><span data-ttu-id="fe10e-107">См. также</span><span class="sxs-lookup"><span data-stu-id="fe10e-107">See also</span></span>

- [<span data-ttu-id="fe10e-108">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="fe10e-108">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="fe10e-109">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="fe10e-109">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="fe10e-110">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="fe10e-110">Overload Resolution</span></span>](../../programming-guide/language-features/procedures/overload-resolution.md)
- [<span data-ttu-id="fe10e-111">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fe10e-111">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
