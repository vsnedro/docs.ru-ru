---
title: Именование ресурсов
description: Ознакомьтесь с рекомендациями по именованию ресурсов в .NET, которые похожи на рекомендации по именованию свойств.
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
ms.openlocfilehash: 765337bcf9fad4f9a8c9272a15b5c77d02770471
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768252"
---
# <a name="naming-resources"></a><span data-ttu-id="2509e-103">Именование ресурсов</span><span class="sxs-lookup"><span data-stu-id="2509e-103">Naming Resources</span></span>
<span data-ttu-id="2509e-104">Так как на локализуемые ресурсы можно ссылаться через определенные объекты, как если бы они были свойствами, рекомендации по именованию ресурсов похожи на правила свойств.</span><span class="sxs-lookup"><span data-stu-id="2509e-104">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>

 <span data-ttu-id="2509e-105">✔️ использовать Паскалкасинг в ключах ресурсов.</span><span class="sxs-lookup"><span data-stu-id="2509e-105">✔️ DO use PascalCasing in resource keys.</span></span>

 <span data-ttu-id="2509e-106">✔️ предоставлять описательные, а не короткие идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="2509e-106">✔️ DO provide descriptive rather than short identifiers.</span></span>

 <span data-ttu-id="2509e-107">❌НЕ используйте ключевые слова, относящиеся к языку, для основных языков CLR.</span><span class="sxs-lookup"><span data-stu-id="2509e-107">❌ DO NOT use language-specific keywords of the main CLR languages.</span></span>

 <span data-ttu-id="2509e-108">✔️ использовать в качестве имен ресурсов только буквы, цифры и символы подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="2509e-108">✔️ DO use only alphanumeric characters and underscores in naming resources.</span></span>

 <span data-ttu-id="2509e-109">✔️ использовать следующее соглашение об именовании для ресурсов сообщений об исключениях.</span><span class="sxs-lookup"><span data-stu-id="2509e-109">✔️ DO use the following naming convention for exception message resources.</span></span>

 <span data-ttu-id="2509e-110">Идентификатор ресурса должен быть именем типа исключения и коротким идентификатором исключения:</span><span class="sxs-lookup"><span data-stu-id="2509e-110">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>

 <span data-ttu-id="2509e-111">`ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`</span><span class="sxs-lookup"><span data-stu-id="2509e-111">`ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`</span></span>
 `ArgumentExceptionFileNameIsMalformed`

 <span data-ttu-id="2509e-112">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="2509e-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="2509e-113">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="2509e-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="2509e-114">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="2509e-114">See also</span></span>

- [<span data-ttu-id="2509e-115">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="2509e-115">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="2509e-116">Рекомендации по именованию</span><span class="sxs-lookup"><span data-stu-id="2509e-116">Naming Guidelines</span></span>](naming-guidelines.md)
