---
title: Разработка современных веб-приложений с помощью ASP.NET Core и Azure
description: Этот документ является полным руководством по созданию монолитных веб-приложений с помощью ASP.NET Core и Azure.
author: ardalis
ms.author: wiwagn
ms.date: 5/25/2020
ms.openlocfilehash: 7be03ea8edb763096b0684a62e71826f1cfcd42f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84284459"
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a><span data-ttu-id="22f12-103">Разработка современных веб-приложений с помощью ASP.NET Core и Azure</span><span class="sxs-lookup"><span data-stu-id="22f12-103">Architect Modern Web Applications with ASP.NET Core and Azure</span></span>

![Изображение обложки руководства по архитектуре современных веб-приложений.](./media/index/web-application-guide-cover-image.png)

<span data-ttu-id="22f12-105">**ВЫПУСК 3.1** — обновлен до ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="22f12-105">**EDITION v3.1** - Updated to ASP.NET Core 3.1</span></span>

<span data-ttu-id="22f12-106">ИЗДАТЕЛЬ</span><span class="sxs-lookup"><span data-stu-id="22f12-106">PUBLISHED BY</span></span>

<span data-ttu-id="22f12-107">Подразделение Microsoft Developer Division, команды разработки .NET и Visual Studio</span><span class="sxs-lookup"><span data-stu-id="22f12-107">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="22f12-108">Подразделение корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="22f12-108">A division of Microsoft Corporation</span></span>

<span data-ttu-id="22f12-109">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="22f12-109">One Microsoft Way</span></span>

<span data-ttu-id="22f12-110">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="22f12-110">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="22f12-111">© Корпорация Майкрософт (Microsoft Corporation), 2020 г.</span><span class="sxs-lookup"><span data-stu-id="22f12-111">Copyright © 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="22f12-112">Все права защищены.</span><span class="sxs-lookup"><span data-stu-id="22f12-112">All rights reserved.</span></span> <span data-ttu-id="22f12-113">Запрещается полное или частичное воспроизведение или передача настоящей книги в любом виде или любыми средствами без письменного разрешения издателя.</span><span class="sxs-lookup"><span data-stu-id="22f12-113">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="22f12-114">Эта книга предоставляется на условиях "как есть" и выражает взгляды и мнения автора.</span><span class="sxs-lookup"><span data-stu-id="22f12-114">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="22f12-115">Взгляды, мнения и сведения, содержащиеся в этой книге, включая URL-адреса и другие ссылки на веб-сайты, могут изменяться без уведомления.</span><span class="sxs-lookup"><span data-stu-id="22f12-115">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="22f12-116">Некоторые приведенные в книге примеры служат только для иллюстрации и являются вымышленными.</span><span class="sxs-lookup"><span data-stu-id="22f12-116">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="22f12-117">Все совпадения с реальными наименованиями, людьми и любыми другими предметами являются непреднамеренными и случайными.</span><span class="sxs-lookup"><span data-stu-id="22f12-117">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="22f12-118">Microsoft и товарные знаки, перечисленные на странице "Товарные знаки" на сайте <https://www.microsoft.com>, являются товарными знаками группы компаний Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="22f12-118">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="22f12-119">Mac и macOS являются товарными знаками Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="22f12-119">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="22f12-120">Логотип Docker с изображением кита является зарегистрированным товарным знаком Docker, Inc. Используется с разрешения.</span><span class="sxs-lookup"><span data-stu-id="22f12-120">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="22f12-121">Все другие наименования и логотипы являются собственностью своих законных владельцев.</span><span class="sxs-lookup"><span data-stu-id="22f12-121">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="22f12-122">Автор:</span><span class="sxs-lookup"><span data-stu-id="22f12-122">Author:</span></span>

> <span data-ttu-id="22f12-123">**Стив Смит (Steve Smith)** , преподаватель и разработчик программного обеспечения, [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="22f12-123">**Steve "ardalis" Smith** - Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="22f12-124">Редакторы:</span><span class="sxs-lookup"><span data-stu-id="22f12-124">Editors:</span></span>

> <span data-ttu-id="22f12-125">**Майра Вензел (Maira Wenzel)**</span><span class="sxs-lookup"><span data-stu-id="22f12-125">**Maira Wenzel**</span></span>

## <a name="action-links"></a><span data-ttu-id="22f12-126">Ссылки действий</span><span class="sxs-lookup"><span data-stu-id="22f12-126">Action links</span></span>

- <span data-ttu-id="22f12-127">Эта электронная книга также доступна в формате PDF (только на английском языке) [Скачать](https://aka.ms/webappebook)</span><span class="sxs-lookup"><span data-stu-id="22f12-127">This e-book is also available in a PDF format (English version only) [Download](https://aka.ms/webappebook)</span></span>

- <span data-ttu-id="22f12-128">Клонируйте эталонное приложение [eShopOnWeb на GitHub](https://github.com/dotnet-architecture/eShopOnWeb) или создайте для него вилку</span><span class="sxs-lookup"><span data-stu-id="22f12-128">Clone/Fork the reference application [eShopOnWeb on GitHub](https://github.com/dotnet-architecture/eShopOnWeb)</span></span>

## <a name="introduction"></a><span data-ttu-id="22f12-129">Вступление</span><span class="sxs-lookup"><span data-stu-id="22f12-129">Introduction</span></span>

<span data-ttu-id="22f12-130">.NET Core и ASP.NET Core имеют ряд преимуществ по сравнению с традиционной разработкой .NET.</span><span class="sxs-lookup"><span data-stu-id="22f12-130">.NET Core and ASP.NET Core offer several advantages over traditional .NET development.</span></span> <span data-ttu-id="22f12-131">Используйте .NET Core для серверных приложений, если для их успешной работы вам важны некоторые или все приведенные далее аспекты:</span><span class="sxs-lookup"><span data-stu-id="22f12-131">You should use .NET Core for your server applications if some or all of the following are important to your application's success:</span></span>

- <span data-ttu-id="22f12-132">Поддержка разных платформ.</span><span class="sxs-lookup"><span data-stu-id="22f12-132">Cross-platform support.</span></span>

- <span data-ttu-id="22f12-133">Использование микрослужб.</span><span class="sxs-lookup"><span data-stu-id="22f12-133">Use of microservices.</span></span>

- <span data-ttu-id="22f12-134">Использование контейнеров Docker.</span><span class="sxs-lookup"><span data-stu-id="22f12-134">Use of Docker containers.</span></span>

- <span data-ttu-id="22f12-135">Требования к обеспечению высокой производительности и масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="22f12-135">High performance and scalability requirements.</span></span>

- <span data-ttu-id="22f12-136">Параллельное управление версиями приложения .NET на одном сервере.</span><span class="sxs-lookup"><span data-stu-id="22f12-136">Side-by-side versioning of .NET versions by application on the same server.</span></span>

<span data-ttu-id="22f12-137">Эти требования поддерживаются многими стандартными приложениями .NET, но оптимизированные платформы ASP.NET Core и .NET Core обеспечивают расширенную поддержку указанных выше сценариев.</span><span class="sxs-lookup"><span data-stu-id="22f12-137">Traditional .NET applications can and do support many of these requirements, but ASP.NET Core and .NET Core have been optimized to offer improved support for the above scenarios.</span></span>

<span data-ttu-id="22f12-138">Все больше организаций предпочитают размещать свои веб-приложения в облаке с помощью таких служб, как Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="22f12-138">More and more organizations are choosing to host their web applications in the cloud using services like Microsoft Azure.</span></span> <span data-ttu-id="22f12-139">Рекомендуется рассмотреть возможность размещения приложения в облаке, если для приложения или организации важны следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="22f12-139">You should consider hosting your application in the cloud if the following are important to your application or organization:</span></span>

- <span data-ttu-id="22f12-140">Сокращение инвестиций в центр обработки данных (оборудование, программное обеспечение, помещения, коммунальные услуги, управление серверами и т. д.)</span><span class="sxs-lookup"><span data-stu-id="22f12-140">Reduced investment in data center costs (hardware, software, space, utilities, server management, etc.)</span></span>

- <span data-ttu-id="22f12-141">Гибкие цены (оплата за фактически используемые, а не простаивающие ресурсы).</span><span class="sxs-lookup"><span data-stu-id="22f12-141">Flexible pricing (pay based on usage, not for idle capacity).</span></span>

- <span data-ttu-id="22f12-142">Исключительная надежность.</span><span class="sxs-lookup"><span data-stu-id="22f12-142">Extreme reliability.</span></span>

- <span data-ttu-id="22f12-143">Улучшенная мобильность приложений, простота изменения места и способа их развертывания.</span><span class="sxs-lookup"><span data-stu-id="22f12-143">Improved app mobility; easily change where and how your app is deployed.</span></span>

- <span data-ttu-id="22f12-144">Гибкая емкость, масштабирование в соответствии с фактическими потребностями.</span><span class="sxs-lookup"><span data-stu-id="22f12-144">Flexible capacity; scale up or down based on actual needs.</span></span>

<span data-ttu-id="22f12-145">Создание веб-приложений с помощью ASP.NET Core, размещенных в Azure, имеет множество конкурентных преимуществ по сравнению с традиционными альтернативами.</span><span class="sxs-lookup"><span data-stu-id="22f12-145">Building web applications with ASP.NET Core, hosted in Azure, offers many competitive advantages over traditional alternatives.</span></span> <span data-ttu-id="22f12-146">Платформа ASP.NET Core оптимизирована для современных методик разработки веб-приложений и сценариев размещения в облаке.</span><span class="sxs-lookup"><span data-stu-id="22f12-146">ASP.NET Core is optimized for modern web application development practices and cloud hosting scenarios.</span></span> <span data-ttu-id="22f12-147">В этом руководстве вы узнаете, как спроектировать приложения ASP.NET Core, чтобы максимально эффективно воспользоваться этими возможностями.</span><span class="sxs-lookup"><span data-stu-id="22f12-147">In this guide, you'll learn how to architect your ASP.NET Core applications to best take advantage of these capabilities.</span></span>

## <a name="version"></a><span data-ttu-id="22f12-148">Версия</span><span class="sxs-lookup"><span data-stu-id="22f12-148">Version</span></span>

<span data-ttu-id="22f12-149">В новую редакцию руководства включены сведения о версии **.NET Core 3.1** и множество дополнений, связанных с тем же "поколением" технологий (то есть, технологий Azure и сторонних производителей), к которому относится выпуск .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="22f12-149">This guide has been revised to cover **.NET Core 3.1** version along with many additional updates related to the same "wave" of technologies (that is, Azure and additional third-party technologies) coinciding in time with the .NET Core 3.1 release.</span></span> <span data-ttu-id="22f12-150">По этой причине книга также обновлена до версии **3.1**.</span><span class="sxs-lookup"><span data-stu-id="22f12-150">That's why the book version has also been updated to version **3.1**.</span></span>

## <a name="purpose"></a><span data-ttu-id="22f12-151">Цель</span><span class="sxs-lookup"><span data-stu-id="22f12-151">Purpose</span></span>

<span data-ttu-id="22f12-152">Этот документ является полным руководством по созданию *монолитных* веб-приложений с помощью ASP.NET Core и Azure.</span><span class="sxs-lookup"><span data-stu-id="22f12-152">This guide provides end-to-end guidance on building *monolithic* web applications using ASP.NET Core and Azure.</span></span> <span data-ttu-id="22f12-153">В этом контексте монолитность означает то, что эти приложения развертываются как единое целое, а не как коллекция интерактивных служб и приложений.</span><span class="sxs-lookup"><span data-stu-id="22f12-153">In this context, "monolithic" refers to the fact that these applications are deployed as a single unit, not as a collection of interacting services and applications.</span></span>

<span data-ttu-id="22f12-154">Это руководство представляет собой дополнение к микрослужбам [" _.NET. Архитектура для упакованных в контейнеры приложений .NET_"](../microservices/index.md) с акцентом на Docker, микрослужбах и развертывании контейнеров для размещения корпоративных приложений.</span><span class="sxs-lookup"><span data-stu-id="22f12-154">This guide is complementary to ["_.NET Microservices. Architecture for Containerized .NET Applications_"](../microservices/index.md), which focuses more on Docker, microservices, and deployment of containers to host enterprise applications.</span></span>

### <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="22f12-155">Микрослужбы .NET.</span><span class="sxs-lookup"><span data-stu-id="22f12-155">.NET Microservices.</span></span> <span data-ttu-id="22f12-156">Архитектура контейнерных приложений .NET</span><span class="sxs-lookup"><span data-stu-id="22f12-156">Architecture for Containerized .NET Applications</span></span>

- <span data-ttu-id="22f12-157">**электронная книга**</span><span class="sxs-lookup"><span data-stu-id="22f12-157">**e-book**</span></span>  
  <https://aka.ms/MicroservicesEbook>
- <span data-ttu-id="22f12-158">**Пример приложения**</span><span class="sxs-lookup"><span data-stu-id="22f12-158">**Sample Application**</span></span>  
  <https://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="22f12-159">Кому необходимо это руководство</span><span class="sxs-lookup"><span data-stu-id="22f12-159">Who should use this guide</span></span>

<span data-ttu-id="22f12-160">Это руководство предназначено главным образом для разработчиков, руководителей отделов разработки и архитекторов, заинтересованных в создании современных веб-приложений с помощью технологий и служб Майкрософт в облаке.</span><span class="sxs-lookup"><span data-stu-id="22f12-160">The audience for this guide is mainly developers, development leads, and architects who are interested in building modern web applications using Microsoft technologies and services in the cloud.</span></span>

<span data-ttu-id="22f12-161">Вторичной аудиторией являются лица, ответственные за принятие технических решений, которые уже знакомы с ASP.NET или Azure и которым требуются сведения о целесообразности обновления до ASP.NET Core для разработки новых и поддержки существующих проектов.</span><span class="sxs-lookup"><span data-stu-id="22f12-161">A secondary audience is technical decision makers who are already familiar ASP.NET or Azure and are looking for information on whether it makes sense to upgrade to ASP.NET Core for new or existing projects.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="22f12-162">Как использовать это руководство</span><span class="sxs-lookup"><span data-stu-id="22f12-162">How you can use this guide</span></span>

<span data-ttu-id="22f12-163">Это руководство было сведено в относительно небольшой документ, в котором основное внимание уделяется созданию веб-приложений с помощью современных технологий .NET и Azure.</span><span class="sxs-lookup"><span data-stu-id="22f12-163">This guide has been condensed into a relatively small document that focuses on building web applications with modern .NET technologies and Azure.</span></span> <span data-ttu-id="22f12-164">Поэтому, чтобы получить базовое представление о таких приложениях и разобраться в соответствующих технических рекомендациях, изучите документ полностью.</span><span class="sxs-lookup"><span data-stu-id="22f12-164">As such, it can be read in its entirety to provide a foundation of understanding such applications and their technical considerations.</span></span> <span data-ttu-id="22f12-165">Это руководство вместе с примером приложения может быть хорошей отправной точкой или полезным справочным документом.</span><span class="sxs-lookup"><span data-stu-id="22f12-165">The guide, along with its sample application, can also serve as a starting point or reference.</span></span> <span data-ttu-id="22f12-166">Используйте приведенный пример приложения в качестве шаблона для собственных приложений, или чтобы увидеть, каким образом можно организовать составные части приложения.</span><span class="sxs-lookup"><span data-stu-id="22f12-166">Use the associated sample application as a template for your own applications, or to see how you might organize your application's component parts.</span></span> <span data-ttu-id="22f12-167">Принимая решение о применении этих вариантов к своему приложению, вы всегда можете обратиться к описанным в руководстве принципам и направлениям архитектуры и технологическим возможностям.</span><span class="sxs-lookup"><span data-stu-id="22f12-167">Refer back to the guide's principles and coverage of architecture and technology options and decision considerations when you're weighing these choices for your own application.</span></span>

<span data-ttu-id="22f12-168">При необходимости вы можете порекомендовать это руководство членам своей команды, чтобы и они были в курсе всех важных аспектов.</span><span class="sxs-lookup"><span data-stu-id="22f12-168">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="22f12-169">Если все заинтересованные лица будут использовать общий набор терминологии и придерживаться основополагающих принципов, архитектурные модели и практики будут применяться более последовательно.</span><span class="sxs-lookup"><span data-stu-id="22f12-169">Having everybody working from a common set of terminology and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="22f12-170">Ссылки</span><span class="sxs-lookup"><span data-stu-id="22f12-170">References</span></span>

- <span data-ttu-id="22f12-171">**Выбор между .NET Core и .NET Framework для серверных приложений**</span><span class="sxs-lookup"><span data-stu-id="22f12-171">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
  [https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server](../../standard/choosing-core-framework-server.md)

>[!div class="step-by-step"]
>[<span data-ttu-id="22f12-172">Вперед</span><span class="sxs-lookup"><span data-stu-id="22f12-172">Next</span></span>](modern-web-applications-characteristics.md)
