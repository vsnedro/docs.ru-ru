---
title: Сравнение использования Razor в ASP.NET MVC и ASP.NET Core
description: Чем Razor отличается между ASP.NET MVC и ASP.NET Core?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: a9f7fa2e6b8c0c6bf61c743cf8c956b1ad09713c
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401720"
---
# <a name="compare-razor-usage-in-aspnet-mvc-and-aspnet-core"></a>Сравнение использования Razor в ASP.NET MVC и ASP.NET Core

Базовый синтаксис Razor не существенно изменился между ASP.NET MVC и ASP.NET Core. Однако существуют некоторые отличия, такие как ввод [вспомогательных функций тегов](/aspnet/core/mvc/views/tag-helpers/intro) и Razor Pages, которые следует учитывать при миграции. Если приложение активно использует пользовательские функции Razor, обратитесь к [Справочнику по синтаксис Razor для ASP.NET Core](/aspnet/core/razor-pages) , чтобы узнать, какие изменения могут потребоваться при миграции на ASP.NET Core.

## <a name="tag-helpers"></a>Вспомогательные функции тегов

Вспомогательные функции тегов позволяют серверному коду участвовать в создании и отрисовке HTML-элементов в файлах Razor. Они предлагают множество преимуществ по сравнению со вспомогательными классами HTML и должны использоваться вместо вспомогательных функций HTML везде, где это возможно. Они предоставляют удобный для HTML процесс разработки, поскольку они выглядят как стандартные HTML и игнорируются большинством средств, предназначенных для редактирования HTML. В _Visual Studio_ имеется широкая поддержка IntelliSense для создания разметки HTML и Razor с помощью вспомогательных функций тегов. Вспомогательные функции тегов могут обеспечить простое или сложное поведение из декларативной разметки в файлах Razor.

## <a name="razor-pages"></a>Razor Pages

Razor Pages предлагают альтернативы контроллерам, действиям и представлениям для приложений на основе страниц и форм. [В этой главе Razor Pages было сравнивалось с ASP.NET MVC ранее](./comparing-razor-pages-aspnet-mvc.md).

## <a name="references"></a>Ссылки

- [Миграция с ASP.NET MVC на ASP.NET Core MVC: контроллеры и представления](/aspnet/core/migration/mvc#migrate-controllers-and-views)
- [Вспомогательные функции тегов в ASP.NET Core](/aspnet/core/mvc/views/tag-helpers/intro)
- [Введение в Razor Pages в ASP.NET Core](/aspnet/core/razor-pages)
- [Справочник по синтаксису Razor для ASP.NET Core](/aspnet/core/razor-pages)

>[!div class="step-by-step"]
>[Назад](controller-differences.md)
>[Вперед](signalr-differences.md)
