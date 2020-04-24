---
title: 'Как: создание строк с помощью StringBuilder'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: c41db584df83782dab99b90043045aa2cabcb6ff
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645328"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="a0e6e-102">Как: создать строки с помощью StringBuilder в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a0e6e-102">How to: create strings using a StringBuilder in Visual Basic</span></span>

<span data-ttu-id="a0e6e-103">Этот пример строит длинную строку из <xref:System.Text.StringBuilder> многих меньших строк с помощью класса.</span><span class="sxs-lookup"><span data-stu-id="a0e6e-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="a0e6e-104">Класс <xref:System.Text.StringBuilder> более эффективен, `&=` чем оператор для свертывания многих строк.</span><span class="sxs-lookup"><span data-stu-id="a0e6e-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>

## <a name="example"></a><span data-ttu-id="a0e6e-105">Пример</span><span class="sxs-lookup"><span data-stu-id="a0e6e-105">Example</span></span>

<span data-ttu-id="a0e6e-106">Следующий пример создает экземпляр <xref:System.Text.StringBuilder> класса, привязывает к этому экземпляру 1000 строк, а затем возвращает его представление строки:</span><span class="sxs-lookup"><span data-stu-id="a0e6e-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation:</span></span>

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a><span data-ttu-id="a0e6e-107">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a0e6e-107">See also</span></span>

- [<span data-ttu-id="a0e6e-108">Использование класса StringBuilder</span><span class="sxs-lookup"><span data-stu-id="a0e6e-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="a0e6e-109">&оператор</span><span class="sxs-lookup"><span data-stu-id="a0e6e-109">&= Operator</span></span>](../../../language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="a0e6e-110">Строки</span><span class="sxs-lookup"><span data-stu-id="a0e6e-110">Strings</span></span>](index.md)
- [<span data-ttu-id="a0e6e-111">Создание строк</span><span class="sxs-lookup"><span data-stu-id="a0e6e-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="a0e6e-112">Операции со строками</span><span class="sxs-lookup"><span data-stu-id="a0e6e-112">Manipulating Strings</span></span>](../../../../standard/base-types/best-practices-strings.md)
