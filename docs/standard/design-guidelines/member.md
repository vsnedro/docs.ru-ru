---
title: Правила разработки членов
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
ms.openlocfilehash: c323e7edd752a1f003bd3f5d81689aca0eaefd20
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288996"
---
# <a name="member-design-guidelines"></a><span data-ttu-id="12819-102">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="12819-102">Member Design Guidelines</span></span>
<span data-ttu-id="12819-103">Методы, свойства, события, конструкторы и поля вместе называются членами.</span><span class="sxs-lookup"><span data-stu-id="12819-103">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="12819-104">Члены в конечном итоге представляют собой средства, с помощью которых функциональные возможности платформы предоставляются конечным пользователям платформы.</span><span class="sxs-lookup"><span data-stu-id="12819-104">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="12819-105">Члены могут быть виртуальными или невиртуальными, конкретными или абстрактными, статическими или экземплярами, а также могут иметь несколько различных областей доступа.</span><span class="sxs-lookup"><span data-stu-id="12819-105">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="12819-106">Все эти разнообразные выявляются невероятно выразительным, но в то же время необходимо соблюдать часть конструктора инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="12819-106">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="12819-107">Эта глава содержит основные рекомендации, которые следует выполнить при проектировании элементов любого типа.</span><span class="sxs-lookup"><span data-stu-id="12819-107">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="12819-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="12819-108">In This Section</span></span>  
 [<span data-ttu-id="12819-109">Перегрузка членов</span><span class="sxs-lookup"><span data-stu-id="12819-109">Member Overloading</span></span>](member-overloading.md)  
 [<span data-ttu-id="12819-110">Конструктор свойств</span><span class="sxs-lookup"><span data-stu-id="12819-110">Property Design</span></span>](property.md)  
 [<span data-ttu-id="12819-111">Конструктор конструктора</span><span class="sxs-lookup"><span data-stu-id="12819-111">Constructor Design</span></span>](constructor.md)  
 [<span data-ttu-id="12819-112">Проектирование событий</span><span class="sxs-lookup"><span data-stu-id="12819-112">Event Design</span></span>](event.md)  
 [<span data-ttu-id="12819-113">Проектирование полей</span><span class="sxs-lookup"><span data-stu-id="12819-113">Field Design</span></span>](field.md)  
 [<span data-ttu-id="12819-114">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="12819-114">Extension Methods</span></span>](extension-methods.md)  
 [<span data-ttu-id="12819-115">Перегрузки операторов</span><span class="sxs-lookup"><span data-stu-id="12819-115">Operator Overloads</span></span>](operator-overloads.md)  
 [<span data-ttu-id="12819-116">Конструктор параметров</span><span class="sxs-lookup"><span data-stu-id="12819-116">Parameter Design</span></span>](parameter-design.md)  
 <span data-ttu-id="12819-117">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="12819-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="12819-118">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="12819-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12819-119">См. также</span><span class="sxs-lookup"><span data-stu-id="12819-119">See also</span></span>

- [<span data-ttu-id="12819-120">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="12819-120">Framework Design Guidelines</span></span>](index.md)
