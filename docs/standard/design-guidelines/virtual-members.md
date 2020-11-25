---
title: Виртуальные члены
ms.date: 10/22/2008
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
ms.openlocfilehash: 7727ea7fcfdbbecf2e53ddd7a44b4cf907211f80
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734352"
---
# <a name="virtual-members"></a><span data-ttu-id="841e6-102">Виртуальные члены</span><span class="sxs-lookup"><span data-stu-id="841e6-102">Virtual Members</span></span>

<span data-ttu-id="841e6-103">Виртуальные члены могут быть переопределены, тем самым изменяя поведение подкласса.</span><span class="sxs-lookup"><span data-stu-id="841e6-103">Virtual members can be overridden, thus changing the behavior of the subclass.</span></span> <span data-ttu-id="841e6-104">Они очень похожи на обратные вызовы с точки зрения расширяемости, которые они предоставляют, но они лучше в плане производительности выполнения и потребления памяти.</span><span class="sxs-lookup"><span data-stu-id="841e6-104">They are quite similar to callbacks in terms of the extensibility they provide, but they are better in terms of execution performance and memory consumption.</span></span> <span data-ttu-id="841e6-105">Кроме того, виртуальные члены более естественны в сценариях, требующих создания специального типа (специализации).</span><span class="sxs-lookup"><span data-stu-id="841e6-105">Also, virtual members feel more natural in scenarios that require creating a special kind of an existing type (specialization).</span></span>

 <span data-ttu-id="841e6-106">Виртуальные члены работают лучше, чем обратные вызовы и события, но не работают лучше, чем методы, не являющиеся виртуальными.</span><span class="sxs-lookup"><span data-stu-id="841e6-106">Virtual members perform better than callbacks and events, but do not perform better than non-virtual methods.</span></span>

 <span data-ttu-id="841e6-107">Основным недостатком виртуальных членов является то, что поведение виртуального члена может быть изменено только во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="841e6-107">The main disadvantage of virtual members is that the behavior of a virtual member can only be modified at the time of compilation.</span></span> <span data-ttu-id="841e6-108">Поведение обратного вызова можно изменить во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="841e6-108">The behavior of a callback can be modified at runtime.</span></span>

 <span data-ttu-id="841e6-109">Виртуальные члены, такие как обратные вызовы (и, возможно, более обратные вызовы), являются дорогостоящими для проектирования, тестирования и обслуживания, так как любой вызов виртуального члена может быть переопределен непредсказуемым образом и может выполнять произвольный код.</span><span class="sxs-lookup"><span data-stu-id="841e6-109">Virtual members, like callbacks (and maybe more than callbacks), are costly to design, test, and maintain because any call to a virtual member can be overridden in unpredictable ways and can execute arbitrary code.</span></span> <span data-ttu-id="841e6-110">Кроме того, обычно требуется гораздо больше усилий, чтобы четко определить контракт виртуальных членов, так что затраты на проектирование и документирование их более высокие.</span><span class="sxs-lookup"><span data-stu-id="841e6-110">Also, much more effort is usually required to clearly define the contract of virtual members, so the cost of designing and documenting them is higher.</span></span>

 <span data-ttu-id="841e6-111">❌ НЕ Создавайте виртуальные члены, если у вас нет веских причин, и вы осведомлены о затратах, связанных с проектированием, тестированием и обслуживанием виртуальных членов.</span><span class="sxs-lookup"><span data-stu-id="841e6-111">❌ DO NOT make members virtual unless you have a good reason to do so and you are aware of all the costs related to designing, testing, and maintaining virtual members.</span></span>

 <span data-ttu-id="841e6-112">Виртуальные члены менее терпим отношению с точки зрения изменений, которые могут быть внесены в них без нарушения совместимости.</span><span class="sxs-lookup"><span data-stu-id="841e6-112">Virtual members are less forgiving in terms of changes that can be made to them without breaking compatibility.</span></span> <span data-ttu-id="841e6-113">Кроме того, они выполняются медленнее, чем невиртуальные члены, в основном потому, что вызовы к виртуальным членам не встроены.</span><span class="sxs-lookup"><span data-stu-id="841e6-113">Also, they are slower than non-virtual members, mostly because calls to virtual members are not inlined.</span></span>

 <span data-ttu-id="841e6-114">✔️ Рассмотрите возможность ограничения расширяемости только тем, что является абсолютно необходимым.</span><span class="sxs-lookup"><span data-stu-id="841e6-114">✔️ CONSIDER limiting extensibility to only what is absolutely necessary.</span></span>

 <span data-ttu-id="841e6-115">✔️ предпочтительнее использовать защищенный доступ для виртуальных членов.</span><span class="sxs-lookup"><span data-stu-id="841e6-115">✔️ DO prefer protected accessibility over public accessibility for virtual members.</span></span> <span data-ttu-id="841e6-116">Открытые члены должны предоставлять расширяемость (при необходимости) путем вызова в защищенный виртуальный член.</span><span class="sxs-lookup"><span data-stu-id="841e6-116">Public members should provide extensibility (if required) by calling into a protected virtual member.</span></span>

 <span data-ttu-id="841e6-117">Открытые члены класса должны предоставлять правильный набор функций для непосредственных потребителей этого класса.</span><span class="sxs-lookup"><span data-stu-id="841e6-117">The public members of a class should provide the right set of functionality for direct consumers of that class.</span></span> <span data-ttu-id="841e6-118">Виртуальные члены предназначены для переопределения в подклассах, а защищенный доступ — это отличный способ области для всех виртуальных точек расширения, где их можно использовать.</span><span class="sxs-lookup"><span data-stu-id="841e6-118">Virtual members are designed to be overridden in subclasses, and protected accessibility is a great way to scope all virtual extensibility points to where they can be used.</span></span>

 <span data-ttu-id="841e6-119">*Части &copy; 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="841e6-119">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="841e6-120">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="841e6-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="841e6-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="841e6-121">See also</span></span>

- [<span data-ttu-id="841e6-122">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="841e6-122">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="841e6-123">Разработка с обеспечением расширяемости</span><span class="sxs-lookup"><span data-stu-id="841e6-123">Designing for Extensibility</span></span>](designing-for-extensibility.md)
