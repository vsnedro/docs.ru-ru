---
title: Имена пространств имен.
description: Используйте эти рекомендации для именования пространств имен в рамках рекомендаций по проектированию библиотек, которые расширяют и взаимодействуют с библиотеками .NET.
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
ms.openlocfilehash: 0ad98af240cf8d1041d6a8b64ab71a56e763f76f
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419061"
---
# <a name="names-of-namespaces"></a><span data-ttu-id="c9d9e-103">Имена пространств имен.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-103">Names of Namespaces</span></span>
<span data-ttu-id="c9d9e-104">Как и в случае с другими рекомендациями по именованию, цель при именовании пространств имен заключается в создании достаточной ясности для программиста, использующего платформу для немедленного знания содержимого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-104">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="c9d9e-105">Следующий шаблон задает общее правило для именования пространств имен.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-105">The following template specifies the general rule for naming namespaces:</span></span>

 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`

 <span data-ttu-id="c9d9e-106">Примеры:</span><span class="sxs-lookup"><span data-stu-id="c9d9e-106">The following are examples:</span></span>

 <span data-ttu-id="c9d9e-107">`Fabrikam.Math` `Litware.Security`</span><span class="sxs-lookup"><span data-stu-id="c9d9e-107">`Fabrikam.Math` `Litware.Security`</span></span>

 <span data-ttu-id="c9d9e-108">✔️ добавляйте имена пространств имен в имя компании, чтобы предотвратить наличие одинакового имени в пространствах имен разных компаний.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-108">✔️ DO prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>

 <span data-ttu-id="c9d9e-109">✔️ использовать стабильное, независимое от версии имя продукта на втором уровне имени пространства имен.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-109">✔️ DO use a stable, version-independent product name at the second level of a namespace name.</span></span>

 <span data-ttu-id="c9d9e-110">❌НЕ используйте организационные иерархии в качестве основания для имен в иерархиях пространства имен, так как имена групп в организациях, как правило, являются кратковременными.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-110">❌ DO NOT use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="c9d9e-111">Упорядочите иерархию пространств имен вокруг групп связанных технологий.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-111">Organize the hierarchy of namespaces around groups of related technologies.</span></span>

 <span data-ttu-id="c9d9e-112">✔️ использовать Паскалкасинг и отдельные компоненты пространства имен с точками (например, `Microsoft.Office.PowerPoint` ).</span><span class="sxs-lookup"><span data-stu-id="c9d9e-112">✔️ DO use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="c9d9e-113">Если ваша торговая марка использует нетрадиционный регистр, следует соблюдать регистр, заданный в торговой марке, даже если он отличается от обычного регистра пространства имен.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-113">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>

 <span data-ttu-id="c9d9e-114">✔️ Рассмотрите возможность использования имен множественного числа пространств имен, где это уместно.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-114">✔️ CONSIDER using plural namespace names where appropriate.</span></span>

 <span data-ttu-id="c9d9e-115">Например, используйте функцию `System.Collections` вместо `System.Collection`.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-115">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="c9d9e-116">Однако названия и акронимы торговых марок являются исключениями из этого правила.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-116">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="c9d9e-117">Например, используйте функцию `System.IO` вместо `System.IOs`.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-117">For example, use `System.IO` instead of `System.IOs`.</span></span>

 <span data-ttu-id="c9d9e-118">❌НЕ используйте одно и то же имя для пространства имен и типа в этом пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-118">❌ DO NOT use the same name for a namespace and a type in that namespace.</span></span>

 <span data-ttu-id="c9d9e-119">Например, не используйте `Debug` в качестве имени пространства имен, а затем предоставьте класс с именем `Debug` в том же пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-119">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="c9d9e-120">Для некоторых компиляторов такие типы должны быть полными.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-120">Several compilers require such types to be fully qualified.</span></span>

### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="c9d9e-121">Конфликты пространств имен и имен типов</span><span class="sxs-lookup"><span data-stu-id="c9d9e-121">Namespaces and Type Name Conflicts</span></span>
 <span data-ttu-id="c9d9e-122">❌Не вводите имена универсальных типов, такие как `Element` , `Node` , `Log` и `Message` .</span><span class="sxs-lookup"><span data-stu-id="c9d9e-122">❌ DO NOT introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>

 <span data-ttu-id="c9d9e-123">Очень высокая вероятность того, что это приводит к конфликтам имен типов в распространенных сценариях.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-123">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="c9d9e-124">Необходимо уточнить имена универсальных типов ( `FormElement` , `XmlNode` , `EventLog` , `SoapMessage` ).</span><span class="sxs-lookup"><span data-stu-id="c9d9e-124">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>

 <span data-ttu-id="c9d9e-125">Существуют определенные рекомендации по предотвращению конфликтов имен типов для различных категорий пространств имен.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-125">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>

- <span data-ttu-id="c9d9e-126">**Пространства имен модели приложения**</span><span class="sxs-lookup"><span data-stu-id="c9d9e-126">**Application model namespaces**</span></span>

     <span data-ttu-id="c9d9e-127">Пространства имен, принадлежащие одной модели приложения, часто используются вместе, но они практически никогда не используются с пространствами имен других моделей приложений.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-127">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="c9d9e-128">Например, <xref:System.Windows.Forms?displayProperty=nameWithType> пространство имен редко используется вместе с <xref:System.Web.UI?displayProperty=nameWithType> пространством имен.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-128">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="c9d9e-129">Ниже приведен список хорошо известных групп пространств имен модели приложений.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-129">The following is a list of well-known application model namespace groups:</span></span>

     <span data-ttu-id="c9d9e-130">`System.Windows*` `System.Web.UI*`</span><span class="sxs-lookup"><span data-stu-id="c9d9e-130">`System.Windows*` `System.Web.UI*`</span></span>

     <span data-ttu-id="c9d9e-131">❌НЕ присваивайте имена типам в пространствах имен в одной модели приложения.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-131">❌ DO NOT give the same name to types in namespaces within a single application model.</span></span>

     <span data-ttu-id="c9d9e-132">Например, не добавляйте тип с именем `Page` в <xref:System.Web.UI.Adapters?displayProperty=nameWithType> пространство имен, так как <xref:System.Web.UI?displayProperty=nameWithType> пространство имен уже содержит тип с именем `Page` .</span><span class="sxs-lookup"><span data-stu-id="c9d9e-132">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>

- <span data-ttu-id="c9d9e-133">**Пространства имен инфраструктуры**</span><span class="sxs-lookup"><span data-stu-id="c9d9e-133">**Infrastructure namespaces**</span></span>

     <span data-ttu-id="c9d9e-134">Эта группа содержит пространства имен, которые редко импортируются во время разработки общих приложений.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-134">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="c9d9e-135">Например, `.Design` пространства имен в основном используются при разработке средств программирования.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-135">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="c9d9e-136">Предотвращение конфликтов с типами в этих пространствах имен не является критически важным.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-136">Avoiding conflicts with types in these namespaces is not critical.</span></span>

- <span data-ttu-id="c9d9e-137">**Основные пространства имен**</span><span class="sxs-lookup"><span data-stu-id="c9d9e-137">**Core namespaces**</span></span>

     <span data-ttu-id="c9d9e-138">К основным пространствам имен относятся все `System` пространства имен, за исключением пространств имен моделей приложений и пространств имен инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-138">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="c9d9e-139">К основным пространствам имен относятся, в частности,,, `System` `System.IO` `System.Xml` и `System.Net` .</span><span class="sxs-lookup"><span data-stu-id="c9d9e-139">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>

     <span data-ttu-id="c9d9e-140">❌НЕ присваивайте имена типов, которые конфликтуют с любым типом в основных пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-140">❌ DO NOT give types names that would conflict with any type in the Core namespaces.</span></span>

     <span data-ttu-id="c9d9e-141">Например, никогда не используйте `Stream` в качестве имени типа.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-141">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="c9d9e-142">Он будет конфликтовать с <xref:System.IO.Stream?displayProperty=nameWithType> , очень часто используемый тип.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-142">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>

- <span data-ttu-id="c9d9e-143">**Группы пространств имен технологий**</span><span class="sxs-lookup"><span data-stu-id="c9d9e-143">**Technology namespace groups**</span></span>

     <span data-ttu-id="c9d9e-144">Эта категория включает все пространства имен с теми же первыми двумя узлами пространства имен `(<Company>.<Technology>*` , например `Microsoft.Build.Utilities` и `Microsoft.Build.Tasks` .</span><span class="sxs-lookup"><span data-stu-id="c9d9e-144">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="c9d9e-145">Важно, чтобы типы, принадлежащие одной технологии, не конфликтовали друг с другом.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-145">It is important that types belonging to a single technology do not conflict with each other.</span></span>

     <span data-ttu-id="c9d9e-146">❌НЕ присваивайте имена типов, которые конфликтуют с другими типами в рамках одной технологии.</span><span class="sxs-lookup"><span data-stu-id="c9d9e-146">❌ DO NOT assign type names that would conflict with other types within a single technology.</span></span>

     <span data-ttu-id="c9d9e-147">❌НЕ вводите конфликты имен типов между типами в пространствах имен технологий и пространством имен модели приложения (если только эта технология не предназначена для использования с моделью приложения).</span><span class="sxs-lookup"><span data-stu-id="c9d9e-147">❌ DO NOT introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>

 <span data-ttu-id="c9d9e-148">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="c9d9e-148">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="c9d9e-149">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="c9d9e-149">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="c9d9e-150">См. также статью</span><span class="sxs-lookup"><span data-stu-id="c9d9e-150">See also</span></span>

- [<span data-ttu-id="c9d9e-151">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="c9d9e-151">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="c9d9e-152">Рекомендации по именованию</span><span class="sxs-lookup"><span data-stu-id="c9d9e-152">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
