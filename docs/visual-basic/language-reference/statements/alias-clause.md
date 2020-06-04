---
title: Предложение Alias
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: c28e931a376b20b2058a7187551405cd9523d4fe
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408475"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="51c76-102">Предложение Alias (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51c76-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="51c76-103">Указывает, что у внешней процедуры есть другое имя в своей библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="51c76-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51c76-104">Комментарии</span><span class="sxs-lookup"><span data-stu-id="51c76-104">Remarks</span></span>  
 <span data-ttu-id="51c76-105">`Alias`Ключевое слово можно использовать в следующем контексте:</span><span class="sxs-lookup"><span data-stu-id="51c76-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="51c76-106">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="51c76-106">Declare Statement</span></span>](declare-statement.md)  
  
 <span data-ttu-id="51c76-107">В следующем примере `Alias` ключевое слово используется для предоставления имени функции в advapi32. dll, `GetUserNameA` , которая `getUserName` используется вместо в этом примере.</span><span class="sxs-lookup"><span data-stu-id="51c76-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="51c76-108">Функция `getUserName` вызывается в подпрограмме `getUser` , которая отображает имя текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="51c76-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="51c76-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="51c76-109">See also</span></span>

- [<span data-ttu-id="51c76-110">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="51c76-110">Keywords</span></span>](../keywords/index.md)
