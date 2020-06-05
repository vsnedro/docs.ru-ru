---
title: Константа должна быть величиной внутреннего или перечислимого типа, а не классом, структурой, параметром типа или массивом
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: 9e36b84252c3d8762308e95323b8e284977df8c0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409768"
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a><span data-ttu-id="251ea-102">Константа должна быть величиной внутреннего или перечислимого типа, а не классом, структурой, параметром типа или массивом</span><span class="sxs-lookup"><span data-stu-id="251ea-102">Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type</span></span>
<span data-ttu-id="251ea-103">Предпринята попытка объявить константу как класс, структуру или тип массива или как параметр типа, определенный содержащим универсальным типом.</span><span class="sxs-lookup"><span data-stu-id="251ea-103">You have attempted to declare a constant as a class, structure, or array type, or as a type parameter defined by a containing generic type.</span></span>  
  
 <span data-ttu-id="251ea-104">Константы должны иметь встроенный тип ( `Boolean` , `Byte` ,, `Date` , `Decimal` `Double` , `Integer` , `Long` ,,,,,,, `Object` `SByte` `Short` `Single` `String` `UInteger` `ULong` или `UShort` ) или тип, `Enum` основанный на одном из целочисленных типов.</span><span class="sxs-lookup"><span data-stu-id="251ea-104">Constants must be of an intrinsic type (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, or `UShort`), or an `Enum` type based on one of the integral types.</span></span>  
  
 <span data-ttu-id="251ea-105">**Идентификатор ошибки:** BC30424</span><span class="sxs-lookup"><span data-stu-id="251ea-105">**Error ID:** BC30424</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="251ea-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="251ea-106">To correct this error</span></span>  
  
1. <span data-ttu-id="251ea-107">Объявите константу как внутренний или `Enum` тип.</span><span class="sxs-lookup"><span data-stu-id="251ea-107">Declare the constant as an intrinsic or `Enum` type.</span></span>  
  
2. <span data-ttu-id="251ea-108">Константа также может быть специальным значением, таким как `True` , `False` или `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="251ea-108">A constant can also be a special value such as `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="251ea-109">Компилятор считает эти предопределенные значения соответствующим внутренним типом.</span><span class="sxs-lookup"><span data-stu-id="251ea-109">The compiler considers these predefined values to be of the appropriate intrinsic type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="251ea-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="251ea-110">See also</span></span>

- [<span data-ttu-id="251ea-111">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="251ea-111">Constants and Enumerations</span></span>](../constants-and-enumerations.md)
- [<span data-ttu-id="251ea-112">Типы данных</span><span class="sxs-lookup"><span data-stu-id="251ea-112">Data Types</span></span>](../../programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="251ea-113">Типы данных</span><span class="sxs-lookup"><span data-stu-id="251ea-113">Data Types</span></span>](../data-types/index.md)
