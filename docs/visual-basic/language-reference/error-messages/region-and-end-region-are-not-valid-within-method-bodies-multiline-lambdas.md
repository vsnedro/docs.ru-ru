---
title: 'Операторы #Region и #End Region недопустимы в телах методов/многострочных лямбда-операторах'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: 5652139ab139ea93258eb116f97ba21b76986a24
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400387"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="9437b-102">Операторы #Region и #End Region недопустимы в телах методов/многострочных лямбда-операторах</span><span class="sxs-lookup"><span data-stu-id="9437b-102">'#Region' and '#End Region' statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="9437b-103">`#Region`Блок должен быть объявлен на уровне класса, модуля или пространства имен.</span><span class="sxs-lookup"><span data-stu-id="9437b-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="9437b-104">Свертываемая область может включать одну или несколько процедур, но не может начинаться или заканчиваться внутри процедуры.</span><span class="sxs-lookup"><span data-stu-id="9437b-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="9437b-105">**Идентификатор ошибки:** BC32025</span><span class="sxs-lookup"><span data-stu-id="9437b-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9437b-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="9437b-106">To correct this error</span></span>  
  
1. <span data-ttu-id="9437b-107">Убедитесь, что предыдущая процедура правильно завершается `End Function` `End Sub` оператором или.</span><span class="sxs-lookup"><span data-stu-id="9437b-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="9437b-108">Убедитесь, что `#Region` `#End Region` директивы и находятся в одном блоке кода.</span><span class="sxs-lookup"><span data-stu-id="9437b-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9437b-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9437b-109">See also</span></span>

- [<span data-ttu-id="9437b-110">Директива #Region</span><span class="sxs-lookup"><span data-stu-id="9437b-110">#Region Directive</span></span>](../directives/region-directive.md)
