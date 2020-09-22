---
title: Аргументы типа не могут быть выведены от делегата
ms.date: 07/20/2015
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords:
- BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
ms.openlocfilehash: 51b0bbf2e346acdd84a1bc2283db4a71adc9f7dc
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870425"
---
# <a name="type-arguments-could-not-be-inferred-from-the-delegate"></a><span data-ttu-id="6d344-102">Аргументы типа не могут быть выведены от делегата</span><span class="sxs-lookup"><span data-stu-id="6d344-102">Type arguments could not be inferred from the delegate</span></span>

<span data-ttu-id="6d344-103">Оператор назначения использует `AddressOf` для назначения делегату адреса универсальной процедуры, но он не предоставляет универсальной процедуре никакие аргументы типа.</span><span class="sxs-lookup"><span data-stu-id="6d344-103">An assignment statement uses `AddressOf` to assign the address of a generic procedure to a delegate, but it does not supply any type arguments to the generic procedure.</span></span>  
  
 <span data-ttu-id="6d344-104">Как правило, при вызове универсального типа указывается аргумент типа для каждого параметра типа, определяемого этим универсальным типом.</span><span class="sxs-lookup"><span data-stu-id="6d344-104">Normally, when you invoke a generic type, you supply a type argument for each type parameter that the generic type defines.</span></span> <span data-ttu-id="6d344-105">Если вы не предоставляете никакие аргументы типов, компилятор пытается вывести типы, которые должны быть переданы в параметры типов.</span><span class="sxs-lookup"><span data-stu-id="6d344-105">If you do not supply any type arguments, the compiler attempts to infer the types to be passed to the type parameters.</span></span> <span data-ttu-id="6d344-106">Если контекст не предоставляет достаточно сведений, чтобы компилятор мог вывести типы, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="6d344-106">If the context does not provide enough information for the compiler to infer the types, an error is generated.</span></span>  
  
 <span data-ttu-id="6d344-107">**Идентификатор ошибки:** BC36564</span><span class="sxs-lookup"><span data-stu-id="6d344-107">**Error ID:** BC36564</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6d344-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6d344-108">To correct this error</span></span>  
  
- <span data-ttu-id="6d344-109">Укажите аргументы типа для универсальной процедуры в выражении `AddressOf` .</span><span class="sxs-lookup"><span data-stu-id="6d344-109">Specify the type arguments for the generic procedure in the `AddressOf` expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d344-110">См. также</span><span class="sxs-lookup"><span data-stu-id="6d344-110">See also</span></span>

- [<span data-ttu-id="6d344-111">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6d344-111">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="6d344-112">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="6d344-112">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="6d344-113">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6d344-113">Generic Procedures in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-procedures.md)
- [<span data-ttu-id="6d344-114">Type List</span><span class="sxs-lookup"><span data-stu-id="6d344-114">Type List</span></span>](../statements/type-list.md)
- [<span data-ttu-id="6d344-115">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="6d344-115">Extension Methods</span></span>](../../programming-guide/language-features/procedures/extension-methods.md)
