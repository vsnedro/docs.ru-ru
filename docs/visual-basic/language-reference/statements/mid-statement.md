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
ms.openlocfilehash: 90408fd8a8cfc9b74c8422d0571d61f8534403f3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404459"
---
# <a name="mid-statement"></a><span data-ttu-id="12111-102">Оператор Mid</span><span class="sxs-lookup"><span data-stu-id="12111-102">Mid Statement</span></span>
<span data-ttu-id="12111-103">Заменяет указанное число символов в `String` переменной символами из другой строки.</span><span class="sxs-lookup"><span data-stu-id="12111-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12111-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12111-104">Syntax</span></span>  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="12111-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="12111-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="12111-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="12111-106">Required.</span></span> <span data-ttu-id="12111-107">Имя переменной, `String` которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="12111-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="12111-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="12111-108">Required.</span></span> <span data-ttu-id="12111-109">Выражение `Integer`.</span><span class="sxs-lookup"><span data-stu-id="12111-109">`Integer` expression.</span></span> <span data-ttu-id="12111-110">Место в символах `Target` , с которого начинается замена текста.</span><span class="sxs-lookup"><span data-stu-id="12111-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="12111-111">`Start`использует индекс, отсчитываемый от единицы.</span><span class="sxs-lookup"><span data-stu-id="12111-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="12111-112">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="12111-112">Optional.</span></span> <span data-ttu-id="12111-113">Выражение `Integer`.</span><span class="sxs-lookup"><span data-stu-id="12111-113">`Integer` expression.</span></span> <span data-ttu-id="12111-114">Число символов для замены.</span><span class="sxs-lookup"><span data-stu-id="12111-114">Number of characters to replace.</span></span> <span data-ttu-id="12111-115">Если этот параметр опущен, `String` используются все.</span><span class="sxs-lookup"><span data-stu-id="12111-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="12111-116">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="12111-116">Required.</span></span> <span data-ttu-id="12111-117">`String`выражение, которое заменяет часть `Target` .</span><span class="sxs-lookup"><span data-stu-id="12111-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="12111-118">Исключения</span><span class="sxs-lookup"><span data-stu-id="12111-118">Exceptions</span></span>  
  
|<span data-ttu-id="12111-119">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="12111-119">Exception type</span></span>|<span data-ttu-id="12111-120">Условие</span><span class="sxs-lookup"><span data-stu-id="12111-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="12111-121">`Start`<= 0 или `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="12111-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12111-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="12111-122">Remarks</span></span>  
 <span data-ttu-id="12111-123">Число заменяемых символов всегда меньше или равно числу символов в `Target` .</span><span class="sxs-lookup"><span data-stu-id="12111-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="12111-124">Visual Basic содержит <xref:Microsoft.VisualBasic.Strings.Mid%2A> функцию и `Mid` оператор.</span><span class="sxs-lookup"><span data-stu-id="12111-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="12111-125">Эти элементы работают с указанным числом символов в строке, но `Mid` функция возвращает символы, пока `Mid` оператор заменяет символы.</span><span class="sxs-lookup"><span data-stu-id="12111-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="12111-126">Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="12111-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="12111-127">`MidB`Инструкция более ранних версий Visual Basic заменяет подстроку в байтах, а не на символы.</span><span class="sxs-lookup"><span data-stu-id="12111-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="12111-128">Он используется в основном для преобразования строк в приложениях с двухбайтовой кодировкой (DBCS).</span><span class="sxs-lookup"><span data-stu-id="12111-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="12111-129">Все строки Visual Basic в Юникоде и больше не `MidB` поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="12111-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12111-130">Пример</span><span class="sxs-lookup"><span data-stu-id="12111-130">Example</span></span>  
 <span data-ttu-id="12111-131">В этом примере используется `Mid` оператор для замены указанного числа символов в строковой переменной символами из другой строки.</span><span class="sxs-lookup"><span data-stu-id="12111-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="12111-132">Требования</span><span class="sxs-lookup"><span data-stu-id="12111-132">Requirements</span></span>  
 <span data-ttu-id="12111-133">**Пространство имен:** [Microsoft. VisualBasic](../runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="12111-133">**Namespace:** [Microsoft.VisualBasic](../runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="12111-134">**Модуль:**`Strings`</span><span class="sxs-lookup"><span data-stu-id="12111-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="12111-135">**Сборка:** Библиотека времени выполнения Visual Basic (в Microsoft. VisualBasic. dll)</span><span class="sxs-lookup"><span data-stu-id="12111-135">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12111-136">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="12111-136">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="12111-137">Строки</span><span class="sxs-lookup"><span data-stu-id="12111-137">Strings</span></span>](../../programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="12111-138">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="12111-138">Introduction to Strings in Visual Basic</span></span>](../../programming-guide/language-features/strings/introduction-to-strings.md)
