---
title: Разработка с обеспечением расширяемости
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
ms.openlocfilehash: 406c15b6ce42b637ed1bbb61761d05e040995579
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280248"
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="6a9bf-102">Разработка с обеспечением расширяемости</span><span class="sxs-lookup"><span data-stu-id="6a9bf-102">Designing for Extensibility</span></span>
<span data-ttu-id="6a9bf-103">Одним из важных аспектов разработки платформы является обеспечение тщательного рассмотрения расширяемости платформы.</span><span class="sxs-lookup"><span data-stu-id="6a9bf-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="6a9bf-104">Для этого необходимо понимать затраты и преимущества, связанные с различными механизмами расширения.</span><span class="sxs-lookup"><span data-stu-id="6a9bf-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="6a9bf-105">Эта глава поможет вам решить, какие механизмы расширения (подклассы, события, виртуальные члены, обратные вызовы и т. д.) лучше удовлетворять требованиям вашей инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="6a9bf-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="6a9bf-106">Существует множество способов разрешить расширяемость в платформах.</span><span class="sxs-lookup"><span data-stu-id="6a9bf-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="6a9bf-107">Они находятся в диапазоне от менее мощных, но менее дорогостоящих к очень мощным, но дорогостоящим.</span><span class="sxs-lookup"><span data-stu-id="6a9bf-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="6a9bf-108">Для любого конкретного требования к расширяемости следует выбрать наиболее дорогостоящий механизм расширяемости, соответствующий требованиям.</span><span class="sxs-lookup"><span data-stu-id="6a9bf-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="6a9bf-109">Помните, что обычно можно добавить дополнительную расширяемость, но вы никогда не сможете отказаться от внесения критических изменений.</span><span class="sxs-lookup"><span data-stu-id="6a9bf-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6a9bf-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6a9bf-110">In This Section</span></span>  
 [<span data-ttu-id="6a9bf-111">Незапечатанные классы</span><span class="sxs-lookup"><span data-stu-id="6a9bf-111">Unsealed Classes</span></span>](unsealed-classes.md)  
 [<span data-ttu-id="6a9bf-112">Защищенные члены</span><span class="sxs-lookup"><span data-stu-id="6a9bf-112">Protected Members</span></span>](protected-members.md)  
 [<span data-ttu-id="6a9bf-113">События и обратные вызовы</span><span class="sxs-lookup"><span data-stu-id="6a9bf-113">Events and Callbacks</span></span>](events-and-callbacks.md)  
 [<span data-ttu-id="6a9bf-114">Виртуальные члены</span><span class="sxs-lookup"><span data-stu-id="6a9bf-114">Virtual Members</span></span>](virtual-members.md)  
 [<span data-ttu-id="6a9bf-115">Абстракции (абстрактные типы и интерфейсы)</span><span class="sxs-lookup"><span data-stu-id="6a9bf-115">Abstractions (Abstract Types and Interfaces)</span></span>](abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="6a9bf-116">Базовые классы для реализации абстракций</span><span class="sxs-lookup"><span data-stu-id="6a9bf-116">Base Classes for Implementing Abstractions</span></span>](base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="6a9bf-117">Запечатывание</span><span class="sxs-lookup"><span data-stu-id="6a9bf-117">Sealing</span></span>](sealing.md)  
 <span data-ttu-id="6a9bf-118">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="6a9bf-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6a9bf-119">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="6a9bf-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a9bf-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6a9bf-120">See also</span></span>

- [<span data-ttu-id="6a9bf-121">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="6a9bf-121">Framework Design Guidelines</span></span>](index.md)
