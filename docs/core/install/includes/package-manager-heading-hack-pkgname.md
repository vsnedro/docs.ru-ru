---
ms.openlocfilehash: 7723892a33bf7dd8e475b2f696db5d9ab287e182
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602756"
---

<span data-ttu-id="a50d4-101">Пакеты, добавляемые в веб-каналы диспетчера пакетов, именуются в формате, 	уязвимом для хакерских атак: `{product}-{type}-{version}`.</span><span class="sxs-lookup"><span data-stu-id="a50d4-101">The packages added to package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="a50d4-102">**product**</span><span class="sxs-lookup"><span data-stu-id="a50d4-102">**product**</span></span>\
<span data-ttu-id="a50d4-103">Тип устанавливаемого продукта .NET.</span><span class="sxs-lookup"><span data-stu-id="a50d4-103">The type of .NET product to install.</span></span> <span data-ttu-id="a50d4-104">Допустимые параметры:</span><span class="sxs-lookup"><span data-stu-id="a50d4-104">Valid options are:</span></span>

  - <span data-ttu-id="a50d4-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="a50d4-105">dotnet</span></span>
  - <span data-ttu-id="a50d4-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="a50d4-106">aspnetcore</span></span>

- <span data-ttu-id="a50d4-107">**type**</span><span class="sxs-lookup"><span data-stu-id="a50d4-107">**type**</span></span>\
<span data-ttu-id="a50d4-108">Позволяет выбрать пакет SDK или среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="a50d4-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="a50d4-109">Допустимые параметры:</span><span class="sxs-lookup"><span data-stu-id="a50d4-109">Valid options are:</span></span>

  - <span data-ttu-id="a50d4-110">sdk</span><span class="sxs-lookup"><span data-stu-id="a50d4-110">sdk</span></span>
  - <span data-ttu-id="a50d4-111">исполняющая среда</span><span class="sxs-lookup"><span data-stu-id="a50d4-111">runtime</span></span>

- <span data-ttu-id="a50d4-112">**version**</span><span class="sxs-lookup"><span data-stu-id="a50d4-112">**version**</span></span>\
<span data-ttu-id="a50d4-113">Версия пакета SDK или среды выполнения для установки.</span><span class="sxs-lookup"><span data-stu-id="a50d4-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="a50d4-114">Эта статья всегда будет содержать инструкции для последней поддерживаемой версии.</span><span class="sxs-lookup"><span data-stu-id="a50d4-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="a50d4-115">Допустимые параметры — любая выпущенная версия, например:</span><span class="sxs-lookup"><span data-stu-id="a50d4-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="a50d4-116">3.1</span><span class="sxs-lookup"><span data-stu-id="a50d4-116">3.1</span></span>
  - <span data-ttu-id="a50d4-117">3.0</span><span class="sxs-lookup"><span data-stu-id="a50d4-117">3.0</span></span>
  - <span data-ttu-id="a50d4-118">2.1</span><span class="sxs-lookup"><span data-stu-id="a50d4-118">2.1</span></span>

  <span data-ttu-id="a50d4-119">Возможно, пакет SDK или среда выполнения, которые вы пытаетесь скачать, недоступны для вашего дистрибутива Linux.</span><span class="sxs-lookup"><span data-stu-id="a50d4-119">It's possible the SDK/runtime you're trying to download is not available for your Linux distribution.</span></span> <span data-ttu-id="a50d4-120">Список поддерживаемых дистрибутивов см. в статье [Зависимости и требования для .NET Core](../linux.md).</span><span class="sxs-lookup"><span data-stu-id="a50d4-120">For a list of supported distributions, see [.NET Core dependencies and requirements](../linux.md).</span></span>

### <a name="examples"></a><span data-ttu-id="a50d4-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="a50d4-121">Examples</span></span>

- <span data-ttu-id="a50d4-122">Установка среды выполнения ASP.NET Core 3.1: `aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="a50d4-122">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="a50d4-123">Установка среды выполнения .NET Core 2.1: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="a50d4-123">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>
- <span data-ttu-id="a50d4-124">Установка пакета SDK для .NET Core 3.1: `dotnet-sdk-3.1`</span><span class="sxs-lookup"><span data-stu-id="a50d4-124">Install the .NET Core 3.1 SDK: `dotnet-sdk-3.1`</span></span>

### <a name="package-missing"></a><span data-ttu-id="a50d4-125">Пакет отсутствует</span><span class="sxs-lookup"><span data-stu-id="a50d4-125">Package missing</span></span>

<span data-ttu-id="a50d4-126">Если сочетание пакета и версии больше не поддерживается, оно недоступно.</span><span class="sxs-lookup"><span data-stu-id="a50d4-126">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="a50d4-127">Например, пакет SDK для ASP.NET Core отсутствует, компоненты этого пакета SDK входят в состав пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a50d4-127">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="a50d4-128">Значение `aspnetcore-sdk-2.2` неправильное и должно быть равно `dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="a50d4-128">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span> <span data-ttu-id="a50d4-129">Список дистрибутивов Linux, поддерживаемых .NET Core, см. в статье [Зависимости и требования для .NET Core](../linux.md).</span><span class="sxs-lookup"><span data-stu-id="a50d4-129">For a list of Linux distributions supported by .NET Core, see [.NET Core dependencies and requirements](../linux.md).</span></span>
