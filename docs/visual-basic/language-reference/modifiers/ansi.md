---
title: Ansi
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: 8dfd830e4c7ed97c8813da4ad310ee59b26f44f8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90868798"
---
# <a name="ansi-visual-basic"></a><span data-ttu-id="8c5a0-102">Ansi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c5a0-102">Ansi (Visual Basic)</span></span>

<span data-ttu-id="8c5a0-103">Указывает, что Visual Basic должны маршалировать все строки в значения Американский национальный институт стандартов (ANSI) (ANSI) независимо от имени объявляемой внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="8c5a0-103">Specifies that Visual Basic should marshal all strings to American National Standards Institute (ANSI) values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="8c5a0-104">При вызове процедуры, определенной вне проекта, Visual Basic компилятор не имеет доступа к информации, которая необходима для правильного вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="8c5a0-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it needs to call the procedure correctly.</span></span> <span data-ttu-id="8c5a0-105">Эти сведения включают в себя расположение процедуры, способ ее определения, последовательность вызова и тип возвращаемого значения, а также используемую строковую кодировку.</span><span class="sxs-lookup"><span data-stu-id="8c5a0-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="8c5a0-106">[Инструкция DECLARE](../statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет эти необходимые сведения.</span><span class="sxs-lookup"><span data-stu-id="8c5a0-106">The [Declare Statement](../statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="8c5a0-107">`charsetmodifier`Часть в `Declare` инструкции предоставляет сведения о кодировке для упаковки строк во время вызова внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="8c5a0-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="8c5a0-108">Он также влияет на то, как Visual Basic ищет имя внешней процедуры во внешнем файле.</span><span class="sxs-lookup"><span data-stu-id="8c5a0-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="8c5a0-109">`Ansi`Модификатор указывает, что Visual Basic должен маршалировать все строки в значения ANSI и выполнять поиск процедуры, не изменяя ее имя во время поиска.</span><span class="sxs-lookup"><span data-stu-id="8c5a0-109">The `Ansi` modifier specifies that Visual Basic should marshal all strings to ANSI values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="8c5a0-110">Если модификатор кодировки не указан, используется значение `Ansi` по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8c5a0-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c5a0-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="8c5a0-111">Remarks</span></span>  

 <span data-ttu-id="8c5a0-112">`Ansi`Модификатор можно использовать в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="8c5a0-112">The `Ansi` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="8c5a0-113">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="8c5a0-113">Declare Statement</span></span>](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="8c5a0-114">Примечания для разработчиков смарт-устройств</span><span class="sxs-lookup"><span data-stu-id="8c5a0-114">Smart Device Developer Notes</span></span>  

 <span data-ttu-id="8c5a0-115">Это ключевое слово не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8c5a0-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c5a0-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8c5a0-116">See also</span></span>

- [<span data-ttu-id="8c5a0-117">Автоматически</span><span class="sxs-lookup"><span data-stu-id="8c5a0-117">Auto</span></span>](auto.md)
- [<span data-ttu-id="8c5a0-118">Юникод</span><span class="sxs-lookup"><span data-stu-id="8c5a0-118">Unicode</span></span>](unicode.md)
- [<span data-ttu-id="8c5a0-119">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8c5a0-119">Keywords</span></span>](../keywords/index.md)
