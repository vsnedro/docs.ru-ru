---
title: Функции Azure — бессерверные приложения
description: Функции Azure предоставляют бессерверные возможности на нескольких языках (C#, JavaScript, Java) и платформах для обеспечения управляемого событиями кода мгновенного масштабирования.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/06/2020
ms.openlocfilehash: 08e1aaecdee753dc25cca0d6356caaafae1ad510
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2020
ms.locfileid: "94557120"
---
# <a name="azure-functions"></a><span data-ttu-id="0e1c7-103">Проверка</span><span class="sxs-lookup"><span data-stu-id="0e1c7-103">Azure Functions</span></span>

<span data-ttu-id="0e1c7-104">Функции Azure предоставляют бессерверные возможности вычислений.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-104">Azure Functions provide a serverless compute experience.</span></span> <span data-ttu-id="0e1c7-105">Функция вызывается *триггером* (например, доступ к конечной точке HTTP или срабатывание по таймеру) и выполняет блок кода или бизнес-логику.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="0e1c7-106">Функции также поддерживают специализированные *привязки*, которые подключаются к таким ресурсам, как хранилище и очереди.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Логотип Функций Azure](./media/azure-functions-logo.png)

<span data-ttu-id="0e1c7-108">Текущая версия среды выполнения 3.0 поддерживает кроссплатформенные приложения .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-108">The current runtime version 3.0 supports cross-platform .NET Core 3.1 applications.</span></span> <span data-ttu-id="0e1c7-109">Помимо C# поддерживаются дополнительные языки, такие как JavaScript, F# и Java.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-109">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="0e1c7-110">Функции, созданные на портале, предоставляют расширенный синтаксис написания скриптов.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-110">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="0e1c7-111">Функции, созданные как отдельные проекты, могут быть развернуты с полной поддержкой и возможностями платформы.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-111">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="0e1c7-112">Дополнительные сведения см. в [документации по Функциям Azure](/azure/azure-functions).</span><span class="sxs-lookup"><span data-stu-id="0e1c7-112">For more information, see [Azure Functions documentation](/azure/azure-functions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="0e1c7-113">Поддержка языков программирования</span><span class="sxs-lookup"><span data-stu-id="0e1c7-113">Programming language support</span></span>

<span data-ttu-id="0e1c7-114">Все следующие языки поддерживаются в общедоступной версии.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-114">The following languages are all supported in general availability (GA).</span></span>

|<span data-ttu-id="0e1c7-115">Язык</span><span class="sxs-lookup"><span data-stu-id="0e1c7-115">Language</span></span>      |<span data-ttu-id="0e1c7-116">Поддерживаемые среды выполнения</span><span class="sxs-lookup"><span data-stu-id="0e1c7-116">Supported runtimes</span></span>|
|--------------|------------------|
|<span data-ttu-id="0e1c7-117">**C#**</span><span class="sxs-lookup"><span data-stu-id="0e1c7-117">**C#**</span></span>        |<span data-ttu-id="0e1c7-118">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="0e1c7-118">.NET Core 3.1</span></span>     |
|<span data-ttu-id="0e1c7-119">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="0e1c7-119">**JavaScript**</span></span>|<span data-ttu-id="0e1c7-120">Узлы 10 и 12</span><span class="sxs-lookup"><span data-stu-id="0e1c7-120">Node 10 & 12</span></span>      |
|<span data-ttu-id="0e1c7-121">**F#**</span><span class="sxs-lookup"><span data-stu-id="0e1c7-121">**F#**</span></span>        |<span data-ttu-id="0e1c7-122">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="0e1c7-122">.NET Core 3.1</span></span>     |
|<span data-ttu-id="0e1c7-123">**Java**</span><span class="sxs-lookup"><span data-stu-id="0e1c7-123">**Java**</span></span>      |<span data-ttu-id="0e1c7-124">Java 8</span><span class="sxs-lookup"><span data-stu-id="0e1c7-124">Java 8</span></span>            |
|<span data-ttu-id="0e1c7-125">**Python**</span><span class="sxs-lookup"><span data-stu-id="0e1c7-125">**Python**</span></span>    |<span data-ttu-id="0e1c7-126">Python 3.6, 3.7 и 3.8</span><span class="sxs-lookup"><span data-stu-id="0e1c7-126">Python 3.6, 3.7, & 3.8</span></span>|
|<span data-ttu-id="0e1c7-127">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="0e1c7-127">**TypeScript**</span></span>|<span data-ttu-id="0e1c7-128">Узлы 10 и 12 (через JavaScript)</span><span class="sxs-lookup"><span data-stu-id="0e1c7-128">Node 10 & 12 (via JavaScript)</span></span>|
|<span data-ttu-id="0e1c7-129">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0e1c7-129">**PowerShell**</span></span>|<span data-ttu-id="0e1c7-130">PowerShell Core 6</span><span class="sxs-lookup"><span data-stu-id="0e1c7-130">PowerShell Core 6</span></span>|

<span data-ttu-id="0e1c7-131">Дополнительные сведения см. в [списке поддерживаемых языков](/azure/azure-functions/supported-languages).</span><span class="sxs-lookup"><span data-stu-id="0e1c7-131">For more information, see [Supported languages](/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="0e1c7-132">Планы службы приложений</span><span class="sxs-lookup"><span data-stu-id="0e1c7-132">App service plans</span></span>

<span data-ttu-id="0e1c7-133">Функции поддерживаются *планом службы приложений*.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-133">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="0e1c7-134">План определяет ресурсы, используемые приложением-функцией.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-134">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="0e1c7-135">Можно назначить планы для региона, определить размер и количество используемых виртуальных машин, а также выбрать ценовую категорию.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-135">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="0e1c7-136">Для истинного бессерверного подхода в приложениях-функциях может использоваться план **потребления**.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-136">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="0e1c7-137">План потребления будет автоматически масштабировать серверную часть в зависимости от нагрузки.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-137">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="0e1c7-138">Другим вариантом размещения для приложений-функций является план [Premium](/azure/azure-functions/functions-premium-plan).</span><span class="sxs-lookup"><span data-stu-id="0e1c7-138">Another hosting option for function apps is the [Premium plan](/azure/azure-functions/functions-premium-plan).</span></span> <span data-ttu-id="0e1c7-139">Этот план предоставляет "постоянно работающий" экземпляр, чтобы избежать начальной загрузки, поддерживает дополнительные функции, такие как подключение к виртуальной сети, и работает на высококлассном оборудовании.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-139">This plan provides an "always on" instance to avoid cold start, supports advanced features like VNet connectivity, and runs on premium hardware.</span></span>

<span data-ttu-id="0e1c7-140">Обзор планов Службы приложений Azure см. в [этой статье](/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span><span class="sxs-lookup"><span data-stu-id="0e1c7-140">For more information, see [App service plans](/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="0e1c7-141">Создание первой функции</span><span class="sxs-lookup"><span data-stu-id="0e1c7-141">Create your first function</span></span>

<span data-ttu-id="0e1c7-142">Существует три стандартных способа создания приложений-функций.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-142">There are three common ways you can create function apps.</span></span>

- <span data-ttu-id="0e1c7-143">Создание скриптов для функций на портале.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-143">Script functions in the portal.</span></span>
- <span data-ttu-id="0e1c7-144">Создание требуемых ресурсов с помощью Azure CLI.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-144">Create the necessary resources using the Azure CLI.</span></span>
- <span data-ttu-id="0e1c7-145">Создание функций локально с помощью избранной интегрированной среды разработки и их публикация в Azure.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-145">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="0e1c7-146">Дополнительные сведения о создании функции с помощью скрипта на портале см. в статье [Создание первой функции на портале Azure](/azure/azure-functions/functions-create-first-azure-function).</span><span class="sxs-lookup"><span data-stu-id="0e1c7-146">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="0e1c7-147">Чтобы выполнить сборку с помощью Azure CLI, ознакомьтесь со статьей [Краткое руководство. Создание первой функции из командной строки с помощью Azure CLI](/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span><span class="sxs-lookup"><span data-stu-id="0e1c7-147">To build from the Azure CLI, see [Create your first function using the Azure CLI](/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="0e1c7-148">Сведения о создании функции из Visual Studio см. в статье [Создание первой функции с помощью Visual Studio](/azure/azure-functions/functions-create-your-first-function-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="0e1c7-148">To create a function from Visual Studio, see [Create your first function using Visual Studio](/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="0e1c7-149">Общие сведения о триггерах и привязках</span><span class="sxs-lookup"><span data-stu-id="0e1c7-149">Understand triggers and bindings</span></span>

<span data-ttu-id="0e1c7-150">Функции вызываются *триггером* и могут иметь только один триггер.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-150">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="0e1c7-151">Помимо вызова функции определенные триггеры также выступают в качестве привязок.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-151">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="0e1c7-152">В дополнение к триггеру можно также определить несколько привязок.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-152">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="0e1c7-153">*Привязки* предоставляют декларативный способ подключения данных к коду.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-153">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="0e1c7-154">Они могут передаваться (входные) или получать данные (выходные).</span><span class="sxs-lookup"><span data-stu-id="0e1c7-154">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="0e1c7-155">Триггеры и привязки упрощают работу с функциями.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-155">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="0e1c7-156">Привязки устраняют затраты на создание подключения к базе данных или файловой системе вручную.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-156">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="0e1c7-157">Вся информация, необходимая для привязок, содержится в специальном файле *functions.JSON* для скриптов или объявляется с атрибутами в коде.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-157">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="0e1c7-158">Некоторые распространенные триггеры:</span><span class="sxs-lookup"><span data-stu-id="0e1c7-158">Some common triggers include:</span></span>

- <span data-ttu-id="0e1c7-159">хранилище BLOB-объектов: вызов функции, когда файл или папка передаются или изменяются в хранилище;</span><span class="sxs-lookup"><span data-stu-id="0e1c7-159">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
- <span data-ttu-id="0e1c7-160">HTTP: вызов функции, например REST API;</span><span class="sxs-lookup"><span data-stu-id="0e1c7-160">HTTP: invoke your function like a REST API.</span></span>
- <span data-ttu-id="0e1c7-161">очередь: вызов функции при наличии элементов в очереди;</span><span class="sxs-lookup"><span data-stu-id="0e1c7-161">Queue: invoke your function when items exist in a queue.</span></span>
- <span data-ttu-id="0e1c7-162">таймер: вызов функции регулярно.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-162">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="0e1c7-163">Примеры привязок:</span><span class="sxs-lookup"><span data-stu-id="0e1c7-163">Examples of bindings include:</span></span>

- <span data-ttu-id="0e1c7-164">CosmosDB: простое подключение к базе данных для передачи или сохранения файлов;</span><span class="sxs-lookup"><span data-stu-id="0e1c7-164">CosmosDB: easily connect to the database to load or save files.</span></span>
- <span data-ttu-id="0e1c7-165">Хранилище таблиц: работа с хранилищем пар "ключ — значение" из приложения-функции;</span><span class="sxs-lookup"><span data-stu-id="0e1c7-165">Table Storage: work with key/value storage from your function app.</span></span>
- <span data-ttu-id="0e1c7-166">Хранилище очередей: простое извлечение элементов из очереди или размещение новых элементов в очереди.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-166">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="0e1c7-167">В следующем примере файла *functions.JSON* определены триггер и привязка:</span><span class="sxs-lookup"><span data-stu-id="0e1c7-167">The following example *functions.json* file defines a trigger and a binding:</span></span>

```json
{
  "bindings": [
    {
      "name": "myBlob",
      "type": "blobTrigger",
      "direction": "in",
      "path": "images/{name}",
      "connection": "AzureWebJobsStorage"
    },
    {
      "name": "$return",
      "type": "queue",
      "direction": "out",
      "queueName": "images",
      "connection": "AzureWebJobsStorage"
    }
  ],
  "disabled": false
}
```

<span data-ttu-id="0e1c7-168">В этом примере функция активируется в результате внесения изменения в хранилище BLOB-объектов в контейнере `images`.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-168">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="0e1c7-169">Для файла передается информация, поэтому триггер также выступает в качестве привязки.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-169">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="0e1c7-170">Существует другая привязка для размещения информации в очереди с именем `images`.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-170">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="0e1c7-171">Ниже приведен скрипт C# для функции.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-171">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="0e1c7-172">Этот пример представляет собой простую функцию, которая принимает имя файла, который был изменен или передан в хранилище BLOB-объектов, и помещает его в очередь для последующей обработки.</span><span class="sxs-lookup"><span data-stu-id="0e1c7-172">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="0e1c7-173">Полный список триггеров и привязок Функций Azure см. в [этой статье](/azure/azure-functions/functions-triggers-bindings).</span><span class="sxs-lookup"><span data-stu-id="0e1c7-173">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](/azure/azure-functions/functions-triggers-bindings).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0e1c7-174">[Назад](azure-serverless-platform.md)
>[Вперед](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="0e1c7-174">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>
