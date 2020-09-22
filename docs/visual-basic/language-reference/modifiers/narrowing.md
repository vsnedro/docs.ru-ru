---
title: Narrowing
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: 77515357ac9dc972992df09c471695aad13985c4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867932"
---
# <a name="narrowing-visual-basic"></a><span data-ttu-id="4361b-102">Narrowing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4361b-102">Narrowing (Visual Basic)</span></span>

<span data-ttu-id="4361b-103">Указывает, что оператор преобразования ( `CType` ) преобразует класс или структуру в тип, который не может содержать некоторые из возможных значений исходного класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="4361b-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that might not be able to hold some of the possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-narrowing-keyword"></a><span data-ttu-id="4361b-104">Преобразование с помощью ключевого слова "Narrow"</span><span class="sxs-lookup"><span data-stu-id="4361b-104">Converting with the Narrowing Keyword</span></span>  

 <span data-ttu-id="4361b-105">Процедура преобразования должна указываться `Public Shared` в дополнение к `Narrowing` .</span><span class="sxs-lookup"><span data-stu-id="4361b-105">The conversion procedure must specify `Public Shared` in addition to `Narrowing`.</span></span>  
  
 <span data-ttu-id="4361b-106">Сужающие преобразования не всегда выполняются успешно во время выполнения и могут привести к сбою или потери данных.</span><span class="sxs-lookup"><span data-stu-id="4361b-106">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="4361b-107">Примерами `Long` являются `Integer` , `String` to `Date` и базовый тип для производного типа.</span><span class="sxs-lookup"><span data-stu-id="4361b-107">Examples are `Long` to `Integer`, `String` to `Date`, and a base type to a derived type.</span></span> <span data-ttu-id="4361b-108">Последнее преобразование является сужением, так как базовый тип может не содержать все члены производного типа и поэтому не является экземпляром производного типа.</span><span class="sxs-lookup"><span data-stu-id="4361b-108">This last conversion is narrowing because the base type might not contain all the members of the derived type and thus is not an instance of the derived type.</span></span>  
  
 <span data-ttu-id="4361b-109">Если `Option Strict` имеет значение `On` , то `CType` для всех сужающих преобразований код должен использовать.</span><span class="sxs-lookup"><span data-stu-id="4361b-109">If `Option Strict` is `On`, the consuming code must use `CType` for all narrowing conversions.</span></span>  
  
 <span data-ttu-id="4361b-110">`Narrowing`Ключевое слово можно использовать в следующем контексте:</span><span class="sxs-lookup"><span data-stu-id="4361b-110">The `Narrowing` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="4361b-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="4361b-111">Operator Statement</span></span>](../statements/operator-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="4361b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4361b-112">See also</span></span>

- [<span data-ttu-id="4361b-113">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="4361b-113">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="4361b-114">Widening</span><span class="sxs-lookup"><span data-stu-id="4361b-114">Widening</span></span>](widening.md)
- [<span data-ttu-id="4361b-115">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="4361b-115">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="4361b-116">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="4361b-116">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="4361b-117">CType Function</span><span class="sxs-lookup"><span data-stu-id="4361b-117">CType Function</span></span>](../functions/ctype-function.md)
- [<span data-ttu-id="4361b-118">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="4361b-118">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
