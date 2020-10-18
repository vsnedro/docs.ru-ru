---
title: Свойство <propertyname1>, используемое по умолчанию, конфликтует со свойством <propertyname2>, используемым по умолчанию в классе <classname>, и должно быть объявлено с ключевым словом Shadows
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: 290971a3173c59f08fbd279b6fffe3bcb618cb72
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160611"
---
# <a name="bc40007-default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a><span data-ttu-id="bc512-102">BC40007: свойство по умолчанию " \<propertyname1> " конфликтует со свойством по умолчанию " \<propertyname2> " в " \<classname> " и поэтому должно быть объявлено как "Shadows"</span><span class="sxs-lookup"><span data-stu-id="bc512-102">BC40007: Default property '\<propertyname1>' conflicts with default property '\<propertyname2>' in '\<classname>' and so should be declared 'Shadows'</span></span>

<span data-ttu-id="bc512-103">Свойство объявлено с тем же именем, что и у свойства, определенного в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="bc512-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="bc512-104">В этом случае свойство в этом классе должно скрывать свойство базового класса.</span><span class="sxs-lookup"><span data-stu-id="bc512-104">In this situation, the property in this class should shadow the base class property.</span></span>

 <span data-ttu-id="bc512-105">Это сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="bc512-105">This message is a warning.</span></span> <span data-ttu-id="bc512-106">`Shadows` подразумевается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bc512-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="bc512-107">Дополнительные сведения о сокрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="bc512-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="bc512-108">**Идентификатор ошибки:** BC40007</span><span class="sxs-lookup"><span data-stu-id="bc512-108">**Error ID:** BC40007</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="bc512-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="bc512-109">To correct this error</span></span>

- <span data-ttu-id="bc512-110">Добавьте `Shadows` ключевое слово в объявление или измените имя объявляемого свойства.</span><span class="sxs-lookup"><span data-stu-id="bc512-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc512-111">См. также</span><span class="sxs-lookup"><span data-stu-id="bc512-111">See also</span></span>

- [<span data-ttu-id="bc512-112">Тени</span><span class="sxs-lookup"><span data-stu-id="bc512-112">Shadows</span></span>](../modifiers/shadows.md)
- [<span data-ttu-id="bc512-113">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bc512-113">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
