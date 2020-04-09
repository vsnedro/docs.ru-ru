---
title: Обрезка автономных приложений
description: Сведения об обрезке автономных приложений для уменьшения их размера. .NET Core объединяет среду выполнения с автономно публикуемым приложением и обычно содержит больше компонентов среды выполнения, чем необходимо.
author: jamshedd
ms.author: jamshedd
ms.date: 01/23/2020
ms.openlocfilehash: 5206ca255c500b382402ac4e7dd3300b7face1cf
ms.sourcegitcommit: 45cced471d59d5dac3f0c92abc9d4849716098a2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/04/2020
ms.locfileid: "80665623"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="f7c85-104">Обрезка автономных развертываний и исполняемых файлов</span><span class="sxs-lookup"><span data-stu-id="f7c85-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="f7c85-105">При публикации автономного приложения среда выполнения .NET Core объединяется с приложением.</span><span class="sxs-lookup"><span data-stu-id="f7c85-105">When publishing an application self-contained, the .NET Core runtime is bundled together with the application.</span></span> <span data-ttu-id="f7c85-106">В этом случае в упакованное приложение добавляется значительный объем содержимого.</span><span class="sxs-lookup"><span data-stu-id="f7c85-106">This bundling adds a significant amount of content to your packaged application.</span></span>

<span data-ttu-id="f7c85-107">Когда дело доходит до развертывания приложения, размер часто является важным фактором.</span><span class="sxs-lookup"><span data-stu-id="f7c85-107">When it comes to deploying your application, size is often an important factor.</span></span> <span data-ttu-id="f7c85-108">Как правило, разработчики приложений стремятся максимально уменьшить размер пакета приложения.</span><span class="sxs-lookup"><span data-stu-id="f7c85-108">Keeping the size of the package application as small as possible is typically a goal for application developers.</span></span>

<span data-ttu-id="f7c85-109">В зависимости от сложности приложения для его запуска и работы требуется только подмножество среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f7c85-109">Depending on the complexity of the application, only a subset of the runtime is required to run the application.</span></span> <span data-ttu-id="f7c85-110">Неиспользуемые компоненты среды выполнения не нужны, поэтому их можно удалить из упакованного приложения.</span><span class="sxs-lookup"><span data-stu-id="f7c85-110">These unused parts of the runtime are unnecessary and can be trimmed from the packaged application.</span></span>

> [!NOTE]
> <span data-ttu-id="f7c85-111">Обрезка — это экспериментальная функция в .NET Core 3.1, которая доступна _только_ для автономно публикуемых приложений.</span><span class="sxs-lookup"><span data-stu-id="f7c85-111">Trimming is an experimental feature in .NET Core 3.1 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="trim-your-application"></a><span data-ttu-id="f7c85-112">Обрезка приложения</span><span class="sxs-lookup"><span data-stu-id="f7c85-112">Trim your application</span></span>

<span data-ttu-id="f7c85-113">В следующем примере показано, как обрезать приложение с помощью команды [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="f7c85-113">The following example shows how to trim your application using the [dotnet publish](../tools/dotnet-publish.md) command:</span></span>

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true /p:PublishSingleFile=false /p:PublishTrimmed=true
```

<span data-ttu-id="f7c85-114">Функция обрезки проверяет двоичные файлы приложения, чтобы найти требуемые сборки среды выполнения и построить соответствующий граф.</span><span class="sxs-lookup"><span data-stu-id="f7c85-114">The trimming feature works by examining the application binaries to discover and build a graph of the required runtime assemblies.</span></span> <span data-ttu-id="f7c85-115">Оставшиеся сборки среды выполнения, на которые отсутствуют ссылки, обрезаются.</span><span class="sxs-lookup"><span data-stu-id="f7c85-115">The remaining runtime assemblies that aren't referenced are trimmed.</span></span>

## <a name="trimming-issues-when-using-reflection"></a><span data-ttu-id="f7c85-116">Проблемы с обрезкой при использовании отражения</span><span class="sxs-lookup"><span data-stu-id="f7c85-116">Trimming issues when using reflection</span></span>

<span data-ttu-id="f7c85-117">В некоторых случаях функции обрезки не удается обнаружить ссылки.</span><span class="sxs-lookup"><span data-stu-id="f7c85-117">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="f7c85-118">Например, эта проблема может возникнуть в приложении, использующем отражение, поскольку зависимость от сборки будет известна только во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f7c85-118">For example, an application that uses reflection could run into this issue because the dependency on the assembly will only be known at run time.</span></span>

<span data-ttu-id="f7c85-119">Обрезка является проблемой только в том случае, если использование отражения зависит от сборки среды выполнения, на которую нет прямой ссылки.</span><span class="sxs-lookup"><span data-stu-id="f7c85-119">Trimming is only a problem if the reflection usage depends on a runtime assembly that isn't referenced directly.</span></span> <span data-ttu-id="f7c85-120">Необходимо иметь в виду, что код приложения может не использовать отражение напрямую, но его может использовать сторонняя сборка, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="f7c85-120">Keep in mind that your application code may not be using reflection directly, but a third-party assembly you're referencing may be using it.</span></span>

<span data-ttu-id="f7c85-121">Если код ссылается на API через отражение и вы не хотите, чтобы компоновщик обрезал сборку, содержащую этот API, можно изменить файл проекта так, чтобы исключить сборку из процесса обрезки.</span><span class="sxs-lookup"><span data-stu-id="f7c85-121">When the code is referencing an API through reflection and you don't want the linker to trim the assembly that contains that API, you can modify your project file to exclude the assembly from the trimming process.</span></span> <span data-ttu-id="f7c85-122">В следующем примере показано исключение сборки `System.Security` из процесса обрезки.</span><span class="sxs-lookup"><span data-stu-id="f7c85-122">The following example shows how to prevent an assembly called `System.Security` from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="see-also"></a><span data-ttu-id="f7c85-123">См. также</span><span class="sxs-lookup"><span data-stu-id="f7c85-123">See also</span></span>

- [<span data-ttu-id="f7c85-124">Развертывание приложений .NET Core</span><span class="sxs-lookup"><span data-stu-id="f7c85-124">.NET Core application deployment</span></span>](index.md)
