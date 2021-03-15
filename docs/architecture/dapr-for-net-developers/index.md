---
title: Dapr для разработчиков .NET
description: Руководство для разработчиков .NET, в котором приводятся общие сведения о среде Microsoft Distributed Apps Runtime с открытым кодом и рекомендации по ее эффективному использованию.
author: robvet
ms.date: 02/07/2021
ms.openlocfilehash: fc38dd1a98570cc4d2b367d272a107e3ad67ead9
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2021
ms.locfileid: "102206572"
---
# <a name="dapr-for-net-developers"></a>Dapr для разработчиков .NET

![изображение обложки](./media/cover.png)

**ПРЕДВАРИТЕЛЬНЫЙ ВЫПУСК**

ИЗДАТЕЛЬ

Отдел разработки Майкрософт, команды .NET и Azure Incubations

Подразделение корпорации Майкрософт

One Microsoft Way

Redmond, Washington 98052-6399

&copy; Корпорация Майкрософт (Microsoft Corporation), 2021.

Все права защищены. Запрещается полное или частичное воспроизведение или передача настоящей книги в любом виде или любыми средствами без письменного разрешения издателя.

Эта книга предоставляется на условиях "как есть" и выражает взгляды и мнения автора. Взгляды, мнения и сведения, содержащиеся в этой книге, включая URL-адреса и другие ссылки на веб-сайты, могут изменяться без уведомления.

Некоторые приведенные в книге примеры служат только для иллюстрации и являются вымышленными. Все совпадения с реальными наименованиями, людьми и любыми другими предметами являются непреднамеренными и случайными.

Microsoft и товарные знаки, перечисленные на странице "Товарные знаки" на сайте <https://www.microsoft.com>, являются товарными знаками группы компаний Майкрософт.

Mac и macOS являются товарными знаками Apple Inc.

Логотип Docker с изображением кита является зарегистрированным товарным знаком Docker, Inc. Используется с разрешения.

Все другие наименования и логотипы являются собственностью своих законных владельцев.

Авторы:

> **Роб Веттор** (Rob Vettor) — главный архитектор облачных решений, [thinkingincloudnative.com](https://thinkingincloudnative.com/about/), корпорация Майкрософт
>
> **Зандер Моленкамп** (Sander Molenkamp) — главный архитектор облачных решений/Microsoft MVP, [sandermolenkamp.com](https://www.sandermolenkamp.com), [Info Support](https://www.infosupport.com/en/)
>
> **Эдвин ван Вейк** (Edwin van Wijk), главный архитектор решений/Microsoft MVP, [defaultconstructor.com](https://defaultconstructor.com), [Info Support](https://www.infosupport.com/en/)

Участники и рецензенты:

> **Марк Руссинович** (Mark Russinovich), технический директор и технический специалист по Azure, управление по техническим вопросам Azure, корпорация Майкрософт
>
> **Ниш Анил (Nish Anil)** , старший менеджер программ, команда .NET, корпорация Майкрософт
>
> **Марк Фасселл** (Mark Fussell), главный руководитель программы, Azure Incubations, корпорация Майкрософт
>
> **Ярон Шнайдер** (Yaron Schneider), главный разработчик, Azure Incubations, корпорация Майкрософт
>
> **Ори Зохар** (Ori Zohar), старший руководитель программы, Azure Incubations, корпорация Майкрософт

Редакторы:

> **Дэвид Пайн** (David Pine), старший разработчик содержимого, команда .NET, корпорация Майкрософт
>
> **Майра Вензел (Maira Wenzel)** , старший руководитель программ, команда .NET, корпорация Майкрософт

## <a name="version"></a>Версия

Это руководство посвящено версии **Dapr 1.0**. Примеры .NET Core созданы на базе **.NET Core 3.1**.

## <a name="who-should-use-this-guide"></a>Кому необходимо это руководство

Это руководство предназначено главным образом для разработчиков, руководителей отделов разработки и архитекторов, желающих научиться создавать приложения, ориентированные на облако.

Побочной аудиторией являются лица, принимающие решения технического характера, которым нужно определить, использовать ли ориентацию на облако при создании своих приложений.

## <a name="how-you-can-use-this-guide"></a>Как использовать это руководство

Руководство доступно как в формате [PDF](https://aka.ms/dapr-ebook), так и в Интернете. При необходимости вы можете порекомендовать этот документ членам своей команды или отправить им ссылку на его интернет-версию, чтобы они были в курсе этих аспектов. В большинстве этих вопросов важную роль играет понимание базовых принципов и шаблонов, а также компромиссов, связанных с соответствующими решениями. Цель этого документа заключается в том, чтобы предоставить командам и их руководителям сведения, необходимые для принятия взвешенных решений по архитектуре, разработке и размещению приложений.

## <a name="send-your-feedback"></a>Отправить отзыв

Эта книга и примеры постоянно дополняются, поэтому мы ждем ваших отзывов. Если у вас есть комментарии о том, как можно улучшить эту книгу, используйте раздел отзывов в нижней части любой страницы, созданный на основе [проблем GitHub](https://github.com/dotnet/docs/issues).

>[!div class="step-by-step"]
>[Вперед](foreword.md)