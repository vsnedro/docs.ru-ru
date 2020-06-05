---
title: Устранение неполадок, связанных с унаследованными обработчиками событий
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: 4e7bedd1de5197fcf8b69091f4cc878f41b01cd5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405110"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="7ed4f-102">Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ed4f-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="7ed4f-103">В этом разделе перечислены распространенные проблемы, возникающие при работе с обработчиками событий в наследуемых компонентах.</span><span class="sxs-lookup"><span data-stu-id="7ed4f-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="7ed4f-104">Процедуры</span><span class="sxs-lookup"><span data-stu-id="7ed4f-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="7ed4f-105">Код в обработчике событий выполняется дважды для каждого вызова</span><span class="sxs-lookup"><span data-stu-id="7ed4f-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
- <span data-ttu-id="7ed4f-106">Наследуемый обработчик событий не должен включать предложение [Handles](../../../language-reference/statements/handles-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="7ed4f-106">An inherited event handler must not include a [Handles](../../../language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="7ed4f-107">Метод в базовом классе уже связан с событием и будет срабатывать соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="7ed4f-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="7ed4f-108">Удалите `Handles` предложение из унаследованного метода.</span><span class="sxs-lookup"><span data-stu-id="7ed4f-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
- <span data-ttu-id="7ed4f-109">Если наследуемый метод не имеет `Handles` ключевого слова, убедитесь, что код не содержит лишних [операторов AddHandler](../../../language-reference/statements/addhandler-statement.md) или дополнительных методов, обрабатывающих это же событие.</span><span class="sxs-lookup"><span data-stu-id="7ed4f-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ed4f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="7ed4f-110">See also</span></span>

- [<span data-ttu-id="7ed4f-111">События</span><span class="sxs-lookup"><span data-stu-id="7ed4f-111">Events</span></span>](index.md)
