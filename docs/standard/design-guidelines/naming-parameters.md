---
title: Именование параметров
description: Ознакомьтесь с рекомендациями по именованию параметров. Например, используйте описательные имена параметров & Camel, & рассмотрите возможность именования на основе значения, а не типа.
ms.date: 10/22/2008
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
ms.openlocfilehash: 9f03eda511c2ef0c9565d270c52fd72bf54692d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698355"
---
# <a name="naming-parameters"></a><span data-ttu-id="4db6d-104">Именование параметров</span><span class="sxs-lookup"><span data-stu-id="4db6d-104">Naming Parameters</span></span>

<span data-ttu-id="4db6d-105">Помимо очевидной причины удобочитаемости, важно следовать рекомендациям по именам параметров, так как параметры отображаются в документации и в конструкторе, когда визуальные средства проектирования предоставляют функции IntelliSense и просмотра классов.</span><span class="sxs-lookup"><span data-stu-id="4db6d-105">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>

 <span data-ttu-id="4db6d-106">✔️ использовать Камелкасинг в именах параметров.</span><span class="sxs-lookup"><span data-stu-id="4db6d-106">✔️ DO use camelCasing in parameter names.</span></span>

 <span data-ttu-id="4db6d-107">✔️ использовать описательные имена параметров.</span><span class="sxs-lookup"><span data-stu-id="4db6d-107">✔️ DO use descriptive parameter names.</span></span>

 <span data-ttu-id="4db6d-108">✔️ РЕКОМЕНДУЕТСЯ использовать имена на основе значения параметра, а не типа параметра.</span><span class="sxs-lookup"><span data-stu-id="4db6d-108">✔️ CONSIDER using names based on a parameter’s meaning rather than the parameter’s type.</span></span>

### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="4db6d-109">Именование параметров перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="4db6d-109">Naming Operator Overload Parameters</span></span>

 <span data-ttu-id="4db6d-110">✔️ использовать `left` и `right` для параметров перегрузки бинарного оператора, если нет смысла в отношении параметров.</span><span class="sxs-lookup"><span data-stu-id="4db6d-110">✔️ DO use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>

 <span data-ttu-id="4db6d-111">✔️ использовать `value` для перегрузки имен параметров унарного оператора, если нет смысла в отношении параметров.</span><span class="sxs-lookup"><span data-stu-id="4db6d-111">✔️ DO use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>

 <span data-ttu-id="4db6d-112">✔️ Рассмотрите осмысленные имена для параметров перегрузки оператора, если это складывает значительное значение.</span><span class="sxs-lookup"><span data-stu-id="4db6d-112">✔️ CONSIDER meaningful names for operator overload parameters if doing so adds significant value.</span></span>

 <span data-ttu-id="4db6d-113">❌ НЕ используйте аббревиатуры или числовые индексы для имен параметров перегрузки оператора.</span><span class="sxs-lookup"><span data-stu-id="4db6d-113">❌ DO NOT use abbreviations or numeric indices for operator overload parameter names.</span></span>

 <span data-ttu-id="4db6d-114">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="4db6d-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="4db6d-115">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="4db6d-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="4db6d-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4db6d-116">See also</span></span>

- [<span data-ttu-id="4db6d-117">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="4db6d-117">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="4db6d-118">Рекомендации по именованию</span><span class="sxs-lookup"><span data-stu-id="4db6d-118">Naming Guidelines</span></span>](naming-guidelines.md)
