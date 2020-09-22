---
title: 'Операторы #Region и #End Region недопустимы в телах методов/многострочных лямбда-операторах'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: e3147b6192f54ce85d0fecd6b67f7d80f6281b54
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870882"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="258bc-102">Операторы #Region и #End Region недопустимы в телах методов/многострочных лямбда-операторах</span><span class="sxs-lookup"><span data-stu-id="258bc-102">'#Region' and '#End Region' statements are not valid within method bodies/multiline lambdas</span></span>

<span data-ttu-id="258bc-103">`#Region`Блок должен быть объявлен на уровне класса, модуля или пространства имен.</span><span class="sxs-lookup"><span data-stu-id="258bc-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="258bc-104">Свертываемая область может включать одну или несколько процедур, но не может начинаться или заканчиваться внутри процедуры.</span><span class="sxs-lookup"><span data-stu-id="258bc-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="258bc-105">**Идентификатор ошибки:** BC32025</span><span class="sxs-lookup"><span data-stu-id="258bc-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="258bc-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="258bc-106">To correct this error</span></span>  
  
1. <span data-ttu-id="258bc-107">Убедитесь, что предыдущая процедура правильно завершается `End Function` `End Sub` оператором или.</span><span class="sxs-lookup"><span data-stu-id="258bc-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="258bc-108">Убедитесь, что `#Region` `#End Region` директивы и находятся в одном блоке кода.</span><span class="sxs-lookup"><span data-stu-id="258bc-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="258bc-109">См. также</span><span class="sxs-lookup"><span data-stu-id="258bc-109">See also</span></span>

- [<span data-ttu-id="258bc-110">Директива #Region</span><span class="sxs-lookup"><span data-stu-id="258bc-110">#Region Directive</span></span>](../directives/region-directive.md)
