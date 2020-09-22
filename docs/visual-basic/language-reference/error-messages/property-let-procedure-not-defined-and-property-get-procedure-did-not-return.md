---
title: Процедура свойства let не определена, а процедура свойства get не вернула объект
ms.date: 07/20/2015
f1_keywords:
- vbrID451
ms.assetid: 8542382a-689f-4e1b-abc0-c1e2dadb92f4
ms.openlocfilehash: fbeaa224ea9e095f86c37e571492d83bc98b4397
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871089"
---
# <a name="property-let-procedure-not-defined-and-property-get-procedure-did-not-return-an-object"></a><span data-ttu-id="8598c-102">Процедура свойства let не определена, а процедура свойства get не вернула объект</span><span class="sxs-lookup"><span data-stu-id="8598c-102">Property let procedure not defined and property get procedure did not return an object</span></span>

<span data-ttu-id="8598c-103">Определенные свойства, методы и операции могут применяться только к `Collection` объектам.</span><span class="sxs-lookup"><span data-stu-id="8598c-103">Certain properties, methods, and operations can only apply to `Collection` objects.</span></span> <span data-ttu-id="8598c-104">Вы указали операцию или свойство, которое является эксклюзивным для коллекций, но объект не является коллекцией.</span><span class="sxs-lookup"><span data-stu-id="8598c-104">You specified an operation or property that is exclusive to collections, but the object is not a collection.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8598c-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="8598c-105">To correct this error</span></span>  
  
1. <span data-ttu-id="8598c-106">Проверьте правильность написания имени объекта или свойства или убедитесь, что объект является `Collection` объектом.</span><span class="sxs-lookup"><span data-stu-id="8598c-106">Check the spelling of the object or property name, or verify that the object is a `Collection` object.</span></span>  
  
2. <span data-ttu-id="8598c-107">Взгляните на `Add` метод, используемый для добавления объекта в коллекцию, чтобы убедиться в правильности синтаксиса и правильности написания всех идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="8598c-107">Look at the `Add` method used to add the object to the collection to be sure the syntax is correct and that any identifiers were spelled correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8598c-108">См. также</span><span class="sxs-lookup"><span data-stu-id="8598c-108">See also</span></span>

- <xref:Microsoft.VisualBasic.Collection>
