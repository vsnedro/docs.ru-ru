---
title: Модернизация классических приложений для Windows 10 с помощью .NET Core 3.1
description: Сведения о модернизации существующих классических приложений с помощью .NET Core 3.1
ms.date: 05/12/2020
ms.openlocfilehash: 5861f806a9158ef761c47bc23e51327d4e2d0480
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83422665"
---
# <a name="modernizing-desktop-apps-on-windows-10-with-net-core-31"></a><span data-ttu-id="69033-103">Модернизация классических приложений для Windows 10 с помощью .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="69033-103">Modernizing Desktop Apps on Windows 10 with .NET Core 3.1</span></span>

![Снимок экрана, на котором показана обложка электронной книги, посвященной модернизации классических приложений.](./media/modernizing-existing-desktop-apps-ebook-cover.png)

<span data-ttu-id="69033-105">ИЗДАТЕЛЬ</span><span class="sxs-lookup"><span data-stu-id="69033-105">PUBLISHED BY</span></span>

<span data-ttu-id="69033-106">Подразделение Microsoft Developer Division, команды разработки .NET и Visual Studio</span><span class="sxs-lookup"><span data-stu-id="69033-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="69033-107">Подразделение корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="69033-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="69033-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="69033-108">One Microsoft Way</span></span>

<span data-ttu-id="69033-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="69033-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="69033-110">© Корпорация Майкрософт (Microsoft Corporation), 2020 г.</span><span class="sxs-lookup"><span data-stu-id="69033-110">Copyright © 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="69033-111">Все права защищены.</span><span class="sxs-lookup"><span data-stu-id="69033-111">All rights reserved.</span></span> <span data-ttu-id="69033-112">Запрещается полное или частичное воспроизведение или передача настоящей книги в любом виде или любыми средствами без письменного разрешения издателя.</span><span class="sxs-lookup"><span data-stu-id="69033-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="69033-113">Эта книга предоставляется на условиях "как есть" и выражает взгляды и мнения автора.</span><span class="sxs-lookup"><span data-stu-id="69033-113">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="69033-114">Взгляды, мнения и сведения, содержащиеся в этой книге, включая URL-адреса и другие ссылки на веб-сайты, могут изменяться без уведомления.</span><span class="sxs-lookup"><span data-stu-id="69033-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="69033-115">Некоторые приведенные в книге примеры служат только для иллюстрации и являются вымышленными.</span><span class="sxs-lookup"><span data-stu-id="69033-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="69033-116">Все совпадения с реальными наименованиями, людьми и любыми другими предметами являются непреднамеренными и случайными.</span><span class="sxs-lookup"><span data-stu-id="69033-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="69033-117">Microsoft и товарные знаки, перечисленные на странице "Товарные знаки" на сайте <https://www.microsoft.com>, являются товарными знаками группы компаний Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="69033-117">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="69033-118">Mac и macOS являются товарными знаками Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="69033-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="69033-119">Все другие наименования и логотипы являются собственностью своих законных владельцев.</span><span class="sxs-lookup"><span data-stu-id="69033-119">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="69033-120">Соавторы:</span><span class="sxs-lookup"><span data-stu-id="69033-120">Co-Authors:</span></span>

> <span data-ttu-id="69033-121">**Олия Гавриш (Olia Gavrysh)** , руководитель программ, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="69033-121">**Olia Gavrysh**, Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="69033-122">**Мигель Анхель Кастехон Домингес (Miguel Angel Castejón Dominguez)** , архитектор инновационных продуктов, Kabel</span><span class="sxs-lookup"><span data-stu-id="69033-122">**Miguel Angel Castejón Dominguez**, Innovation Architect, Kabel</span></span>

<span data-ttu-id="69033-123">Участники и рецензенты:</span><span class="sxs-lookup"><span data-stu-id="69033-123">Participants and reviewers:</span></span>

> <span data-ttu-id="69033-124">**Майра Вензел (Maira Wenzel)** , старший руководитель программ, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="69033-124">**Maira Wenzel**, Senior Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="69033-125">**Энди де Горже (Andy De Gorge)** , старший разработчик содержимого, группа разработчиков документации по .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="69033-125">**Andy De Gorge**, Senior Content Developer, .NET docs team, Microsoft</span></span>

> <span data-ttu-id="69033-126">**Мигель Рамос (Miguel Ramos)** , старший руководитель программ, команда по платформе разработчиков Windows, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="69033-126">**Miguel Ramos**, Senior Program Manager, Windows Developer Platform team, Microsoft</span></span>

> <span data-ttu-id="69033-127">**Адам Браден (Adam Braden)** , главный руководитель программ, команда платформы разработчиков Windows, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="69033-127">**Adam Braden**, Principal Program Manager, Windows Developer Platform team, Microsoft</span></span>

> <span data-ttu-id="69033-128">**Рикардо Мингес Паблос (Ricardo Minguez Pablos)** , старший руководитель программ, команда Azure IoT, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="69033-128">**Ricardo Minguez Pablos**, Senior Program Manager, Azure IoT team, Microsoft</span></span>

> <span data-ttu-id="69033-129">**Ниш Анил (Nish Anil)** , старший менеджер программ, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="69033-129">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="69033-130">**Бет Масси (Beth Massi)** , старший менеджер по маркетингу продукции, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="69033-130">**Beth Massi**, Senior Product Marketing Manager, Microsoft</span></span>

> <span data-ttu-id="69033-131">**Скотт Хантер (Scott Hunter)** , помощник главного руководителя программ, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="69033-131">**Scott Hunter**, Partner Director Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="69033-132">**Марта Фуэнтес Лара (Marta Fuentes Lara)** , Kabel</span><span class="sxs-lookup"><span data-stu-id="69033-132">**Marta Fuentes Lara**, Kabel</span></span>

> <span data-ttu-id="69033-133">**Рауль Фернандес де Кордоба (Raúl Fernández de Córdoba)** , Kabel</span><span class="sxs-lookup"><span data-stu-id="69033-133">**Raúl Fernández de Córdoba**, Kabel</span></span>

> <span data-ttu-id="69033-134">**Сан Антонио Мануэль Фернáндес Кантос (Antonio Manuel Fernández Cantos)** , Kabel</span><span class="sxs-lookup"><span data-stu-id="69033-134">**Antonio Manuel Fernández Cantos**, Kabel</span></span>

## <a name="introduction"></a><span data-ttu-id="69033-135">Вступление</span><span class="sxs-lookup"><span data-stu-id="69033-135">Introduction</span></span>

<span data-ttu-id="69033-136">Эта книга посвящена стратегиям, которые можно реализовать в целях модернизации существующих классических настольных приложений и внедрения новейших возможностей среды выполнения, языка и платформы.</span><span class="sxs-lookup"><span data-stu-id="69033-136">This book is about strategies you can adopt to move your existing desktop applications through the path of modernization and incorporate the latest runtime, language, and platform features.</span></span> <span data-ttu-id="69033-137">Вы поймете, что уникальной методики нет, так как каждое приложение имеет свои особенности, а у вас есть собственные требования и предпочтения.</span><span class="sxs-lookup"><span data-stu-id="69033-137">You'll discover that there's no unique recipe as each application is different, and so are your requirements and preferences.</span></span> <span data-ttu-id="69033-138">Хорошо, что существуют общие подходы, которые можно применять для добавления новых функций и возможностей в приложения.</span><span class="sxs-lookup"><span data-stu-id="69033-138">The good news is that there are common approaches you can apply to add new features and capabilities to your applications.</span></span> <span data-ttu-id="69033-139">Для внедрения некоторых из них даже не потребуется вносить значительные изменения в код.</span><span class="sxs-lookup"><span data-stu-id="69033-139">Some of them won't even require major modifications of your code.</span></span> <span data-ttu-id="69033-140">В этой книге мы расскажем о работе всех этих функций в фоновом режиме и объясним механизм их реализации.</span><span class="sxs-lookup"><span data-stu-id="69033-140">In this book, we'll reveal how all those features work behind the scenes and explain the mechanics of their implementations.</span></span> <span data-ttu-id="69033-141">Кроме того, вы ознакомитесь с рядом стандартных сценариев модернизации существующих классических приложений, которые помогут вам совершенствовать ваши собственные проекты.</span><span class="sxs-lookup"><span data-stu-id="69033-141">Moreover, you'll find some common scenarios for modernizing existing desktop applications shown in detail so you can find inspiration for evolving your projects.</span></span>

<span data-ttu-id="69033-142">Подход корпорации Майкрософт к модернизации существующих приложений заключается в том, чтобы предоставить вам гибкие возможности для создания собственного настраиваемого решения.</span><span class="sxs-lookup"><span data-stu-id="69033-142">Microsoft's approach to modernizing existing applications is to give you the flexibility to create your own customized path.</span></span> <span data-ttu-id="69033-143">Все стратегии модернизации, описанные в этой книге, являются в основном независимыми.</span><span class="sxs-lookup"><span data-stu-id="69033-143">All the modernization strategies described in this book are mostly independent.</span></span> <span data-ttu-id="69033-144">Вы можете выбрать те, которые подходят для вашего приложения, и не обращать внимания на другие.</span><span class="sxs-lookup"><span data-stu-id="69033-144">You can choose ones that are relevant for your application and skip others that aren't important for you.</span></span> <span data-ttu-id="69033-145">Иными словами, вы можете отобрать необходимые стратегии в нужном сочетании, которое лучше всего соответствует требованиям вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="69033-145">In other words, you can mix and match the strategies to best address your application needs.</span></span>

## <a name="who-should-use-the-book"></a><span data-ttu-id="69033-146">Для кого предназначена эта книга</span><span class="sxs-lookup"><span data-stu-id="69033-146">Who should use the book</span></span>

<span data-ttu-id="69033-147">Мы написали эту книгу для разработчиков и архитекторов решений, стремящихся модернизировать существующие приложения Windows Forms и классические приложения WPF, чтобы использовать преимущества .NET Core и Windows 10.</span><span class="sxs-lookup"><span data-stu-id="69033-147">We wrote this book for developers and solution architects who want to modernize existing Windows Forms and WPF desktop applications to leverage the benefits of .NET Core and Windows 10.</span></span>

<span data-ttu-id="69033-148">Эта книга также может оказаться полезной тем, кто принимает технические решения, например архитекторам корпоративных систем, ведущим разработчикам или руководителям, желающим получить представление о преимуществах обновления существующих классических приложений.</span><span class="sxs-lookup"><span data-stu-id="69033-148">You might also find this book useful if you're a technical decision maker, such as an enterprise architect or a development lead or director who wants an overview of the benefits of updating existing desktop applications.</span></span>

## <a name="how-to-use-the-book"></a><span data-ttu-id="69033-149">Как пользоваться книгой</span><span class="sxs-lookup"><span data-stu-id="69033-149">How to use the book</span></span>

<span data-ttu-id="69033-150">Эта книга отвечает на вопрос о необходимости модернизации существующих приложений и о том, какие преимущества будут вам доступны при использовании NET Core 3.1 и MSIX для достижения этой цели.</span><span class="sxs-lookup"><span data-stu-id="69033-150">This book addresses the "why"—why you might want to modernize your existing applications, and the specific benefits you get from using NET Core 3.1 and MSIX to modernize your desktop apps.</span></span> <span data-ttu-id="69033-151">Содержимое книги предназначено для архитекторов и лиц, принимающих технические решения, которые хотят получить общие сведения, но не ставят перед собой задачу детального изучения вопросов реализации и технических особенностей.</span><span class="sxs-lookup"><span data-stu-id="69033-151">The content of the book is designed for architects and technical decision makers who want an overview, but who don't need to focus on implementation and technical, step-by-step details.</span></span>

<span data-ttu-id="69033-152">В различных главах приводятся примеры фрагментов кода реализации и снимки экранов, а в главе 5 демонстрируется полный процесс миграции на примере нескольких приложений.</span><span class="sxs-lookup"><span data-stu-id="69033-152">Along the different chapters, sample implementation code snippets and screenshots are provided, with chapter 5 devoted to showcase a complete migration process for sample applications.</span></span>

## <a name="what-this-book-doesnt-cover"></a><span data-ttu-id="69033-153">Темы, которые выходят за рамки этой книги</span><span class="sxs-lookup"><span data-stu-id="69033-153">What this book doesn't cover</span></span>

<span data-ttu-id="69033-154">В этой книге рассматривается конкретное подмножество сценариев миграции по принципу lift-and-shift, а также определяется вариант получения преимуществ модернизации без переписывания кода.</span><span class="sxs-lookup"><span data-stu-id="69033-154">This book covers a specific subset of scenarios that are focused on lift-and-shift scenarios, outlining the way to gain the benefits of modernizing without the effort of rewriting code.</span></span>

<span data-ttu-id="69033-155">Эта книга не посвящена разработке современных приложений с помощью .NET Core с нуля или началу работы с Windows Forms и WPF.</span><span class="sxs-lookup"><span data-stu-id="69033-155">This book isn't about developing modern applications with .NET Core from scratch or about getting started with Windows Forms and WPF.</span></span> <span data-ttu-id="69033-156">Она акцентируется на обновлении существующих классических приложений с помощью новейших технологий для разработки классических приложений.</span><span class="sxs-lookup"><span data-stu-id="69033-156">It focuses on how you can update existing desktop applications with the latest technologies for desktop development.</span></span>

## <a name="samples-used-in-this-book"></a><span data-ttu-id="69033-157">Примеры, используемые в этой книге</span><span class="sxs-lookup"><span data-stu-id="69033-157">Samples used in this book</span></span>

<span data-ttu-id="69033-158">Чтобы выделить необходимые этапы проведения модернизации, мы будем использовать пример приложения с именем `eShopModernizing`.</span><span class="sxs-lookup"><span data-stu-id="69033-158">To highlight the necessary steps to perform a modernization, we'll be using a sample application called `eShopModernizing`.</span></span> <span data-ttu-id="69033-159">У этого приложения есть два варианта, — Windows Forms и WPF — и мы пошагово выполним модернизацию каждого из них с помощью .NET Core.</span><span class="sxs-lookup"><span data-stu-id="69033-159">This application has two flavors, Windows Forms and WPF, and we'll show a step-by-step process on how to perform the modernization on both of them to .NET Core.</span></span>

<span data-ttu-id="69033-160">Кроме того, если вы решите пройти пошаговое руководство, вы сможете узнать результаты процесса в репозитории GitHub.</span><span class="sxs-lookup"><span data-stu-id="69033-160">Also, on the GitHub repository for this book, you'll find the results of the process, which you can consult with if you decide to follow the step-by-step tutorial.</span></span>

## <a name="send-your-feedback"></a><span data-ttu-id="69033-161">Отправить отзыв</span><span class="sxs-lookup"><span data-stu-id="69033-161">Send your feedback</span></span>

<span data-ttu-id="69033-162">Эта книга и примеры постоянно дополняются, поэтому мы ждем ваших отзывов.</span><span class="sxs-lookup"><span data-stu-id="69033-162">This book and related samples are constantly evolving, so your feedback is welcomed!</span></span> <span data-ttu-id="69033-163">Если у вас есть комментарии о том, как можно улучшить эту книгу, используйте раздел отзывов в нижней части любой страницы, созданный на основе [проблем GitHub](https://github.com/dotnet/docs/issues).</span><span class="sxs-lookup"><span data-stu-id="69033-163">If you have comments about how this book can be improved, use the feedback section at the bottom of any page built on [GitHub issues](https://github.com/dotnet/docs/issues).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="69033-164">Вперед</span><span class="sxs-lookup"><span data-stu-id="69033-164">Next</span></span>](why-modern-applications.md)
