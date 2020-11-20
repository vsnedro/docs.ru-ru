---
title: Телеметрия пакета SDK для .NET
description: Сведения о функциях телеметрии пакета SDK для .NET, позволяющих собирать сведения об использовании для анализа, а также о собираемых данных и способе отключения этих функций.
author: KathleenDollard
ms.date: 08/27/2019
ms.openlocfilehash: 4f137822c61e1a04eccd28ebd0cd56c04f4a85e2
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2020
ms.locfileid: "94633874"
---
# <a name="net-sdk-telemetry"></a><span data-ttu-id="2f595-103">Телеметрия пакета SDK для .NET</span><span class="sxs-lookup"><span data-stu-id="2f595-103">.NET SDK telemetry</span></span>

<span data-ttu-id="2f595-104">[Пакет SDK для .NET](index.md) включает функцию телеметрии, которая собирает данные об использовании и сведения об исключениях при сбоях .NET CLI.</span><span class="sxs-lookup"><span data-stu-id="2f595-104">The [.NET SDK](index.md) includes a telemetry feature that collects usage data and exception information when the .NET CLI crashes.</span></span> <span data-ttu-id="2f595-105">.NET CLI поставляется с пакетом SDK для .NET и представляет собой набор команд, позволяющих создавать, тестировать и публиковать приложения .NET.</span><span class="sxs-lookup"><span data-stu-id="2f595-105">The .NET CLI comes with the .NET SDK and is the set of verbs that enable you to build, test, and publish your .NET apps.</span></span> <span data-ttu-id="2f595-106">Команде разработчиков .NET важно знать, как используются эти средства, чтобы их можно было улучшить.</span><span class="sxs-lookup"><span data-stu-id="2f595-106">It's important that the .NET team understands how the tools are used so they can be improved.</span></span> <span data-ttu-id="2f595-107">Сведения об ошибках помогают команде решать проблемы и устранять ошибки.</span><span class="sxs-lookup"><span data-stu-id="2f595-107">Information on failures helps the team resolve problems and fix bugs.</span></span>

<span data-ttu-id="2f595-108">Данные публикуются в сводной форме по [лицензии Creative Commons Attribution](https://creativecommons.org/licenses/by/4.0/).</span><span class="sxs-lookup"><span data-stu-id="2f595-108">The collected data is published in aggregate under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span>

## <a name="scope"></a><span data-ttu-id="2f595-109">Область</span><span class="sxs-lookup"><span data-stu-id="2f595-109">Scope</span></span>

<span data-ttu-id="2f595-110">`dotnet` имеет две функции: для запуска приложений и для выполнения команд CLI.</span><span class="sxs-lookup"><span data-stu-id="2f595-110">`dotnet` has two functions: to run apps, and to execute CLI commands.</span></span> <span data-ttu-id="2f595-111">Данные телеметрии *не собираются* при использовании `dotnet` для запуска приложения в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="2f595-111">Telemetry *isn't collected* when using `dotnet` to start an application in the following format:</span></span>

- `dotnet [path-to-app].dll`

<span data-ttu-id="2f595-112">Данные телеметрии *собираются* при использовании [команд CLI .NET](index.md), например:</span><span class="sxs-lookup"><span data-stu-id="2f595-112">Telemetry *is collected* when using any of the [.NET CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet run`

## <a name="how-to-opt-out"></a><span data-ttu-id="2f595-113">Как отключить функцию</span><span class="sxs-lookup"><span data-stu-id="2f595-113">How to opt out</span></span>

<span data-ttu-id="2f595-114">Функция телеметрии пакета SDK для .NET по умолчанию включена.</span><span class="sxs-lookup"><span data-stu-id="2f595-114">The .NET SDK telemetry feature is enabled by default.</span></span> <span data-ttu-id="2f595-115">Чтобы отключить ее, присвойте переменной среды `DOTNET_CLI_TELEMETRY_OPTOUT` значение `1` или `true`.</span><span class="sxs-lookup"><span data-stu-id="2f595-115">To opt out of the telemetry feature, set the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

<span data-ttu-id="2f595-116">При успешной установке программа установки пакета SDK для .NET отправляет единую запись телеметрии.</span><span class="sxs-lookup"><span data-stu-id="2f595-116">A single telemetry entry is also sent by the .NET SDK installer when a successful installation happens.</span></span> <span data-ttu-id="2f595-117">Чтобы отказаться от этого, задайте переменную среды `DOTNET_CLI_TELEMETRY_OPTOUT` перед установкой пакета SDK для .NET.</span><span class="sxs-lookup"><span data-stu-id="2f595-117">To opt out, set the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable before you install the .NET SDK.</span></span>

## <a name="disclosure"></a><span data-ttu-id="2f595-118">Раскрытие информации</span><span class="sxs-lookup"><span data-stu-id="2f595-118">Disclosure</span></span>

<span data-ttu-id="2f595-119">При первом выполнении одной из [команд .NET CLI](index.md) (например, `dotnet build`) пакет SDK для .NET выводит следующий текст.</span><span class="sxs-lookup"><span data-stu-id="2f595-119">The .NET SDK displays text similar to the following when you first run one of the [.NET CLI commands](index.md) (for example, `dotnet build`).</span></span> <span data-ttu-id="2f595-120">Он может немного отличаться в зависимости от используемой версии пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="2f595-120">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="2f595-121">Именно таким образом корпорация Майкрософт уведомляет вас о сборе данных.</span><span class="sxs-lookup"><span data-stu-id="2f595-121">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Telemetry
---------
The .NET tools collect usage data in order to help us improve your experience. The data is collected by Microsoft and shared with the community. You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

<span data-ttu-id="2f595-122">Чтобы отключить отображение этого сообщения и приветственного сообщения .NET, задайте для переменной среды `DOTNET_NOLOGO` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="2f595-122">To disable this message and the .NET welcome message, set the `DOTNET_NOLOGO` environment variable to `true`.</span></span> <span data-ttu-id="2f595-123">Обратите внимание, что эта переменная не влияет на отказ от отправки данных телеметрии.</span><span class="sxs-lookup"><span data-stu-id="2f595-123">Note that this variable has no effect on telemetry opt out.</span></span>

## <a name="data-points"></a><span data-ttu-id="2f595-124">Точки данных</span><span class="sxs-lookup"><span data-stu-id="2f595-124">Data points</span></span>

<span data-ttu-id="2f595-125">Функция телеметрии не собирает персональные данные, например имена пользователей и их адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="2f595-125">The telemetry feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="2f595-126">Она не проверяет код и не извлекает данные уровня проекта, например имя, репозиторий или автора.</span><span class="sxs-lookup"><span data-stu-id="2f595-126">It doesn't scan your code and doesn't extract project-level data, such as name, repository, or author.</span></span> <span data-ttu-id="2f595-127">Данные отправляются по защищенному протоколу на серверы Майкрософт с помощью технологии [Azure Monitor](https://azure.microsoft.com/services/monitor/), хранятся в режиме ограниченного доступа и используются в защищенных системах [хранилища Azure](https://azure.microsoft.com/services/storage/) с соблюдением строгих мер безопасности.</span><span class="sxs-lookup"><span data-stu-id="2f595-127">The data is sent securely to Microsoft servers using [Azure Monitor](https://azure.microsoft.com/services/monitor/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="2f595-128">Мы заботимся о вашей конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="2f595-128">Protecting your privacy is important to us.</span></span> <span data-ttu-id="2f595-129">Если у вас есть подозрения, что функция телеметрии собирает конфиденциальные данные или что мы обрабатываем данные небезопасным либо неподобающим образом, отправьте сообщение о проблеме в репозитории [dotnet/sdk](https://github.com/dotnet/sdk/issues) или по адресу [dotnet@microsoft.com](mailto:dotnet@microsoft.com) для изучения.</span><span class="sxs-lookup"><span data-stu-id="2f595-129">If you suspect the telemetry is collecting sensitive data or the data is being insecurely or inappropriately handled, file an issue in the [dotnet/sdk](https://github.com/dotnet/sdk/issues) repository or send an email to [dotnet@microsoft.com](mailto:dotnet@microsoft.com) for investigation.</span></span>

<span data-ttu-id="2f595-130">Функция телеметрии собирает следующие данные:</span><span class="sxs-lookup"><span data-stu-id="2f595-130">The telemetry feature collects the following data:</span></span>

| <span data-ttu-id="2f595-131">Версии пакета SDK</span><span class="sxs-lookup"><span data-stu-id="2f595-131">SDK versions</span></span> | <span data-ttu-id="2f595-132">Данные</span><span class="sxs-lookup"><span data-stu-id="2f595-132">Data</span></span> |
|--------------|------|
| <span data-ttu-id="2f595-133">Все</span><span class="sxs-lookup"><span data-stu-id="2f595-133">All</span></span>          | <span data-ttu-id="2f595-134">Метка времени вызова.</span><span class="sxs-lookup"><span data-stu-id="2f595-134">Timestamp of invocation.</span></span> |
| <span data-ttu-id="2f595-135">Все</span><span class="sxs-lookup"><span data-stu-id="2f595-135">All</span></span>          | <span data-ttu-id="2f595-136">Вызываемая команда (например, build), хэшируется с версии 2.1.</span><span class="sxs-lookup"><span data-stu-id="2f595-136">Command invoked (for example, "build"), hashed starting in 2.1.</span></span> |
| <span data-ttu-id="2f595-137">Все</span><span class="sxs-lookup"><span data-stu-id="2f595-137">All</span></span>          | <span data-ttu-id="2f595-138">Состоящий из трех октетов IP-адрес, используемый для определения географического местоположения.</span><span class="sxs-lookup"><span data-stu-id="2f595-138">Three octet IP address used to determine the geographical location.</span></span> |
| <span data-ttu-id="2f595-139">Все</span><span class="sxs-lookup"><span data-stu-id="2f595-139">All</span></span>          | <span data-ttu-id="2f595-140">Операционная система и ее версия.</span><span class="sxs-lookup"><span data-stu-id="2f595-140">Operating system and version.</span></span> |
| <span data-ttu-id="2f595-141">Все</span><span class="sxs-lookup"><span data-stu-id="2f595-141">All</span></span>          | <span data-ttu-id="2f595-142">Идентификатор среды выполнения (RID), в которой работает пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="2f595-142">Runtime ID (RID) the SDK is running on.</span></span> |
| <span data-ttu-id="2f595-143">Все</span><span class="sxs-lookup"><span data-stu-id="2f595-143">All</span></span>          | <span data-ttu-id="2f595-144">Версия пакета SDK для .NET.</span><span class="sxs-lookup"><span data-stu-id="2f595-144">.NET SDK version.</span></span> |
| <span data-ttu-id="2f595-145">Все</span><span class="sxs-lookup"><span data-stu-id="2f595-145">All</span></span>          | <span data-ttu-id="2f595-146">Профиль телеметрии: необязательное значение используется только при явном включении пользователем и внутри корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2f595-146">Telemetry profile: an optional value only used with explicit user opt-in and used internally at Microsoft.</span></span> |
| <span data-ttu-id="2f595-147">>= 2.0</span><span class="sxs-lookup"><span data-stu-id="2f595-147">>=2.0</span></span>        | <span data-ttu-id="2f595-148">Аргументы и параметры команды: собираются только известные аргументы и параметры (но не произвольные строки).</span><span class="sxs-lookup"><span data-stu-id="2f595-148">Command arguments and options: several arguments and options are collected (not arbitrary strings).</span></span> <span data-ttu-id="2f595-149">См. раздел о [собираемых параметрах](#collected-options).</span><span class="sxs-lookup"><span data-stu-id="2f595-149">See [collected options](#collected-options).</span></span> <span data-ttu-id="2f595-150">Хэшируется после версии 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="2f595-150">Hashed after 2.1.300.</span></span> |
| <span data-ttu-id="2f595-151">>= 2.0</span><span class="sxs-lookup"><span data-stu-id="2f595-151">>=2.0</span></span>         | <span data-ttu-id="2f595-152">выполняется ли пакет SDK в контейнере;</span><span class="sxs-lookup"><span data-stu-id="2f595-152">Whether the SDK is running in a container.</span></span> |
| <span data-ttu-id="2f595-153">>= 2.0</span><span class="sxs-lookup"><span data-stu-id="2f595-153">>=2.0</span></span>         | <span data-ttu-id="2f595-154">Целевые платформы (из события `TargetFramework`), хэшируются начиная с версии 2.1.</span><span class="sxs-lookup"><span data-stu-id="2f595-154">Target frameworks (from the `TargetFramework` event), hashed starting in 2.1.</span></span> |
| <span data-ttu-id="2f595-155">>= 2.0</span><span class="sxs-lookup"><span data-stu-id="2f595-155">>=2.0</span></span>         | <span data-ttu-id="2f595-156">Адрес управления доступом к среде передачи данных (MAC-адрес) с хэшированием (SHA256).</span><span class="sxs-lookup"><span data-stu-id="2f595-156">Hashed Media Access Control (MAC) address (SHA256).</span></span> |
| <span data-ttu-id="2f595-157">>= 2.0</span><span class="sxs-lookup"><span data-stu-id="2f595-157">>=2.0</span></span>         | <span data-ttu-id="2f595-158">хэшированный текущий рабочий каталог.</span><span class="sxs-lookup"><span data-stu-id="2f595-158">Hashed current working directory.</span></span> |
| <span data-ttu-id="2f595-159">>= 2.0</span><span class="sxs-lookup"><span data-stu-id="2f595-159">>=2.0</span></span>         | <span data-ttu-id="2f595-160">Отчет об успешном выполнении установки с хэшированным именем EXE-файла установщика.</span><span class="sxs-lookup"><span data-stu-id="2f595-160">Install success report, with hashed installer exe filename.</span></span> |
| <span data-ttu-id="2f595-161">>= 2.1.300</span><span class="sxs-lookup"><span data-stu-id="2f595-161">>=2.1.300</span></span>     | <span data-ttu-id="2f595-162">Версия ядра.</span><span class="sxs-lookup"><span data-stu-id="2f595-162">Kernel version.</span></span> |
| <span data-ttu-id="2f595-163">>= 2.1.300</span><span class="sxs-lookup"><span data-stu-id="2f595-163">>=2.1.300</span></span>     | <span data-ttu-id="2f595-164">Выпуск или версия libc.</span><span class="sxs-lookup"><span data-stu-id="2f595-164">Libc release/version.</span></span> |
| <span data-ttu-id="2f595-165">>= 3.0.100</span><span class="sxs-lookup"><span data-stu-id="2f595-165">>=3.0.100</span></span>     | <span data-ttu-id="2f595-166">Были ли перенаправлены выходные данные (true или false).</span><span class="sxs-lookup"><span data-stu-id="2f595-166">Whether the output was redirected (true or false).</span></span> |
| <span data-ttu-id="2f595-167">>= 3.0.100</span><span class="sxs-lookup"><span data-stu-id="2f595-167">>=3.0.100</span></span>     | <span data-ttu-id="2f595-168">При сбое интерфейса командной строки или пакета SDK тип исключения и его трассировка стека (в отправляемую трассировку стека включается только код CLI или SDK).</span><span class="sxs-lookup"><span data-stu-id="2f595-168">On a CLI/SDK crash, the exception type and its stack trace (only CLI/SDK code is included in the stack trace sent).</span></span> <span data-ttu-id="2f595-169">Дополнительные сведения см. в разделе [Сбор данных телеметрии об исключениях при сбоях .NET CLI и SDK](#net-clisdk-crash-exception-telemetry-collected).</span><span class="sxs-lookup"><span data-stu-id="2f595-169">For more information, see [.NET CLI/SDK crash exception telemetry collected](#net-clisdk-crash-exception-telemetry-collected).</span></span> |

### <a name="collected-options"></a><span data-ttu-id="2f595-170">Собираемые параметры</span><span class="sxs-lookup"><span data-stu-id="2f595-170">Collected options</span></span>

<span data-ttu-id="2f595-171">Некоторые команды отправляют дополнительные данные.</span><span class="sxs-lookup"><span data-stu-id="2f595-171">Certain commands send additional data.</span></span> <span data-ttu-id="2f595-172">Подмножество команд отправляет первый аргумент:</span><span class="sxs-lookup"><span data-stu-id="2f595-172">A subset of commands sends the first argument:</span></span>

| <span data-ttu-id="2f595-173">Команда</span><span class="sxs-lookup"><span data-stu-id="2f595-173">Command</span></span>               | <span data-ttu-id="2f595-174">Данные первого аргумента отправлены</span><span class="sxs-lookup"><span data-stu-id="2f595-174">First argument data sent</span></span>                |
|-----------------------|-----------------------------------------|
| `dotnet help <arg>`   | <span data-ttu-id="2f595-175">Запрашивается справка по командам.</span><span class="sxs-lookup"><span data-stu-id="2f595-175">The command help is being queried for.</span></span>  |
| `dotnet new <arg>`    | <span data-ttu-id="2f595-176">Имя шаблона (хэшированное).</span><span class="sxs-lookup"><span data-stu-id="2f595-176">The template name (hashed).</span></span>             |
| `dotnet add <arg>`    | <span data-ttu-id="2f595-177">Слово `package` или `reference`.</span><span class="sxs-lookup"><span data-stu-id="2f595-177">The word `package` or `reference`.</span></span>      |
| `dotnet remove <arg>` | <span data-ttu-id="2f595-178">Слово `package` или `reference`.</span><span class="sxs-lookup"><span data-stu-id="2f595-178">The word `package` or `reference`.</span></span>      |
| `dotnet list <arg>`   | <span data-ttu-id="2f595-179">Слово `package` или `reference`.</span><span class="sxs-lookup"><span data-stu-id="2f595-179">The word `package` or `reference`.</span></span>      |
| `dotnet sln <arg>`    | <span data-ttu-id="2f595-180">Слово `add`, `list` или `remove`.</span><span class="sxs-lookup"><span data-stu-id="2f595-180">The word `add`, `list`, or `remove`.</span></span>    |
| `dotnet nuget <arg>`  | <span data-ttu-id="2f595-181">Слово `delete`, `locals` или `push`.</span><span class="sxs-lookup"><span data-stu-id="2f595-181">The word `delete`, `locals`, or `push`.</span></span> |

<span data-ttu-id="2f595-182">Подмножество команд отправляет выбранные параметры, если они используются, а также их значения:</span><span class="sxs-lookup"><span data-stu-id="2f595-182">A subset of commands sends selected options if they're used, along with their values:</span></span>

| <span data-ttu-id="2f595-183">Параметр</span><span class="sxs-lookup"><span data-stu-id="2f595-183">Option</span></span>                  | <span data-ttu-id="2f595-184">Команды</span><span class="sxs-lookup"><span data-stu-id="2f595-184">Commands</span></span>                                                                                       |
|-------------------------|------------------------------------------------------------------------------------------------|
| `--verbosity`           | <span data-ttu-id="2f595-185">Все команды</span><span class="sxs-lookup"><span data-stu-id="2f595-185">All commands</span></span>                                                                                   |
| `--language`            | `dotnet new`                                                                                   |
| `--configuration`       | <span data-ttu-id="2f595-186">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`</span><span class="sxs-lookup"><span data-stu-id="2f595-186">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`</span></span>                  |
| `--framework`           | <span data-ttu-id="2f595-187">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest`</span><span class="sxs-lookup"><span data-stu-id="2f595-187">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest`</span></span> |
| `--runtime`             | <span data-ttu-id="2f595-188">`dotnet build`, `dotnet publish`</span><span class="sxs-lookup"><span data-stu-id="2f595-188">`dotnet build`,  `dotnet publish`</span></span>                                                              |
| `--platform`            | `dotnet vstest`                                                                                |
| `--logger`              | `dotnet vstest`                                                                                |
| `--sdk-package-version` | `dotnet migrate`                                                                               |

<span data-ttu-id="2f595-189">За исключением `--verbosity` и `--sdk-package-version` все остальные значения хэшируются, начиная с пакета SDK для .NET Core 2.1.100.</span><span class="sxs-lookup"><span data-stu-id="2f595-189">Except for `--verbosity` and `--sdk-package-version`, all the other values are hashed starting with .NET Core 2.1.100 SDK.</span></span>

## <a name="net-clisdk-crash-exception-telemetry-collected"></a><span data-ttu-id="2f595-190">Сбор данных телеметрии об исключениях при сбоях .NET CLI и SDK</span><span class="sxs-lookup"><span data-stu-id="2f595-190">.NET CLI/SDK crash exception telemetry collected</span></span>

<span data-ttu-id="2f595-191">В случае сбоя .NET CLI или пакета SDK он собирает имя исключения и трассировку стека кода CLI/SDK.</span><span class="sxs-lookup"><span data-stu-id="2f595-191">If the .NET CLI/SDK crashes, it collects the name of the exception and stack trace of the CLI/SDK code.</span></span> <span data-ttu-id="2f595-192">Эти сведения собираются для оценки проблем и улучшения качества пакета SDK для .NET и интерфейса командной строки.</span><span class="sxs-lookup"><span data-stu-id="2f595-192">This information is collected to assess problems and improve the quality of the .NET SDK and CLI.</span></span> <span data-ttu-id="2f595-193">В этой статье приводятся сведения о данных, которые мы собираем.</span><span class="sxs-lookup"><span data-stu-id="2f595-193">This article provides information about the data we collect.</span></span> <span data-ttu-id="2f595-194">Кроме того, она содержит советы, помогающие пользователям, создающим собственную версию пакета SDK для .NET, избежать случайного раскрытия персональных или конфиденциальных сведений.</span><span class="sxs-lookup"><span data-stu-id="2f595-194">It also provides tips on how users building their own version of the .NET SDK can avoid inadvertent disclosure of personal or sensitive information.</span></span>

### <a name="types-of-collected-data"></a><span data-ttu-id="2f595-195">Типы собираемых данных</span><span class="sxs-lookup"><span data-stu-id="2f595-195">Types of collected data</span></span>

<span data-ttu-id="2f595-196">.NET CLI собирает сведения только об исключениях CLI/SDK, а не об исключениях в приложении.</span><span class="sxs-lookup"><span data-stu-id="2f595-196">.NET CLI collects information for CLI/SDK exceptions only, not exceptions in your application.</span></span> <span data-ttu-id="2f595-197">Собранные данные содержат имя исключения и трассировку стека.</span><span class="sxs-lookup"><span data-stu-id="2f595-197">The collected data contains the name of the exception and the stack trace.</span></span> <span data-ttu-id="2f595-198">Эта трассировка стека относится к коду CLI или пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="2f595-198">This stack trace is of CLI/SDK code.</span></span>

<span data-ttu-id="2f595-199">В следующем примере показан тип собираемых данных:</span><span class="sxs-lookup"><span data-stu-id="2f595-199">The following example shows the kind of data that is collected:</span></span>

```console
System.IO.IOException
at System.ConsolePal.WindowsConsoleStream.Write(Byte[] buffer, Int32 offset, Int32 count)
at System.IO.StreamWriter.Flush(Boolean flushStream, Boolean flushEncoder)
at System.IO.StreamWriter.Write(Char[] buffer)
at System.IO.TextWriter.WriteLine()
at System.IO.TextWriter.SyncTextWriter.WriteLine()
at Microsoft.DotNet.Cli.Utils.Reporter.WriteLine()
at Microsoft.DotNet.Tools.Run.RunCommand.EnsureProjectIsBuilt()
at Microsoft.DotNet.Tools.Run.RunCommand.Execute()
at Microsoft.DotNet.Tools.Run.RunCommand.Run(String[] args)
at Microsoft.DotNet.Cli.Program.ProcessArgs(String[] args, ITelemetry telemetryClient)
at Microsoft.DotNet.Cli.Program.Main(String[] args)
```

### <a name="avoid-inadvertent-disclosure-of-information"></a><span data-ttu-id="2f595-200">Избегайте случайного разглашения информации</span><span class="sxs-lookup"><span data-stu-id="2f595-200">Avoid inadvertent disclosure of information</span></span>

<span data-ttu-id="2f595-201">Участники .NET и все остальные, кто использует версию пакета SDK для .NET, которую они создали сами, должны учитывать путь к исходному коду пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="2f595-201">.NET contributors and anyone else running a version of the .NET SDK that they built themselves should consider the path to their SDK source code.</span></span> <span data-ttu-id="2f595-202">Если сбой происходит при использовании пакета SDK для .NET, который является пользовательской сборкой отладки или настроен с помощью файлов пользовательских символов сборки, путь к исходному файлу пакета SDK с компьютера сборки собирается как часть трассировки стека и не хэшируется.</span><span class="sxs-lookup"><span data-stu-id="2f595-202">If a crash occurs while using a .NET SDK that is a custom debug build or configured with custom build symbol files, the SDK source file path from the build machine is collected as part of the stack trace and isn't hashed.</span></span>

<span data-ttu-id="2f595-203">По этой причине пользовательские сборки пакета SDK для .NET не должны размещаться в каталогах, имена путей которых раскрывают персональные или конфиденциальные сведения.</span><span class="sxs-lookup"><span data-stu-id="2f595-203">Because of this, custom builds of the .NET SDK shouldn't be located in directories whose path names expose personal or sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f595-204">См. также</span><span class="sxs-lookup"><span data-stu-id="2f595-204">See also</span></span>

- [<span data-ttu-id="2f595-205">Данные телеметрии .NET CLI</span><span class="sxs-lookup"><span data-stu-id="2f595-205">.NET CLI Telemetry Data</span></span>](https://dotnet.microsoft.com/platform/telemetry)
- [<span data-ttu-id="2f595-206">Справочные материалы по телеметрии (репозиторий dotnet/sdk)</span><span class="sxs-lookup"><span data-stu-id="2f595-206">Telemetry reference source (dotnet/sdk repository)</span></span>](https://github.com/dotnet/sdk/tree/master/src/Cli/dotnet/Telemetry)
