---
title: Примеры бизнес-сценариев и вариантов использования бессерверных приложений
description: Ознакомьтесь с бессерверными технологиями, изучая конкретные примеры для разных сценариев — от обработки изображений до поддержки мобильных устройств и конвейеров ETL (извлечения, преобразования и загрузки).
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/17/2020
ms.openlocfilehash: 3cb3b73325fccc327ccf17f7298048f2eeb3577a
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158454"
---
# <a name="serverless-business-scenarios-and-use-cases"></a>Бессерверные сценарии и варианты использования для бизнеса

Существует множество вариантов использования и сценариев применения бессерверных приложений. В этой главе содержатся примеры, иллюстрирующие различные сценарии. Сценарии содержат ссылки на связанные документы и общедоступные репозитории исходного кода. Примеры в этой главе позволяют приступить к созданию и реализации собственных бессерверных решений.

## <a name="big-data-processing"></a>Обработка больших данных

![Схема сопоставления и редукции](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/media/mapreducearchitecture.png)

В этом примере бессерверная операция используется для сопоставления и редукции большого набора данных. Он определяет среднюю скорость такси для ежедневных поездок за 2017 год.

[Обработка больших данных. Бессерверная операция MapReduce в Azure](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/)

## <a name="create-serverless-applications-hands-on-lab"></a>Создание бессерверных приложений (практическое занятие)

Узнайте, как с помощью функций выполнять логику сервера и создавать бессерверные архитектуры.

- Выбор лучшей службы Azure для вашего бизнеса
- Создание Функций Azure
- Использование триггеров
- Цепочка функций
- Длительные рабочие процессы
- Мониторинг
- Разработка, тестирование и развертывание

[Создание бессерверных приложений](https://docs.microsoft.com/learn/paths/create-serverless-applications/)

## <a name="customer-reviews"></a>Отзывы пользователей

В этом примере демонстрируются новые инструменты Функций Azure работы для работы с библиотеками классов C# в Visual Studio. Создайте веб-сайт, на котором пользователи оставляют отзывы о продуктах, сохраняя данные в хранилище BLOB-объектов Azure и CosmosDB. Добавьте функцию Azure для автоматизированной модерации отзывов пользователей с помощью Azure Cognitive Services. Примените очередь службы хранилища Azure, чтобы отделить веб-сайт от функции.

[Приложение для сбора отзывов пользователей на основе Cognitive Services](https://docs.microsoft.com/samples/azure-samples/functions-customer-reviews/customer-reviews-cognitive-services/)

## <a name="docker-linux-image-support"></a>Поддержка образа Docker для Linux

В этом примере показано, как создать `Dockerfile` для сборки и выполнения Функций Azure в контейнере Docker на платформе Linux.

[Функции Azure в Linux](https://docs.microsoft.com/samples/azure-samples/functions-linux-custom-image/azure-functions-on-linux-custom-image-tutorial-sample-project/)

## <a name="file-processing-and-validation"></a>Обработка и проверка файлов

В этом примере выполняется синтаксический анализ набора CSV-файлов, которые могли быть получены от пользователей. В примере проверяется готовность всех необходимых файлов для пакета, а затем проверяется структуру каждого из этих файлов. Здесь представлены разные решения на основе Функций Azure, Logic Apps и Устойчивых функций.

[Обработка и проверка файлов с помощью Функций Azure, Logic Apps и Устойчивых функций](https://docs.microsoft.com/samples/azure-samples/serverless-file-validation/file-processing-and-validation-using-azure-functions-logic-apps-and-durable-functions/)

## <a name="game-data-visualization"></a>Визуализация игровых данных

![Телеметрия игр](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/media/points.png)

Пример того, как разработчик может реализовать в игре решение для визуализации данных в редакторе. Что интересно, подключаемые модули Unreal Engine 4 и Unity используют именно этот пример в качестве основы для серверной части. Компонент службы не имеет никаких сведений о ядре игры.

[Визуализация телеметрии игры в редакторе](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/)

## <a name="graphql"></a>GraphQL

Создание бессерверной функции, которая предоставляет API GraphQL.

[Бессерверные функции для GraphQL](https://github.com/softchris/graphql-workshop-dotnet/blob/master/docs/workshop/4.md)

## <a name="internet-of-things-iot-reliable-edge-relay"></a>Надежный пограничный ретранслятор для Интернета вещей

![Архитектура Интернета вещей](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/media/architecture.png)

В этом примере реализован новый протокол связи, который обеспечивает надежную передачу данных от устройств Интернета вещей к концентратору. Он автоматизирует обнаружение и заполнение пропусков в данных.

[Надежный пограничный ретранслятор для Интернета вещей](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/)

## <a name="microservices-reference-architecture"></a>Эталонная архитектура микрослужб

![Эталонная архитектура](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/media/macro-architecture.png)

Эталонная архитектура, в которой описан процесс принятия решений по проектированию, разработке и доставке приложения Rideshare, создаваемого вымышленной компанией Relecloud. Здесь представлены практические инструкции по настройке и развертыванию всех компонентов архитектуры.

[Эталонная архитектура бессерверных микрослужб](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/)

## <a name="migrate-console-apps-to-serverless"></a>Миграция консольных приложений на бессерверные технологии

Этот пример представляет собой универсальную функцию (`.csx` файл), которую можно использовать для преобразования любого консольного приложения в веб-службу HTTP, размещенную в Функциях Azure. Все, что нужно сделать, — это изменить файл конфигурации и указать входные параметры для передачи в качестве аргументов в `.exe`.

[Запуск консольных приложений в Функциях Azure](https://docs.microsoft.com/samples/azure-samples/functions-dotnet-migrating-console-apps/run-console-apps-on-azure-functions/)

## <a name="serverless-for-mobile"></a>Бессерверные технологии для мобильных приложений

Функции Azure очень легко реализовать и обслуживать, а также они поддерживают доступ по протоколу HTTP. Это отличная основа для реализации API для мобильного приложения. Корпорация Майкрософт предоставляет отличные кроссплатформенные средства для платформ iOS, Android и Windows с Xamarin. Это означает, что Функции Azure и Xamarin отлично работают вместе. В этой статье показано, как реализовать функцию Azure с помощью портала Azure или Visual Studio, а затем создать кросс-платформенный клиент на основе Xamarin.Forms, который будет работать в Android, iOS и Windows.

[Implementing a simple Azure Function with a Xamarin.Forms client](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/) (Реализация простой функции Azure с помощью клиента Xamarin.Forms)

## <a name="serverless-messaging"></a>Обмен сообщениями без использования сервера

В этом примере показано, как использовать шаблон развертывания в Устойчивых функциях для загрузки произвольного числа сообщений в любое количество сеансов или секций. Он поддерживает работу со Служебной шиной, Центрами событий или очередями службы хранилища. Также этот пример позволяет добавить возможность использовать эти сообщения с другой функцией Azure и загружать полученные данные о времени выполнения в другой концентратор событий. Затем данные принимаются в службы аналитики, например в Обозреватель данных Azure.

[Создание и использование сообщений в Функциях Azure с помощью Служебной шины, Центров событий и очередей службы хранилища](https://docs.microsoft.com/samples/azure-samples/durable-functions-producer-consumer/product-consume-messages-az-functions/)

## <a name="recommended-resources"></a>Рекомендуемые ресурсы

- [Функции Azure в Linux](https://docs.microsoft.com/samples/azure-samples/functions-linux-custom-image/azure-functions-on-linux-custom-image-tutorial-sample-project/)
- [Обработка больших данных. Бессерверная операция MapReduce в Azure](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/)
- [Создание бессерверных приложений.](https://docs.microsoft.com/learn/paths/create-serverless-applications/)
- [Приложение для сбора отзывов пользователей на основе Cognitive Services](https://docs.microsoft.com/samples/azure-samples/functions-customer-reviews/customer-reviews-cognitive-services/)
- [Обработка и проверка файлов с помощью Функций Azure, Logic Apps и Устойчивых функций](https://docs.microsoft.com/samples/azure-samples/serverless-file-validation/file-processing-and-validation-using-azure-functions-logic-apps-and-durable-functions/)
- [Implementing a simple Azure Function with a Xamarin.Forms client](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/) (Реализация простой функции Azure с помощью клиента Xamarin.Forms)
- [Визуализация телеметрии игры в редакторе](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/)
- [Надежный пограничный ретранслятор для Интернета вещей](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/)
- [Создание и использование сообщений в Функциях Azure с помощью Служебной шины, Центров событий и очередей службы хранилища](https://docs.microsoft.com/samples/azure-samples/durable-functions-producer-consumer/product-consume-messages-az-functions/)
- [Запуск консольных приложений в Функциях Azure](https://docs.microsoft.com/samples/azure-samples/functions-dotnet-migrating-console-apps/run-console-apps-on-azure-functions/)
- [Бессерверные функции для GraphQL](https://github.com/softchris/graphql-workshop-dotnet/blob/master/docs/workshop/4.md)
- [Эталонная архитектура бессерверных микрослужб](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/)

>[!div class="step-by-step"]
>[Назад](orchestration-patterns.md)
>[Вперед](serverless-conclusion.md)
