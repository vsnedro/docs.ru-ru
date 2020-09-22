---
title: Оператор Mid
ms.date: 07/20/2015
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
ms.openlocfilehash: 0379a6cabe819365b22994a5e4f9353d98b2c768
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873196"
---
# <a name="mid-statement"></a><span data-ttu-id="a2105-102">Оператор Mid</span><span class="sxs-lookup"><span data-stu-id="a2105-102">Mid Statement</span></span>

<span data-ttu-id="a2105-103">Заменяет указанное число символов в `String` переменной символами из другой строки.</span><span class="sxs-lookup"><span data-stu-id="a2105-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2105-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2105-104">Syntax</span></span>  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="a2105-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="a2105-105">Parts</span></span>  

 `Target`  
 <span data-ttu-id="a2105-106">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a2105-106">Required.</span></span> <span data-ttu-id="a2105-107">Имя переменной, `String` которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="a2105-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="a2105-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="a2105-108">Required.</span></span> <span data-ttu-id="a2105-109">Выражение `Integer`.</span><span class="sxs-lookup"><span data-stu-id="a2105-109">`Integer` expression.</span></span> <span data-ttu-id="a2105-110">Место в символах `Target` , с которого начинается замена текста.</span><span class="sxs-lookup"><span data-stu-id="a2105-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="a2105-111">`Start` использует индекс, отсчитываемый от единицы.</span><span class="sxs-lookup"><span data-stu-id="a2105-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="a2105-112">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a2105-112">Optional.</span></span> <span data-ttu-id="a2105-113">Выражение `Integer`.</span><span class="sxs-lookup"><span data-stu-id="a2105-113">`Integer` expression.</span></span> <span data-ttu-id="a2105-114">Число символов для замены.</span><span class="sxs-lookup"><span data-stu-id="a2105-114">Number of characters to replace.</span></span> <span data-ttu-id="a2105-115">Если этот параметр опущен, `String` используются все.</span><span class="sxs-lookup"><span data-stu-id="a2105-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="a2105-116">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a2105-116">Required.</span></span> <span data-ttu-id="a2105-117">`String` выражение, которое заменяет часть `Target` .</span><span class="sxs-lookup"><span data-stu-id="a2105-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="a2105-118">Исключения</span><span class="sxs-lookup"><span data-stu-id="a2105-118">Exceptions</span></span>  
  
|<span data-ttu-id="a2105-119">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="a2105-119">Exception type</span></span>|<span data-ttu-id="a2105-120">Условие</span><span class="sxs-lookup"><span data-stu-id="a2105-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="a2105-121">`Start` <= 0 или `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="a2105-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2105-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="a2105-122">Remarks</span></span>  

 <span data-ttu-id="a2105-123">Число заменяемых символов всегда меньше или равно числу символов в `Target` .</span><span class="sxs-lookup"><span data-stu-id="a2105-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="a2105-124">Visual Basic содержит <xref:Microsoft.VisualBasic.Strings.Mid%2A> функцию и `Mid` оператор.</span><span class="sxs-lookup"><span data-stu-id="a2105-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="a2105-125">Эти элементы работают с указанным числом символов в строке, но `Mid` функция возвращает символы, пока `Mid` оператор заменяет символы.</span><span class="sxs-lookup"><span data-stu-id="a2105-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="a2105-126">Для получения дополнительной информации см. <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="a2105-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a2105-127">`MidB`Инструкция более ранних версий Visual Basic заменяет подстроку в байтах, а не на символы.</span><span class="sxs-lookup"><span data-stu-id="a2105-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="a2105-128">Он используется в основном для преобразования строк в приложениях с двухбайтовой кодировкой (DBCS).</span><span class="sxs-lookup"><span data-stu-id="a2105-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="a2105-129">Все строки Visual Basic в Юникоде и больше не `MidB` поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="a2105-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2105-130">Пример</span><span class="sxs-lookup"><span data-stu-id="a2105-130">Example</span></span>  

 <span data-ttu-id="a2105-131">В этом примере используется `Mid` оператор для замены указанного числа символов в строковой переменной символами из другой строки.</span><span class="sxs-lookup"><span data-stu-id="a2105-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="a2105-132">Требования</span><span class="sxs-lookup"><span data-stu-id="a2105-132">Requirements</span></span>  

 <span data-ttu-id="a2105-133">**Пространство имен:** [Microsoft. VisualBasic](../runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="a2105-133">**Namespace:** [Microsoft.VisualBasic](../runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="a2105-134">**Модуль:**`Strings`</span><span class="sxs-lookup"><span data-stu-id="a2105-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="a2105-135">**Сборка:** Библиотека времени выполнения Visual Basic (в Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="a2105-135">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2105-136">См. также</span><span class="sxs-lookup"><span data-stu-id="a2105-136">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="a2105-137">Строки</span><span class="sxs-lookup"><span data-stu-id="a2105-137">Strings</span></span>](../../programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="a2105-138">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a2105-138">Introduction to Strings in Visual Basic</span></span>](../../programming-guide/language-features/strings/introduction-to-strings.md)
