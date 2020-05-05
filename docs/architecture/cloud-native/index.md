---
title: Разработка ориентированных на облако приложений .NET для Azure
description: Руководство по созданию ориентированных на облако приложений, использующих контейнеры, микрослужбы и бессерверные функции Azure.
author: ardalis
ms.date: 04/23/2020
ms.openlocfilehash: 24d5c75fc5d2e5623892e8f83daea52553d13765
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507394"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a><span data-ttu-id="1671d-103">Разработка ориентированных на облако приложений .NET для Azure</span><span class="sxs-lookup"><span data-stu-id="1671d-103">Architecting Cloud Native .NET Applications for Azure</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

![изображение обложки](./media/cover.png)

<span data-ttu-id="1671d-105">ИЗДАТЕЛЬ</span><span class="sxs-lookup"><span data-stu-id="1671d-105">PUBLISHED BY</span></span>

<span data-ttu-id="1671d-106">Подразделение Microsoft Developer Division, команды разработки .NET и Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1671d-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="1671d-107">Подразделение корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1671d-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="1671d-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="1671d-108">One Microsoft Way</span></span>

<span data-ttu-id="1671d-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="1671d-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="1671d-110">&copy; Корпорация Майкрософт (Microsoft Corporation), 2019</span><span class="sxs-lookup"><span data-stu-id="1671d-110">Copyright &copy; 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="1671d-111">Все права защищены.</span><span class="sxs-lookup"><span data-stu-id="1671d-111">All rights reserved.</span></span> <span data-ttu-id="1671d-112">Запрещается полное или частичное воспроизведение или передача настоящей книги в любом виде или любыми средствами без письменного разрешения издателя.</span><span class="sxs-lookup"><span data-stu-id="1671d-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="1671d-113">Эта книга предоставляется на условиях "как есть" и выражает взгляды и мнения автора.</span><span class="sxs-lookup"><span data-stu-id="1671d-113">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="1671d-114">Взгляды, мнения и сведения, содержащиеся в этой книге, включая URL-адреса и другие ссылки на веб-сайты, могут изменяться без уведомления.</span><span class="sxs-lookup"><span data-stu-id="1671d-114">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="1671d-115">Некоторые приведенные в книге примеры служат только для иллюстрации и являются вымышленными.</span><span class="sxs-lookup"><span data-stu-id="1671d-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="1671d-116">Все совпадения с реальными наименованиями, людьми и любыми другими предметами являются непреднамеренными и случайными.</span><span class="sxs-lookup"><span data-stu-id="1671d-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="1671d-117">Microsoft и товарные знаки, перечисленные на странице "Товарные знаки" на сайте https://www.microsoft.com, являются товарными знаками группы компаний Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1671d-117">Microsoft and the trademarks listed at https://www.microsoft.com on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="1671d-118">Mac и macOS являются товарными знаками Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="1671d-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="1671d-119">Логотип Docker с изображением кита является зарегистрированным товарным знаком Docker, Inc. Используется с разрешения.</span><span class="sxs-lookup"><span data-stu-id="1671d-119">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="1671d-120">Все другие наименования и логотипы являются собственностью своих законных владельцев.</span><span class="sxs-lookup"><span data-stu-id="1671d-120">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="1671d-121">Авторы:</span><span class="sxs-lookup"><span data-stu-id="1671d-121">Authors:</span></span>

> <span data-ttu-id="1671d-122">**Роб Веттор (Rob Vettor)**  — главный архитектор облачных систем/IP-архитектор — [thinkingincloudnative.com](http://thinkingincloudnative.com/about/), корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1671d-122">**Rob Vettor**, Principal Cloud System Architect/IP Architect - [thinkingincloudnative.com](http://thinkingincloudnative.com/about/), Microsoft</span></span>
>
> <span data-ttu-id="1671d-123">**Стив Смит (Steve Smith)** , преподаватель и разработчик программного обеспечения, [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="1671d-123">**Steve "ardalis" Smith**, Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="1671d-124">Участники и рецензенты:</span><span class="sxs-lookup"><span data-stu-id="1671d-124">Participants and Reviewers:</span></span>

> <span data-ttu-id="1671d-125">**Цезарь де ла Торре (Cesar De la Torre)** , старший менеджер программ, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1671d-125">**Cesar De la Torre**, Principal Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="1671d-126">**Ниш Анил (Nish Anil)** , старший менеджер программ, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1671d-126">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="1671d-127">**Джереми Ликнесс (Jeremy Likness)** , старший менеджер программ, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1671d-127">**Jeremy Likness**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="1671d-128">**Сесил Филлип (Cecil Phillip)** , старший советник по облачной разработке, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1671d-128">**Cecil Phillip**, Senior Cloud Advocate, Microsoft</span></span>

<span data-ttu-id="1671d-129">Дополнительные сведения о eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="1671d-129">Learn more about eShopOnContainers</span></span>

<span data-ttu-id="1671d-130">Редакторы:</span><span class="sxs-lookup"><span data-stu-id="1671d-130">Editors:</span></span>

> <span data-ttu-id="1671d-131">**Майра Вензел (Maira Wenzel)** , менеджер программ, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1671d-131">**Maira Wenzel**, Program Manager, .NET team, Microsoft</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="1671d-132">Кому необходимо это руководство</span><span class="sxs-lookup"><span data-stu-id="1671d-132">Who should use this guide</span></span>

<span data-ttu-id="1671d-133">Это руководство предназначено главным образом для разработчиков, руководителей отделов разработки и архитекторов, желающих научиться создавать приложения, ориентированные на облако.</span><span class="sxs-lookup"><span data-stu-id="1671d-133">The audience for this guide is mainly developers, development leads, and architects who are interested in learning how to build applications designed for the cloud.</span></span>

<span data-ttu-id="1671d-134">Побочной аудиторией являются лица, принимающие решения технического характера, которым нужно определить, использовать ли ориентацию на облако при создании своих приложений.</span><span class="sxs-lookup"><span data-stu-id="1671d-134">A secondary audience is technical decision-makers who plan to choose whether to build their applications using a cloud-native approach.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="1671d-135">Как использовать это руководство</span><span class="sxs-lookup"><span data-stu-id="1671d-135">How you can use this guide</span></span>

<span data-ttu-id="1671d-136">Это руководство начинается с определения ориентации на облако и представляет эталонное приложение, созданное с применением принципов и технологий ориентации на облако.</span><span class="sxs-lookup"><span data-stu-id="1671d-136">This guide begins by defining cloud native and introducing a reference application built using cloud-native principles and technologies.</span></span> <span data-ttu-id="1671d-137">Помимо этих первых двух глав, оставшаяся часть книги поделена на главы, касающиеся большинства ориентированных на облако приложений.</span><span class="sxs-lookup"><span data-stu-id="1671d-137">Beyond these first two chapters, the rest of the book is broken up into specific chapters focused on topics common to most cloud-native applications.</span></span> <span data-ttu-id="1671d-138">Вы можете перейти к любой из этих глав, чтобы узнать о подходах ориентации на облако.</span><span class="sxs-lookup"><span data-stu-id="1671d-138">You can jump to any of these chapters to learn about cloud-native approaches to:</span></span>

- <span data-ttu-id="1671d-139">Данные и доступ к ним</span><span class="sxs-lookup"><span data-stu-id="1671d-139">Data and data access</span></span>
- <span data-ttu-id="1671d-140">Модели связи</span><span class="sxs-lookup"><span data-stu-id="1671d-140">Communication patterns</span></span>
- <span data-ttu-id="1671d-141">Масштабирование и масштабируемость</span><span class="sxs-lookup"><span data-stu-id="1671d-141">Scaling and scalability</span></span>
- <span data-ttu-id="1671d-142">Устойчивость приложения</span><span class="sxs-lookup"><span data-stu-id="1671d-142">Application resiliency</span></span>
- <span data-ttu-id="1671d-143">Мониторинг и работоспособность</span><span class="sxs-lookup"><span data-stu-id="1671d-143">Monitoring and health</span></span>
- <span data-ttu-id="1671d-144">Идентификация и безопасность</span><span class="sxs-lookup"><span data-stu-id="1671d-144">Identity and security</span></span>
- <span data-ttu-id="1671d-145">DevOps</span><span class="sxs-lookup"><span data-stu-id="1671d-145">DevOps</span></span>

<span data-ttu-id="1671d-146">Руководство доступно как в формате PDF, так и в интерактивном формате.</span><span class="sxs-lookup"><span data-stu-id="1671d-146">This guide is available both in PDF form and online.</span></span> <span data-ttu-id="1671d-147">При необходимости вы можете порекомендовать этот документ членам своей команды или отправить им ссылку на его интернет-версию, чтобы они были в курсе этих аспектов.</span><span class="sxs-lookup"><span data-stu-id="1671d-147">Feel free to forward this document or links to its online version to your team to help ensure common understanding of these topics.</span></span> <span data-ttu-id="1671d-148">В большинстве этих вопросов важную роль играет понимание базовых принципов и шаблонов, а также компромиссов, связанных с соответствующими решениями.</span><span class="sxs-lookup"><span data-stu-id="1671d-148">Most of these topics benefit from a consistent understanding of the underlying principles and patterns, as well as the trade-offs involved in decisions related to these topics.</span></span> <span data-ttu-id="1671d-149">Цель этого документа заключается в том, чтобы предоставить командам и их руководителям сведения, необходимые для принятия взвешенных решений по архитектуре, разработке и размещению приложений.</span><span class="sxs-lookup"><span data-stu-id="1671d-149">Our goal with this document is to equip teams and their leaders with the information they need to make well-informed decisions for their applications' architecture, development, and hosting.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="1671d-150">Вперед</span><span class="sxs-lookup"><span data-stu-id="1671d-150">Next</span></span>](introduction.md)
