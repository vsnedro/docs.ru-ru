---
title: Дополнительные ресурсы по переносу
description: Где команды могут найти ресурсы, помогающие перенести их платформа .NET Framework приложения в .NET Core?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: c6563f4791d133606cb1818a088bff17a315b1f6
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2021
ms.locfileid: "102401883"
---
# <a name="additional-migration-resources"></a>Дополнительные ресурсы по переносу

Когда вы планируете и выполняете миграцию из ASP.NET MVC и (или) веб-API в ASP.NET Core, существует ряд ресурсов, которые могут оказаться полезными за пределами этой книги. Запишите эти данные и используйте их, чтобы помочь вам преодолеть препятствия, возникающие при переходе.

## <a name="official-documentation"></a>Официальная документация

Официальный веб-сайт документации, [docs.Microsoft.com](https://docs.microsoft.com/), содержит самые свежие сведения о версиях, платформах, критических изменениях и вариантах поддержки. В этой книге вы найдете множество ссылок на статьи, но для любой возникшей проблемы часто стоит по крайней мере выполнить быстрый поиск по документации, чтобы узнать, есть ли уже сведения, касающиеся этой проблемы, и предложить решение или обходной путь.

## <a name="github"></a>GitHub

Поскольку .NET Core является проектом с открытым исходным кодом, обнаруживаются многие проблемы, о которых сообщается, обсуждается и исправлена на GitHub. Корпорация Майкрософт имеет несколько организаций GitHub, в которых можно найти репозитории, которые могут оказаться полезными. Частичный список этих организаций и некоторые из общедоступных репозиториев перечислены ниже:

- [Майкрософт](https://github.com/microsoft)
  - [Управление версиями API ASP.NET](https://github.com/microsoft/aspnet-api-versioning)
- [dotnet](https://github.com/dotnet)
  - [ASP.NET Core](https://github.com/dotnet/aspnetcore)
  - [Среда выполнения .NET](https://github.com/dotnet/runtime)
  - [Entity Framework Core](https://github.com/dotnet/efcore)
  - [Язык C#](https://github.com/dotnet/csharplang)
  - [Docs](https://github.com/dotnet/docs)
  - [Примеры документов](https://github.com/dotnet/samples)
  - [Попробуйте преобразовать](https://github.com/dotnet/try-convert)
  - [Помощник по обновлению .NET](https://aka.ms/dotnet-upgrade-assistant)
- [Справочные приложения по архитектуре .NET](https://github.com/dotnet-architecture)
  - [eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing)
  - [eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb)
  - [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers)

При возникновении проблем с миграцией эти репозитории GitHub являются хорошим местом для их сообщения. Группы разработчиков программного продукта проводят проблемы и обычно реагируют на отчеты об ошибках (хотя вопрос «как» может быть более соответствующим образом направлен в Stack Overflow).

## <a name="stack-overflow"></a>Stack Overflow

[Stack overflow](https://stackoverflow.com/) имеет множество сведений в форме предыдущих вопросов и ответов с указанными ответами, с наиболее полезными ответами, которые были указаны первыми и отмечены, если проблема решена. Помимо поиска существующего решения для проблемы, которую вы можете столкнуться, вы можете также задать вопрос самостоятельно и надеюсь на некоторый ответ от сообщества .NET. Не забывайте, что вы можете сократить Поиск с помощью тегов и не забывайте использовать соответствующие теги, если задаюте вопросы, чтобы максимально увеличить вероятность того, что кто-то сможет узнать о вашем вопросе.

## <a name="youtube-channels"></a>Каналы YouTube

В YouTube имеется огромный объем видеоматериалов .NET и .NET Core, который может содержать полезные учебники или пошаговые руководства, охватывающие любые сценарии, которые могут возникнуть. Попробуйте выполнить поиск по отдельности, если другие усилия по поиску справки в Интернете происходят слишком быстро. Вот несколько хороших мест, чтобы приступить к работе:

- [dotnet](https://www.youtube.com/dotnet)
- [Visual Studio](https://www.youtube.com/visualstudio)

## <a name="twitter-gitter-slack-and-other-community-channels"></a>Twitter, gitter, временной резерв и другие каналы сообщества

Вы найдете много других способов подключения разработчиков .NET на [странице сообщества .NET](https://dotnet.microsoft.com/platform/community). Вы также можете присоединиться к [серверу Дотнетеволутион дискорд](https://aka.ms/dotnet-discord). Кроме того, многие группы продуктов и члены группы находятся в Twitter, а также в различных других сообществах. Вы также можете общаться с [автором этой книги в Twitter](https://twitter.com/ardalis) .

## <a name="references"></a>Ссылки

- [Общие сведения о переносе кода в .NET Core из .NET Framework](../../core/porting/index.md)
- [Помощник по обновлению .NET](https://aka.ms/dotnet-upgrade-assistant)
- [Миграция с ASP.NET на ASP.NET Core](../../core/porting/index.md)
- [Ресурсы сообщества .NET](https://dotnet.microsoft.com/platform/community)

>[!div class="step-by-step"]
>[Назад](deployment-strategies.md)
>[Вперед](architectural-differences.md)
