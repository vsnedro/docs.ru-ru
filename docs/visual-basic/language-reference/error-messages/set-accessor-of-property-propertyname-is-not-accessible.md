---
title: Метод доступа Set свойства <propertyname> недоступен
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: 077533a5b1fe241b61ded9516ad8f450d7dbbf5e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400348"
---
# <a name="set-accessor-of-property-propertyname-is-not-accessible"></a><span data-ttu-id="8983d-102">Метод доступа Set свойства \<propertyname> недоступен</span><span class="sxs-lookup"><span data-stu-id="8983d-102">'Set' accessor of property '\<propertyname>' is not accessible</span></span>
<span data-ttu-id="8983d-103">Оператор пытается сохранить значение свойства, если оно не имеет доступа к `Set` процедуре свойства.</span><span class="sxs-lookup"><span data-stu-id="8983d-103">A statement attempts to store the value of a property when it does not have access to the property's `Set` procedure.</span></span>  
  
 <span data-ttu-id="8983d-104">Если [инструкция SET](../statements/set-statement.md) помечена более ограниченным уровнем доступа, чем его [Инструкция Property](../statements/property-statement.md), попытка установить значение свойства может завершиться ошибкой в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="8983d-104">If the [Set Statement](../statements/set-statement.md) is marked with a more restrictive access level than its [Property Statement](../statements/property-statement.md), an attempt to set the property value could fail in the following cases:</span></span>  
  
- <span data-ttu-id="8983d-105">`Set`Инструкция помечена как [закрытая](../modifiers/private.md) , а вызывающий код находится за пределами класса или структуры, в которой определено свойство.</span><span class="sxs-lookup"><span data-stu-id="8983d-105">The `Set` statement is marked [Private](../modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
- <span data-ttu-id="8983d-106">`Set`Инструкция помечена как [protected](../modifiers/protected.md) и вызывающий код не находится в классе или структуре, в которой определено свойство, и в производном классе.</span><span class="sxs-lookup"><span data-stu-id="8983d-106">The `Set` statement is marked [Protected](../modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
- <span data-ttu-id="8983d-107">`Set`Инструкция помечена как [Friend](../modifiers/friend.md) , а вызывающий код — не в той сборке, в которой определено свойство.</span><span class="sxs-lookup"><span data-stu-id="8983d-107">The `Set` statement is marked [Friend](../modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="8983d-108">**Идентификатор ошибки:** BC31102</span><span class="sxs-lookup"><span data-stu-id="8983d-108">**Error ID:** BC31102</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8983d-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="8983d-109">To correct this error</span></span>  
  
- <span data-ttu-id="8983d-110">Если вы управляете исходным кодом, определяющим свойство, попробуйте объявить `Set` процедуру с тем же уровнем доступа, что и само свойство.</span><span class="sxs-lookup"><span data-stu-id="8983d-110">If you have control of the source code defining the property, consider declaring the `Set` procedure with the same access level as the property itself.</span></span>  
  
- <span data-ttu-id="8983d-111">Если у вас нет контроля над исходным кодом, определяющим свойство, или необходимо ограничить `Set` уровень доступа к процедуре больше, чем само свойство, попробуйте переместить инструкцию, устанавливающую значение свойства, в область кода, имеющую Улучшенный доступ к свойству.</span><span class="sxs-lookup"><span data-stu-id="8983d-111">If you do not have control of the source code defining the property, or you must restrict the `Set` procedure access level more than the property itself, try to move the statement that sets the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8983d-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8983d-112">See also</span></span>

- [<span data-ttu-id="8983d-113">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="8983d-113">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="8983d-114">Практическое руководство. Объявление свойства со смешанным уровнем доступа</span><span class="sxs-lookup"><span data-stu-id="8983d-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
