---
title: Свойство <propertyname1>, используемое по умолчанию, конфликтует со свойством <propertyname2>, используемым по умолчанию в классе <classname>, и должно быть объявлено с ключевым словом Shadows
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: 37f98ce8120d5861552819690f9d5f22c9959a0e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409729"
---
# <a name="default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a><span data-ttu-id="6842b-102">Свойство \<propertyname1>, используемое по умолчанию, конфликтует со свойством \<propertyname2>, используемым по умолчанию в классе \<classname>, и должно быть объявлено с ключевым словом Shadows</span><span class="sxs-lookup"><span data-stu-id="6842b-102">Default property '\<propertyname1>' conflicts with default property '\<propertyname2>' in '\<classname>' and so should be declared 'Shadows'</span></span>
<span data-ttu-id="6842b-103">Свойство объявлено с тем же именем, что и у свойства, определенного в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="6842b-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="6842b-104">В этом случае свойство в этом классе должно скрывать свойство базового класса.</span><span class="sxs-lookup"><span data-stu-id="6842b-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="6842b-105">Это сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="6842b-105">This message is a warning.</span></span> <span data-ttu-id="6842b-106">`Shadows` подразумевается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6842b-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="6842b-107">Дополнительные сведения о сокрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="6842b-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="6842b-108">**Идентификатор ошибки:** BC40007</span><span class="sxs-lookup"><span data-stu-id="6842b-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6842b-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6842b-109">To correct this error</span></span>  
  
- <span data-ttu-id="6842b-110">Добавьте `Shadows` ключевое слово в объявление или измените имя объявляемого свойства.</span><span class="sxs-lookup"><span data-stu-id="6842b-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6842b-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6842b-111">See also</span></span>

- [<span data-ttu-id="6842b-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="6842b-112">Shadows</span></span>](../modifiers/shadows.md)
- [<span data-ttu-id="6842b-113">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6842b-113">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
