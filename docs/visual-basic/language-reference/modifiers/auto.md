---
title: Auto (Автоматически)
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: b9bdeed55788252c71b8fb1c995c140cbfdf60eb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373132"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="aea5a-102">Auto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aea5a-102">Auto (Visual Basic)</span></span>
<span data-ttu-id="aea5a-103">Указывает, что Visual Basic должны маршалировать строки согласно правилам .NET Framework, исходя из внешнего имени объявляемой внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="aea5a-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="aea5a-104">При вызове процедуры, определенной вне проекта, Visual Basic компилятор не имеет доступа к информации, которая необходима для правильного вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="aea5a-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="aea5a-105">Эти сведения включают в себя расположение процедуры, способ ее определения, последовательность вызова и тип возвращаемого значения, а также используемую строковую кодировку.</span><span class="sxs-lookup"><span data-stu-id="aea5a-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="aea5a-106">[Инструкция DECLARE](../statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет эти необходимые сведения.</span><span class="sxs-lookup"><span data-stu-id="aea5a-106">The [Declare Statement](../statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="aea5a-107">`charsetmodifier`Часть в `Declare` инструкции предоставляет сведения о кодировке для упаковки строк во время вызова внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="aea5a-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="aea5a-108">Он также влияет на то, как Visual Basic ищет имя внешней процедуры во внешнем файле.</span><span class="sxs-lookup"><span data-stu-id="aea5a-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="aea5a-109">`Auto`Модификатор указывает, что Visual Basic должен маршалировать строки в соответствии с правилами .NET Framework и должен определить базовый набор символов платформы времени выполнения и, возможно, изменить имя внешней процедуры в случае сбоя первоначального поиска.</span><span class="sxs-lookup"><span data-stu-id="aea5a-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="aea5a-110">Дополнительные сведения см. в разделе «Наборы символов» в [операторе Declare](../statements/declare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aea5a-110">For more information, see "Character Sets" in [Declare Statement](../statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="aea5a-111">Если модификатор кодировки не указан, используется значение `Ansi` по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aea5a-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aea5a-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="aea5a-112">Remarks</span></span>  
 <span data-ttu-id="aea5a-113">`Auto`Модификатор можно использовать в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="aea5a-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="aea5a-114">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="aea5a-114">Declare Statement</span></span>](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="aea5a-115">Примечания для разработчиков смарт-устройств</span><span class="sxs-lookup"><span data-stu-id="aea5a-115">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="aea5a-116">Это ключевое слово не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="aea5a-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aea5a-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="aea5a-117">See also</span></span>

- [<span data-ttu-id="aea5a-118">Ansi</span><span class="sxs-lookup"><span data-stu-id="aea5a-118">Ansi</span></span>](ansi.md)
- [<span data-ttu-id="aea5a-119">Юникод</span><span class="sxs-lookup"><span data-stu-id="aea5a-119">Unicode</span></span>](unicode.md)
- [<span data-ttu-id="aea5a-120">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="aea5a-120">Keywords</span></span>](../keywords/index.md)
