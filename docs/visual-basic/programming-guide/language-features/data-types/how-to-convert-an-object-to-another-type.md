---
title: Практическое руководство. Преобразование объекта в другой тип
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: cdb78bc66867ce27076d7b7e42de6a2880cb3a8c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393965"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a><span data-ttu-id="84e8a-102">Практическое руководство. Преобразование объекта к другому типу в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="84e8a-102">How to: Convert an Object to Another Type in Visual Basic</span></span>
<span data-ttu-id="84e8a-103">Преобразование `Object` переменной в другой тип данных осуществляется с помощью ключевого слова преобразования, например [CType Function](../../../language-reference/functions/ctype-function.md).</span><span class="sxs-lookup"><span data-stu-id="84e8a-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../language-reference/functions/ctype-function.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="84e8a-104">Пример</span><span class="sxs-lookup"><span data-stu-id="84e8a-104">Example</span></span>  
 <span data-ttu-id="84e8a-105">В следующем примере переменная преобразуется `Object` в `Integer` и `String` .</span><span class="sxs-lookup"><span data-stu-id="84e8a-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span></span>  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 <span data-ttu-id="84e8a-106">Если известно, что содержимое `Object` переменной относится к определенному типу данных, лучше преобразовать переменную в этот тип данных.</span><span class="sxs-lookup"><span data-stu-id="84e8a-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span></span> <span data-ttu-id="84e8a-107">Если вы продолжаете использовать `Object` переменную, вы используете *упаковку* и *распаковку* (для типа значения) или *позднее связывание* (для ссылочного типа).</span><span class="sxs-lookup"><span data-stu-id="84e8a-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span></span> <span data-ttu-id="84e8a-108">Все эти операции занимают некоторое время и снижают производительность.</span><span class="sxs-lookup"><span data-stu-id="84e8a-108">These operations all take extra execution time and make your performance slower.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="84e8a-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="84e8a-109">Compile the code</span></span>  
 <span data-ttu-id="84e8a-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="84e8a-110">This example requires:</span></span>  
  
- <span data-ttu-id="84e8a-111">ссылка на пространство имен <xref:System?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="84e8a-111">A reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84e8a-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="84e8a-112">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="84e8a-113">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="84e8a-113">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="84e8a-114">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="84e8a-114">Widening and Narrowing Conversions</span></span>](widening-and-narrowing-conversions.md)
- [<span data-ttu-id="84e8a-115">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="84e8a-115">Implicit and Explicit Conversions</span></span>](implicit-and-explicit-conversions.md)
- [<span data-ttu-id="84e8a-116">Преобразования значений между строковыми и другими типами</span><span class="sxs-lookup"><span data-stu-id="84e8a-116">Conversions Between Strings and Other Types</span></span>](conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="84e8a-117">Преобразования массивов</span><span class="sxs-lookup"><span data-stu-id="84e8a-117">Array Conversions</span></span>](array-conversions.md)
- [<span data-ttu-id="84e8a-118">Структуры</span><span class="sxs-lookup"><span data-stu-id="84e8a-118">Structures</span></span>](structures.md)
- [<span data-ttu-id="84e8a-119">Типы данных</span><span class="sxs-lookup"><span data-stu-id="84e8a-119">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="84e8a-120">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="84e8a-120">Type Conversion Functions</span></span>](../../../language-reference/functions/type-conversion-functions.md)
