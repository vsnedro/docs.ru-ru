---
title: Выражение имеет тип <typename> который является ограниченным и не может использоваться для доступа к членам, унаследованным от Object или ValueType
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 3e19c0d71ee47ac61e9704f0fcd2637f01aa0896
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163055"
---
# <a name="bc31393-expression-has-the-type-typename-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-object-or-valuetype"></a><span data-ttu-id="5c053-102">BC31393: выражение имеет тип " \<typename> ", который является ограниченным типом и не может использоваться для доступа к членам, унаследованным от "Object" или "ValueType"</span><span class="sxs-lookup"><span data-stu-id="5c053-102">BC31393: Expression has the type '\<typename>' which is a restricted type and cannot be used to access members inherited from 'Object' or 'ValueType'</span></span>

<span data-ttu-id="5c053-103">Выражение принимает тип, который не может быть упакован средой CLR, но обращается к члену, для которого требуется упаковка-преобразование.</span><span class="sxs-lookup"><span data-stu-id="5c053-103">An expression evaluates to a type that cannot be boxed by the common language runtime (CLR) but accesses a member that requires boxing.</span></span>

 <span data-ttu-id="5c053-104">*Упаковкой-преобразованием* называется обработка, необходимая для преобразования типа в `Object` или, в некоторых случаях, в <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="5c053-104">*Boxing* refers to the processing necessary to convert a type to `Object` or, on occasion, to <xref:System.ValueType>.</span></span> <span data-ttu-id="5c053-105">Среда CLR не может быть Box для определенных типов структуры, например <xref:System.ArgIterator> , <xref:System.RuntimeArgumentHandle> и <xref:System.TypedReference> .</span><span class="sxs-lookup"><span data-stu-id="5c053-105">The common language runtime cannot box certain structure types, for example <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, and <xref:System.TypedReference>.</span></span>

 <span data-ttu-id="5c053-106">Это выражение пытается использовать ограниченный тип для вызова метода, унаследованного от <xref:System.Object> или <xref:System.ValueType> , например <xref:System.Object.GetHashCode%2A> или <xref:System.Object.ToString%2A> .</span><span class="sxs-lookup"><span data-stu-id="5c053-106">This expression attempts to use the restricted type to call a method inherited from <xref:System.Object> or <xref:System.ValueType>, such as <xref:System.Object.GetHashCode%2A> or <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="5c053-107">Для доступа к этому методу Visual Basic предпринималась попытка неявного преобразования упаковки, которое вызывает эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="5c053-107">To access this method, Visual Basic has attempted an implicit boxing conversion that causes this error.</span></span>

 <span data-ttu-id="5c053-108">**Идентификатор ошибки:** BC31393</span><span class="sxs-lookup"><span data-stu-id="5c053-108">**Error ID:** BC31393</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="5c053-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="5c053-109">To correct this error</span></span>

1. <span data-ttu-id="5c053-110">Найдите выражение, которое оценивается в указанный тип.</span><span class="sxs-lookup"><span data-stu-id="5c053-110">Locate the expression that evaluates to the cited type.</span></span>

2. <span data-ttu-id="5c053-111">Находит часть инструкции, которая пытается вызвать метод, наследуемый от <xref:System.Object> или <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="5c053-111">Locate the part of your statement that attempts to call the method inherited from <xref:System.Object> or <xref:System.ValueType>.</span></span>

3. <span data-ttu-id="5c053-112">Перепишите инструкцию, чтобы избежать вызова метода.</span><span class="sxs-lookup"><span data-stu-id="5c053-112">Rewrite the statement to avoid the method call.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c053-113">См. также</span><span class="sxs-lookup"><span data-stu-id="5c053-113">See also</span></span>

- [<span data-ttu-id="5c053-114">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="5c053-114">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
