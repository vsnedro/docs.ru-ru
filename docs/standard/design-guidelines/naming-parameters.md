---
title: Именование параметров
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
ms.openlocfilehash: 0d5c5cd144fbae88439ee981fbdb6e30ff487005
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290166"
---
# <a name="naming-parameters"></a><span data-ttu-id="3e7fb-102">Именование параметров</span><span class="sxs-lookup"><span data-stu-id="3e7fb-102">Naming Parameters</span></span>
<span data-ttu-id="3e7fb-103">Помимо очевидной причины удобочитаемости, важно следовать рекомендациям по именам параметров, так как параметры отображаются в документации и в конструкторе, когда визуальные средства проектирования предоставляют функции IntelliSense и просмотра классов.</span><span class="sxs-lookup"><span data-stu-id="3e7fb-103">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>

 <span data-ttu-id="3e7fb-104">✔️ использовать Камелкасинг в именах параметров.</span><span class="sxs-lookup"><span data-stu-id="3e7fb-104">✔️ DO use camelCasing in parameter names.</span></span>

 <span data-ttu-id="3e7fb-105">✔️ использовать описательные имена параметров.</span><span class="sxs-lookup"><span data-stu-id="3e7fb-105">✔️ DO use descriptive parameter names.</span></span>

 <span data-ttu-id="3e7fb-106">✔️ РЕКОМЕНДУЕТСЯ использовать имена на основе значения параметра, а не типа параметра.</span><span class="sxs-lookup"><span data-stu-id="3e7fb-106">✔️ CONSIDER using names based on a parameter’s meaning rather than the parameter’s type.</span></span>

### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="3e7fb-107">Именование параметров перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="3e7fb-107">Naming Operator Overload Parameters</span></span>
 <span data-ttu-id="3e7fb-108">✔️ использовать `left` и `right` для параметров перегрузки бинарного оператора, если нет смысла в отношении параметров.</span><span class="sxs-lookup"><span data-stu-id="3e7fb-108">✔️ DO use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>

 <span data-ttu-id="3e7fb-109">✔️ использовать `value` для перегрузки имен параметров унарного оператора, если нет смысла в отношении параметров.</span><span class="sxs-lookup"><span data-stu-id="3e7fb-109">✔️ DO use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>

 <span data-ttu-id="3e7fb-110">✔️ Рассмотрите осмысленные имена для параметров перегрузки оператора, если это складывает значительное значение.</span><span class="sxs-lookup"><span data-stu-id="3e7fb-110">✔️ CONSIDER meaningful names for operator overload parameters if doing so adds significant value.</span></span>

 <span data-ttu-id="3e7fb-111">❌НЕ используйте аббревиатуры или числовые индексы для имен параметров перегрузки оператора.</span><span class="sxs-lookup"><span data-stu-id="3e7fb-111">❌ DO NOT use abbreviations or numeric indices for operator overload parameter names.</span></span>

 <span data-ttu-id="3e7fb-112">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="3e7fb-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="3e7fb-113">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="3e7fb-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="3e7fb-114">См. также</span><span class="sxs-lookup"><span data-stu-id="3e7fb-114">See also</span></span>

- [<span data-ttu-id="3e7fb-115">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="3e7fb-115">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="3e7fb-116">Рекомендации по именованию</span><span class="sxs-lookup"><span data-stu-id="3e7fb-116">Naming Guidelines</span></span>](naming-guidelines.md)
