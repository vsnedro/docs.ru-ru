---
title: Разработка ориентированных на облако приложений .NET для Azure
description: Руководство по созданию ориентированных на облако приложений, использующих контейнеры, микрослужбы и бессерверные функции Azure.
author: ardalis
ms.date: 05/13/2020
ms.openlocfilehash: b315f097b1584bd93f694c10f36ee7524d7e020a
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144387"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a><span data-ttu-id="a8b81-103">Разработка ориентированных на облако приложений .NET для Azure</span><span class="sxs-lookup"><span data-stu-id="a8b81-103">Architecting Cloud Native .NET Applications for Azure</span></span>

![изображение обложки](./media/cover.png)

<span data-ttu-id="a8b81-105">**Выпуск v.1.0**</span><span class="sxs-lookup"><span data-stu-id="a8b81-105">**EDITION v.1.0**</span></span>

<span data-ttu-id="a8b81-106">ИЗДАТЕЛЬ</span><span class="sxs-lookup"><span data-stu-id="a8b81-106">PUBLISHED BY</span></span>

<span data-ttu-id="a8b81-107">Подразделение Microsoft Developer Division, команды разработки .NET и Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a8b81-107">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="a8b81-108">Подразделение корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a8b81-108">A division of Microsoft Corporation</span></span>

<span data-ttu-id="a8b81-109">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="a8b81-109">One Microsoft Way</span></span>

<span data-ttu-id="a8b81-110">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="a8b81-110">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="a8b81-111">&copy; Корпорация Майкрософт (Microsoft Corporation), 2020.</span><span class="sxs-lookup"><span data-stu-id="a8b81-111">Copyright &copy; 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="a8b81-112">Все права защищены.</span><span class="sxs-lookup"><span data-stu-id="a8b81-112">All rights reserved.</span></span> <span data-ttu-id="a8b81-113">Запрещается полное или частичное воспроизведение или передача настоящей книги в любом виде или любыми средствами без письменного разрешения издателя.</span><span class="sxs-lookup"><span data-stu-id="a8b81-113">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="a8b81-114">Эта книга предоставляется на условиях "как есть" и выражает взгляды и мнения автора.</span><span class="sxs-lookup"><span data-stu-id="a8b81-114">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="a8b81-115">Взгляды, мнения и сведения, содержащиеся в этой книге, включая URL-адреса и другие ссылки на веб-сайты, могут изменяться без уведомления.</span><span class="sxs-lookup"><span data-stu-id="a8b81-115">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="a8b81-116">Некоторые приведенные в книге примеры служат только для иллюстрации и являются вымышленными.</span><span class="sxs-lookup"><span data-stu-id="a8b81-116">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="a8b81-117">Все совпадения с реальными наименованиями, людьми и любыми другими предметами являются непреднамеренными и случайными.</span><span class="sxs-lookup"><span data-stu-id="a8b81-117">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="a8b81-118">Microsoft и товарные знаки, перечисленные на странице "Товарные знаки" на сайте <https://www.microsoft.com>, являются товарными знаками группы компаний Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a8b81-118">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="a8b81-119">Mac и macOS являются товарными знаками Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="a8b81-119">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="a8b81-120">Логотип Docker с изображением кита является зарегистрированным товарным знаком Docker, Inc. Используется с разрешения.</span><span class="sxs-lookup"><span data-stu-id="a8b81-120">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="a8b81-121">Все другие наименования и логотипы являются собственностью своих законных владельцев.</span><span class="sxs-lookup"><span data-stu-id="a8b81-121">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="a8b81-122">Авторы:</span><span class="sxs-lookup"><span data-stu-id="a8b81-122">Authors:</span></span>

> <span data-ttu-id="a8b81-123">**Роб Веттор (Rob Vettor)**  — главный архитектор облачных систем/IP-архитектор — [thinkingincloudnative.com](https://thinkingincloudnative.com/about/), корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a8b81-123">**Rob Vettor**, Principal Cloud System Architect/IP Architect - [thinkingincloudnative.com](https://thinkingincloudnative.com/about/), Microsoft</span></span>
>
> <span data-ttu-id="a8b81-124">**Стив Смит (Steve Smith)** , преподаватель и разработчик программного обеспечения, [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="a8b81-124">**Steve "ardalis" Smith**, Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="a8b81-125">Участники и рецензенты:</span><span class="sxs-lookup"><span data-stu-id="a8b81-125">Participants and Reviewers:</span></span>

> <span data-ttu-id="a8b81-126">**Цезарь де ла Торре (Cesar De la Torre)** , старший менеджер программ, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a8b81-126">**Cesar De la Torre**, Principal Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="a8b81-127">**Ниш Анил (Nish Anil)** , старший менеджер программ, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a8b81-127">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="a8b81-128">**Джереми Ликнесс (Jeremy Likness)** , старший менеджер программ, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a8b81-128">**Jeremy Likness**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="a8b81-129">**Сесил Филлип (Cecil Phillip)** , старший советник по облачной разработке, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a8b81-129">**Cecil Phillip**, Senior Cloud Advocate, Microsoft</span></span>

<span data-ttu-id="a8b81-130">Редакторы:</span><span class="sxs-lookup"><span data-stu-id="a8b81-130">Editors:</span></span>

> <span data-ttu-id="a8b81-131">**Майра Вензел (Maira Wenzel)** , менеджер программ, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a8b81-131">**Maira Wenzel**, Program Manager, .NET team, Microsoft</span></span>

## <a name="version"></a><span data-ttu-id="a8b81-132">Version</span><span class="sxs-lookup"><span data-stu-id="a8b81-132">Version</span></span>

<span data-ttu-id="a8b81-133">Руководство содержит сведения о версии **.NET Core 3.1** и множество дополнений, связанных с тем же "поколением" технологий (то есть, технологий Azure и сторонних производителей), к которому относится выпуск .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="a8b81-133">This guide has been written to cover **.NET Core 3.1** version along with many additional updates related to the same “wave” of technologies (that is, Azure and additional third-party technologies) coinciding in time with the .NET Core 3.1 release.</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="a8b81-134">Кому необходимо это руководство</span><span class="sxs-lookup"><span data-stu-id="a8b81-134">Who should use this guide</span></span>

<span data-ttu-id="a8b81-135">Это руководство предназначено главным образом для разработчиков, руководителей отделов разработки и архитекторов, желающих научиться создавать приложения, ориентированные на облако.</span><span class="sxs-lookup"><span data-stu-id="a8b81-135">The audience for this guide is mainly developers, development leads, and architects who are interested in learning how to build applications designed for the cloud.</span></span>

<span data-ttu-id="a8b81-136">Побочной аудиторией являются лица, принимающие решения технического характера, которым нужно определить, использовать ли ориентацию на облако при создании своих приложений.</span><span class="sxs-lookup"><span data-stu-id="a8b81-136">A secondary audience is technical decision-makers who plan to choose whether to build their applications using a cloud-native approach.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="a8b81-137">Как использовать это руководство</span><span class="sxs-lookup"><span data-stu-id="a8b81-137">How you can use this guide</span></span>

<span data-ttu-id="a8b81-138">Это руководство начинается с определения ориентации на облако и представляет эталонное приложение, созданное с применением принципов и технологий ориентации на облако.</span><span class="sxs-lookup"><span data-stu-id="a8b81-138">This guide begins by defining cloud native and introducing a reference application built using cloud-native principles and technologies.</span></span> <span data-ttu-id="a8b81-139">Помимо этих первых двух глав, оставшаяся часть книги поделена на главы, касающиеся большинства ориентированных на облако приложений.</span><span class="sxs-lookup"><span data-stu-id="a8b81-139">Beyond these first two chapters, the rest of the book is broken up into specific chapters focused on topics common to most cloud-native applications.</span></span> <span data-ttu-id="a8b81-140">Вы можете перейти к любой из этих глав, чтобы узнать о подходах ориентации на облако.</span><span class="sxs-lookup"><span data-stu-id="a8b81-140">You can jump to any of these chapters to learn about cloud-native approaches to:</span></span>

- <span data-ttu-id="a8b81-141">Данные и доступ к ним</span><span class="sxs-lookup"><span data-stu-id="a8b81-141">Data and data access</span></span>
- <span data-ttu-id="a8b81-142">Модели связи</span><span class="sxs-lookup"><span data-stu-id="a8b81-142">Communication patterns</span></span>
- <span data-ttu-id="a8b81-143">Масштабирование и масштабируемость</span><span class="sxs-lookup"><span data-stu-id="a8b81-143">Scaling and scalability</span></span>
- <span data-ttu-id="a8b81-144">Устойчивость приложения</span><span class="sxs-lookup"><span data-stu-id="a8b81-144">Application resiliency</span></span>
- <span data-ttu-id="a8b81-145">Мониторинг и работоспособность</span><span class="sxs-lookup"><span data-stu-id="a8b81-145">Monitoring and health</span></span>
- <span data-ttu-id="a8b81-146">Идентификация и безопасность</span><span class="sxs-lookup"><span data-stu-id="a8b81-146">Identity and security</span></span>
- <span data-ttu-id="a8b81-147">DevOps</span><span class="sxs-lookup"><span data-stu-id="a8b81-147">DevOps</span></span>

<span data-ttu-id="a8b81-148">Руководство доступно как в формате PDF, так и в интерактивном формате.</span><span class="sxs-lookup"><span data-stu-id="a8b81-148">This guide is available both in PDF form and online.</span></span> <span data-ttu-id="a8b81-149">При необходимости вы можете порекомендовать этот документ членам своей команды или отправить им ссылку на его интернет-версию, чтобы они были в курсе этих аспектов.</span><span class="sxs-lookup"><span data-stu-id="a8b81-149">Feel free to forward this document or links to its online version to your team to help ensure common understanding of these topics.</span></span> <span data-ttu-id="a8b81-150">В большинстве этих вопросов важную роль играет понимание базовых принципов и шаблонов, а также компромиссов, связанных с соответствующими решениями.</span><span class="sxs-lookup"><span data-stu-id="a8b81-150">Most of these topics benefit from a consistent understanding of the underlying principles and patterns, as well as the trade-offs involved in decisions related to these topics.</span></span> <span data-ttu-id="a8b81-151">Цель этого документа заключается в том, чтобы предоставить командам и их руководителям сведения, необходимые для принятия взвешенных решений по архитектуре, разработке и размещению приложений.</span><span class="sxs-lookup"><span data-stu-id="a8b81-151">Our goal with this document is to equip teams and their leaders with the information they need to make well-informed decisions for their applications' architecture, development, and hosting.</span></span>

## <a name="send-your-feedback"></a><span data-ttu-id="a8b81-152">Отправить отзыв</span><span class="sxs-lookup"><span data-stu-id="a8b81-152">Send your feedback</span></span>

<span data-ttu-id="a8b81-153">Эта книга и примеры постоянно дополняются, поэтому мы ждем ваших отзывов.</span><span class="sxs-lookup"><span data-stu-id="a8b81-153">This book and related samples are constantly evolving, so your feedback is welcomed!</span></span> <span data-ttu-id="a8b81-154">Если у вас есть комментарии о том, как можно улучшить эту книгу, используйте раздел отзывов в нижней части любой страницы, созданный на основе [проблем GitHub](https://github.com/dotnet/docs/issues).</span><span class="sxs-lookup"><span data-stu-id="a8b81-154">If you have comments about how this book can be improved, use the feedback section at the bottom of any page built on [GitHub issues](https://github.com/dotnet/docs/issues).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="a8b81-155">Вперед</span><span class="sxs-lookup"><span data-stu-id="a8b81-155">Next</span></span>](introduction.md)
