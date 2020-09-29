---
title: Примеры бизнес-сценариев и вариантов использования бессерверных приложений
description: Ознакомьтесь с бессерверными технологиями, изучая конкретные примеры для разных сценариев — от обработки изображений до поддержки мобильных устройств и конвейеров ETL (извлечения, преобразования и загрузки).
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/17/2020
ms.openlocfilehash: df76b132579eb3a6d05ce38c94cb9fceb9281aef
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171615"
---
# <a name="serverless-business-scenarios-and-use-cases"></a><span data-ttu-id="e9bb2-103">Бессерверные сценарии и варианты использования для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e9bb2-103">Serverless business scenarios and use cases</span></span>

<span data-ttu-id="e9bb2-104">Существует множество вариантов использования и сценариев применения бессерверных приложений.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-104">There are many use cases and scenarios for serverless applications.</span></span> <span data-ttu-id="e9bb2-105">В этой главе содержатся примеры, иллюстрирующие различные сценарии.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-105">This chapter includes samples that illustrate the different scenarios.</span></span> <span data-ttu-id="e9bb2-106">Сценарии содержат ссылки на связанные документы и общедоступные репозитории исходного кода.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-106">The scenarios include links to related documentation and public source code repositories.</span></span> <span data-ttu-id="e9bb2-107">Примеры в этой главе позволяют приступить к созданию и реализации собственных бессерверных решений.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-107">The samples in this chapter enable you to get started on your own building and implementing serverless solutions.</span></span>

## <a name="big-data-processing"></a><span data-ttu-id="e9bb2-108">Обработка больших данных</span><span class="sxs-lookup"><span data-stu-id="e9bb2-108">Big data processing</span></span>

![Схема сопоставления и редукции](/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/media/mapreducearchitecture.png)

<span data-ttu-id="e9bb2-110">В этом примере бессерверная операция используется для сопоставления и редукции большого набора данных.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-110">This example uses serverless to do a map/reduce operation on a big data set.</span></span> <span data-ttu-id="e9bb2-111">Он определяет среднюю скорость такси для ежедневных поездок за 2017 год.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-111">It determines the average speed of New York Yellow taxi trips per day in 2017.</span></span>

[<span data-ttu-id="e9bb2-112">Обработка больших данных. Бессерверная операция MapReduce в Azure</span><span class="sxs-lookup"><span data-stu-id="e9bb2-112">Big Data Processing: Serverless MapReduce on Azure</span></span>](/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/)

## <a name="create-serverless-applications-hands-on-lab"></a><span data-ttu-id="e9bb2-113">Создание бессерверных приложений (практическое занятие)</span><span class="sxs-lookup"><span data-stu-id="e9bb2-113">Create serverless applications: hands-on lab</span></span>

<span data-ttu-id="e9bb2-114">Узнайте, как с помощью функций выполнять логику сервера и создавать бессерверные архитектуры.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-114">Learn how to use functions to execute server-side logic and build serverless architectures.</span></span>

- <span data-ttu-id="e9bb2-115">Выбор лучшей службы Azure для вашего бизнеса</span><span class="sxs-lookup"><span data-stu-id="e9bb2-115">Choosing the best Azure service for your business</span></span>
- <span data-ttu-id="e9bb2-116">Создание Функций Azure</span><span class="sxs-lookup"><span data-stu-id="e9bb2-116">Creating Azure Functions</span></span>
- <span data-ttu-id="e9bb2-117">Использование триггеров</span><span class="sxs-lookup"><span data-stu-id="e9bb2-117">Using triggers</span></span>
- <span data-ttu-id="e9bb2-118">Цепочка функций</span><span class="sxs-lookup"><span data-stu-id="e9bb2-118">Chaining functions</span></span>
- <span data-ttu-id="e9bb2-119">Длительные рабочие процессы</span><span class="sxs-lookup"><span data-stu-id="e9bb2-119">Long-running workflows</span></span>
- <span data-ttu-id="e9bb2-120">Мониторинг</span><span class="sxs-lookup"><span data-stu-id="e9bb2-120">Monitoring</span></span>
- <span data-ttu-id="e9bb2-121">Разработка, тестирование и развертывание</span><span class="sxs-lookup"><span data-stu-id="e9bb2-121">Development, testing, and deployment</span></span>

[<span data-ttu-id="e9bb2-122">Создание бессерверных приложений</span><span class="sxs-lookup"><span data-stu-id="e9bb2-122">Create serverless applications</span></span>](/learn/paths/create-serverless-applications/)

## <a name="customer-reviews"></a><span data-ttu-id="e9bb2-123">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="e9bb2-123">Customer reviews</span></span>

<span data-ttu-id="e9bb2-124">В этом примере демонстрируются новые инструменты Функций Azure работы для работы с библиотеками классов C# в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-124">This sample showcases the new Azure Functions tooling for C# Class Libraries in Visual Studio.</span></span> <span data-ttu-id="e9bb2-125">Создайте веб-сайт, на котором пользователи оставляют отзывы о продуктах, сохраняя данные в хранилище BLOB-объектов Azure и CosmosDB.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-125">Create a website where customers submit product reviews that are stored in Azure storage blobs and CosmosDB.</span></span> <span data-ttu-id="e9bb2-126">Добавьте функцию Azure для автоматизированной модерации отзывов пользователей с помощью Azure Cognitive Services.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-126">Add an Azure Function to perform automated moderation of the customer reviews using Azure Cognitive Services.</span></span> <span data-ttu-id="e9bb2-127">Примените очередь службы хранилища Azure, чтобы отделить веб-сайт от функции.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-127">Use an Azure storage queue to decouple the website from the function.</span></span>

[<span data-ttu-id="e9bb2-128">Приложение для сбора отзывов пользователей на основе Cognitive Services</span><span class="sxs-lookup"><span data-stu-id="e9bb2-128">Customer Reviews App with Cognitive Services</span></span>](/samples/azure-samples/functions-customer-reviews/customer-reviews-cognitive-services/)

## <a name="docker-linux-image-support"></a><span data-ttu-id="e9bb2-129">Поддержка образа Docker для Linux</span><span class="sxs-lookup"><span data-stu-id="e9bb2-129">Docker Linux image support</span></span>

<span data-ttu-id="e9bb2-130">В этом примере показано, как создать `Dockerfile` для сборки и выполнения Функций Azure в контейнере Docker на платформе Linux.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-130">This sample demonstrates how to create a `Dockerfile` to build and run Azure Functions on a Linux Docker container.</span></span>

[<span data-ttu-id="e9bb2-131">Функции Azure в Linux</span><span class="sxs-lookup"><span data-stu-id="e9bb2-131">Azure Functions on Linux</span></span>](/samples/azure-samples/functions-linux-custom-image/azure-functions-on-linux-custom-image-tutorial-sample-project/)

## <a name="file-processing-and-validation"></a><span data-ttu-id="e9bb2-132">Обработка и проверка файлов</span><span class="sxs-lookup"><span data-stu-id="e9bb2-132">File processing and validation</span></span>

<span data-ttu-id="e9bb2-133">В этом примере выполняется синтаксический анализ набора CSV-файлов, которые могли быть получены от пользователей.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-133">This example parses a set of CSV files from hypothetical customers.</span></span> <span data-ttu-id="e9bb2-134">В примере проверяется готовность всех необходимых файлов для пакета, а затем проверяется структуру каждого из этих файлов.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-134">It ensures that all files required for a customer "batch" are ready, then validates the structure of each file.</span></span> <span data-ttu-id="e9bb2-135">Здесь представлены разные решения на основе Функций Azure, Logic Apps и Устойчивых функций.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-135">Different solutions are presented using Azure Functions, Logic Apps, and Durable Functions.</span></span>

[<span data-ttu-id="e9bb2-136">Обработка и проверка файлов с помощью Функций Azure, Logic Apps и Устойчивых функций</span><span class="sxs-lookup"><span data-stu-id="e9bb2-136">File processing and validation using Azure Functions, Logic Apps, and Durable Functions</span></span>](/samples/azure-samples/serverless-file-validation/file-processing-and-validation-using-azure-functions-logic-apps-and-durable-functions/)

## <a name="game-data-visualization"></a><span data-ttu-id="e9bb2-137">Визуализация игровых данных</span><span class="sxs-lookup"><span data-stu-id="e9bb2-137">Game data visualization</span></span>

![Телеметрия игр](/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/media/points.png)

<span data-ttu-id="e9bb2-139">Пример того, как разработчик может реализовать в игре решение для визуализации данных в редакторе.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-139">An example of how a developer could implement an in-editor data visualization solution for their game.</span></span> <span data-ttu-id="e9bb2-140">Что интересно, подключаемые модули Unreal Engine 4 и Unity используют именно этот пример в качестве основы для серверной части.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-140">In fact, an Unreal Engine 4 Plugin and Unity Plugin were developed using this sample as its backend.</span></span> <span data-ttu-id="e9bb2-141">Компонент службы не имеет никаких сведений о ядре игры.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-141">The service component is game engine agnostic.</span></span>

[<span data-ttu-id="e9bb2-142">Визуализация телеметрии игры в редакторе</span><span class="sxs-lookup"><span data-stu-id="e9bb2-142">In-editor game telemetry visualization</span></span>](/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/)

## <a name="graphql"></a><span data-ttu-id="e9bb2-143">GraphQL</span><span class="sxs-lookup"><span data-stu-id="e9bb2-143">GraphQL</span></span>

<span data-ttu-id="e9bb2-144">Создание бессерверной функции, которая предоставляет API GraphQL.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-144">Create a serverless function that exposes a GraphQL API.</span></span>

[<span data-ttu-id="e9bb2-145">Бессерверные функции для GraphQL</span><span class="sxs-lookup"><span data-stu-id="e9bb2-145">Serverless functions for GraphQL</span></span>](https://github.com/softchris/graphql-workshop-dotnet/blob/master/docs/workshop/4.md)

## <a name="internet-of-things-iot-reliable-edge-relay"></a><span data-ttu-id="e9bb2-146">Надежный пограничный ретранслятор для Интернета вещей</span><span class="sxs-lookup"><span data-stu-id="e9bb2-146">Internet of Things (IoT) reliable edge relay</span></span>

![Архитектура Интернета вещей](/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/media/architecture.png)

<span data-ttu-id="e9bb2-148">В этом примере реализован новый протокол связи, который обеспечивает надежную передачу данных от устройств Интернета вещей к концентратору.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-148">This sample implements a new communication protocol to enable reliable upstream communication from IoT devices.</span></span> <span data-ttu-id="e9bb2-149">Он автоматизирует обнаружение и заполнение пропусков в данных.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-149">It automates data gap detection and backfill.</span></span>

[<span data-ttu-id="e9bb2-150">Надежный пограничный ретранслятор для Интернета вещей</span><span class="sxs-lookup"><span data-stu-id="e9bb2-150">IoT Reliable Edge Relay</span></span>](/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/)

## <a name="microservices-reference-architecture"></a><span data-ttu-id="e9bb2-151">Эталонная архитектура микрослужб</span><span class="sxs-lookup"><span data-stu-id="e9bb2-151">Microservices reference architecture</span></span>

![Эталонная архитектура](/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/media/macro-architecture.png)

<span data-ttu-id="e9bb2-153">Эталонная архитектура, в которой описан процесс принятия решений по проектированию, разработке и доставке приложения Rideshare, создаваемого вымышленной компанией Relecloud.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-153">A reference architecture that walks you through the decision-making process involved in designing, developing, and delivering the Rideshare by Relecloud application (a fictitious company).</span></span> <span data-ttu-id="e9bb2-154">Здесь представлены практические инструкции по настройке и развертыванию всех компонентов архитектуры.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-154">It includes hands-on instructions for configuring and deploying all of the architecture's components.</span></span>

[<span data-ttu-id="e9bb2-155">Эталонная архитектура бессерверных микрослужб</span><span class="sxs-lookup"><span data-stu-id="e9bb2-155">Serverless Microservices reference architecture</span></span>](/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/)

## <a name="migrate-console-apps-to-serverless"></a><span data-ttu-id="e9bb2-156">Миграция консольных приложений на бессерверные технологии</span><span class="sxs-lookup"><span data-stu-id="e9bb2-156">Migrate console apps to serverless</span></span>

<span data-ttu-id="e9bb2-157">Этот пример представляет собой универсальную функцию (`.csx` файл), которую можно использовать для преобразования любого консольного приложения в веб-службу HTTP, размещенную в Функциях Azure.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-157">This sample is a generic function (`.csx` file) that can be used to convert any console application to an HTTP web service in Azure Functions.</span></span> <span data-ttu-id="e9bb2-158">Все, что нужно сделать, — это изменить файл конфигурации и указать входные параметры для передачи в качестве аргументов в `.exe`.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-158">All you have to do is edit a configuration file and specify what input parameters will be passed as arguments to the `.exe`.</span></span>

[<span data-ttu-id="e9bb2-159">Запуск консольных приложений в Функциях Azure</span><span class="sxs-lookup"><span data-stu-id="e9bb2-159">Run Console Apps on Azure Functions</span></span>](/samples/azure-samples/functions-dotnet-migrating-console-apps/run-console-apps-on-azure-functions/)

## <a name="serverless-for-mobile"></a><span data-ttu-id="e9bb2-160">Бессерверные технологии для мобильных приложений</span><span class="sxs-lookup"><span data-stu-id="e9bb2-160">Serverless for mobile</span></span>

<span data-ttu-id="e9bb2-161">Функции Azure очень легко реализовать и обслуживать, а также они поддерживают доступ по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-161">Azure Functions are easy to implement and maintain, and accessible through HTTP.</span></span> <span data-ttu-id="e9bb2-162">Это отличная основа для реализации API для мобильного приложения.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-162">They are a great way to implement an API for a mobile application.</span></span> <span data-ttu-id="e9bb2-163">Корпорация Майкрософт предоставляет отличные кроссплатформенные средства для платформ iOS, Android и Windows с Xamarin.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-163">Microsoft offers great cross-platform tools for iOS, Android, and Windows with Xamarin.</span></span> <span data-ttu-id="e9bb2-164">Это означает, что Функции Azure и Xamarin отлично работают вместе.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-164">As such, Xamarin and Azure Functions are working great together.</span></span> <span data-ttu-id="e9bb2-165">В этой статье показано, как реализовать функцию Azure с помощью портала Azure или Visual Studio, а затем создать кросс-платформенный клиент на основе Xamarin.Forms, который будет работать в Android, iOS и Windows.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-165">This article shows how to implement an Azure Function in the Azure portal or in Visual Studio at first, and build a cross-platform client with Xamarin.Forms running on Android, iOS, and Windows.</span></span>

<span data-ttu-id="e9bb2-166">[Implementing a simple Azure Function with a Xamarin.Forms client](/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/) (Реализация простой функции Azure с помощью клиента Xamarin.Forms)</span><span class="sxs-lookup"><span data-stu-id="e9bb2-166">[Implementing a simple Azure Function with a Xamarin.Forms client](/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)</span></span>

## <a name="serverless-messaging"></a><span data-ttu-id="e9bb2-167">Обмен сообщениями без использования сервера</span><span class="sxs-lookup"><span data-stu-id="e9bb2-167">Serverless messaging</span></span>

<span data-ttu-id="e9bb2-168">В этом примере показано, как использовать шаблон развертывания в Устойчивых функциях для загрузки произвольного числа сообщений в любое количество сеансов или секций.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-168">This sample shows how to utilize Durable Functions' fan-out pattern to load an arbitrary number of messages across any number of sessions/partitions.</span></span> <span data-ttu-id="e9bb2-169">Он поддерживает работу со Служебной шиной, Центрами событий или очередями службы хранилища.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-169">It targets Service Bus, Event Hubs, or Storage Queues.</span></span> <span data-ttu-id="e9bb2-170">Также этот пример позволяет добавить возможность использовать эти сообщения с другой функцией Azure и загружать полученные данные о времени выполнения в другой концентратор событий.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-170">The sample also adds the ability to consume those messages with another Azure Function and load the resulting timing data in to another Event Hub.</span></span> <span data-ttu-id="e9bb2-171">Затем данные принимаются в службы аналитики, например в Обозреватель данных Azure.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-171">The data is then ingested into analytics services like Azure Data Explorer.</span></span>

[<span data-ttu-id="e9bb2-172">Создание и использование сообщений в Функциях Azure с помощью Служебной шины, Центров событий и очередей службы хранилища</span><span class="sxs-lookup"><span data-stu-id="e9bb2-172">Produce and Consume messages through Service Bus, Event Hubs, and Storage Queues with Azure Functions</span></span>](/samples/azure-samples/durable-functions-producer-consumer/product-consume-messages-az-functions/)

## <a name="recommended-resources"></a><span data-ttu-id="e9bb2-173">Рекомендуемые ресурсы</span><span class="sxs-lookup"><span data-stu-id="e9bb2-173">Recommended resources</span></span>

- [<span data-ttu-id="e9bb2-174">Функции Azure в Linux</span><span class="sxs-lookup"><span data-stu-id="e9bb2-174">Azure Functions on Linux</span></span>](/samples/azure-samples/functions-linux-custom-image/azure-functions-on-linux-custom-image-tutorial-sample-project/)
- [<span data-ttu-id="e9bb2-175">Обработка больших данных. Бессерверная операция MapReduce в Azure</span><span class="sxs-lookup"><span data-stu-id="e9bb2-175">Big Data Processing: Serverless MapReduce on Azure</span></span>](/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/)
- [<span data-ttu-id="e9bb2-176">Создание бессерверных приложений.</span><span class="sxs-lookup"><span data-stu-id="e9bb2-176">Create serverless applications</span></span>](/learn/paths/create-serverless-applications/)
- [<span data-ttu-id="e9bb2-177">Приложение для сбора отзывов пользователей на основе Cognitive Services</span><span class="sxs-lookup"><span data-stu-id="e9bb2-177">Customer Reviews App with Cognitive Services</span></span>](/samples/azure-samples/functions-customer-reviews/customer-reviews-cognitive-services/)
- [<span data-ttu-id="e9bb2-178">Обработка и проверка файлов с помощью Функций Azure, Logic Apps и Устойчивых функций</span><span class="sxs-lookup"><span data-stu-id="e9bb2-178">File processing and validation using Azure Functions, Logic Apps, and Durable Functions</span></span>](/samples/azure-samples/serverless-file-validation/file-processing-and-validation-using-azure-functions-logic-apps-and-durable-functions/)
- <span data-ttu-id="e9bb2-179">[Implementing a simple Azure Function with a Xamarin.Forms client](/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/) (Реализация простой функции Azure с помощью клиента Xamarin.Forms)</span><span class="sxs-lookup"><span data-stu-id="e9bb2-179">[Implementing a simple Azure Function with a Xamarin.Forms client](/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)</span></span>
- [<span data-ttu-id="e9bb2-180">Визуализация телеметрии игры в редакторе</span><span class="sxs-lookup"><span data-stu-id="e9bb2-180">In-editor game telemetry visualization</span></span>](/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/)
- [<span data-ttu-id="e9bb2-181">Надежный пограничный ретранслятор для Интернета вещей</span><span class="sxs-lookup"><span data-stu-id="e9bb2-181">IoT Reliable Edge Relay</span></span>](/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/)
- [<span data-ttu-id="e9bb2-182">Создание и использование сообщений в Функциях Azure с помощью Служебной шины, Центров событий и очередей службы хранилища</span><span class="sxs-lookup"><span data-stu-id="e9bb2-182">Produce and Consume messages through Service Bus, Event Hubs, and Storage Queues with Azure Functions</span></span>](/samples/azure-samples/durable-functions-producer-consumer/product-consume-messages-az-functions/)
- [<span data-ttu-id="e9bb2-183">Запуск консольных приложений в Функциях Azure</span><span class="sxs-lookup"><span data-stu-id="e9bb2-183">Run Console Apps on Azure Functions</span></span>](/samples/azure-samples/functions-dotnet-migrating-console-apps/run-console-apps-on-azure-functions/)
- [<span data-ttu-id="e9bb2-184">Бессерверные функции для GraphQL</span><span class="sxs-lookup"><span data-stu-id="e9bb2-184">Serverless functions for GraphQL</span></span>](https://github.com/softchris/graphql-workshop-dotnet/blob/master/docs/workshop/4.md)
- [<span data-ttu-id="e9bb2-185">Эталонная архитектура бессерверных микрослужб</span><span class="sxs-lookup"><span data-stu-id="e9bb2-185">Serverless Microservices reference architecture</span></span>](/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/)

>[!div class="step-by-step"]
><span data-ttu-id="e9bb2-186">[Назад](orchestration-patterns.md)
>[Вперед](serverless-conclusion.md)</span><span class="sxs-lookup"><span data-stu-id="e9bb2-186">[Previous](orchestration-patterns.md)
[Next](serverless-conclusion.md)</span></span>
