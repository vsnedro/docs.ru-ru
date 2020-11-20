---
ms.openlocfilehash: ab1006f706439bcf5129854da3d14538e5b690a2
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506882"
---

<span data-ttu-id="966b9-101">Пакеты, добавляемые в веб-каналы диспетчера пакетов, именуются в формате, 	уязвимом для хакерских атак: `{product}-{type}-{version}`.</span><span class="sxs-lookup"><span data-stu-id="966b9-101">The packages added to package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="966b9-102">**product**</span><span class="sxs-lookup"><span data-stu-id="966b9-102">**product**</span></span>\
<span data-ttu-id="966b9-103">Тип устанавливаемого продукта .NET.</span><span class="sxs-lookup"><span data-stu-id="966b9-103">The type of .NET product to install.</span></span> <span data-ttu-id="966b9-104">Допустимые параметры:</span><span class="sxs-lookup"><span data-stu-id="966b9-104">Valid options are:</span></span>

  - <span data-ttu-id="966b9-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="966b9-105">dotnet</span></span>
  - <span data-ttu-id="966b9-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="966b9-106">aspnetcore</span></span>

- <span data-ttu-id="966b9-107">**type**</span><span class="sxs-lookup"><span data-stu-id="966b9-107">**type**</span></span>\
<span data-ttu-id="966b9-108">Позволяет выбрать пакет SDK или среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="966b9-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="966b9-109">Допустимые параметры:</span><span class="sxs-lookup"><span data-stu-id="966b9-109">Valid options are:</span></span>

  - <span data-ttu-id="966b9-110">sdk</span><span class="sxs-lookup"><span data-stu-id="966b9-110">sdk</span></span>
  - <span data-ttu-id="966b9-111">исполняющая среда</span><span class="sxs-lookup"><span data-stu-id="966b9-111">runtime</span></span>

- <span data-ttu-id="966b9-112">**version**</span><span class="sxs-lookup"><span data-stu-id="966b9-112">**version**</span></span>\
<span data-ttu-id="966b9-113">Версия пакета SDK или среды выполнения для установки.</span><span class="sxs-lookup"><span data-stu-id="966b9-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="966b9-114">Эта статья всегда будет содержать инструкции для последней поддерживаемой версии.</span><span class="sxs-lookup"><span data-stu-id="966b9-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="966b9-115">Допустимые параметры — любая выпущенная версия, например:</span><span class="sxs-lookup"><span data-stu-id="966b9-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="966b9-116">5,0</span><span class="sxs-lookup"><span data-stu-id="966b9-116">5.0</span></span>
  - <span data-ttu-id="966b9-117">3.1</span><span class="sxs-lookup"><span data-stu-id="966b9-117">3.1</span></span>
  - <span data-ttu-id="966b9-118">3.0</span><span class="sxs-lookup"><span data-stu-id="966b9-118">3.0</span></span>
  - <span data-ttu-id="966b9-119">2.1</span><span class="sxs-lookup"><span data-stu-id="966b9-119">2.1</span></span>

  <span data-ttu-id="966b9-120">Возможно, пакет SDK или среда выполнения, которые вы пытаетесь скачать, недоступны для вашего дистрибутива Linux.</span><span class="sxs-lookup"><span data-stu-id="966b9-120">It's possible the SDK/runtime you're trying to download is not available for your Linux distribution.</span></span> <span data-ttu-id="966b9-121">Список поддерживаемых дистрибутивов см. в статье [Зависимости и требования для .NET Core](../linux.md).</span><span class="sxs-lookup"><span data-stu-id="966b9-121">For a list of supported distributions, see [.NET Core dependencies and requirements](../linux.md).</span></span>

### <a name="examples"></a><span data-ttu-id="966b9-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="966b9-122">Examples</span></span>

- <span data-ttu-id="966b9-123">Установка среды выполнения ASP.NET Core 5.0: `aspnetcore-runtime-5.0`</span><span class="sxs-lookup"><span data-stu-id="966b9-123">Install the ASP.NET Core 5.0 runtime: `aspnetcore-runtime-5.0`</span></span>
- <span data-ttu-id="966b9-124">Установка среды выполнения .NET Core 2.1: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="966b9-124">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>
- <span data-ttu-id="966b9-125">Установка пакета SDK .NET 5.0: `dotnet-sdk-5.0`</span><span class="sxs-lookup"><span data-stu-id="966b9-125">Install the .NET 5.0 SDK: `dotnet-sdk-5.0`</span></span>
- <span data-ttu-id="966b9-126">Установка пакета SDK для .NET Core 3.1: `dotnet-sdk-3.1`</span><span class="sxs-lookup"><span data-stu-id="966b9-126">Install the .NET Core 3.1 SDK: `dotnet-sdk-3.1`</span></span>

### <a name="package-missing"></a><span data-ttu-id="966b9-127">Пакет отсутствует</span><span class="sxs-lookup"><span data-stu-id="966b9-127">Package missing</span></span>

<span data-ttu-id="966b9-128">Если сочетание пакета и версии больше не поддерживается, оно недоступно.</span><span class="sxs-lookup"><span data-stu-id="966b9-128">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="966b9-129">Например, пакет SDK для ASP.NET Core отсутствует, компоненты этого пакета SDK входят в состав пакета SDK для .NET.</span><span class="sxs-lookup"><span data-stu-id="966b9-129">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET SDK.</span></span> <span data-ttu-id="966b9-130">Значение `aspnetcore-sdk-2.2` неправильное и должно быть равно `dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="966b9-130">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span> <span data-ttu-id="966b9-131">Список дистрибутивов Linux, поддерживаемых .NET Core, см. в статье [Зависимости и требования для .NET](../linux.md).</span><span class="sxs-lookup"><span data-stu-id="966b9-131">For a list of Linux distributions supported by .NET Core, see [.NET dependencies and requirements](../linux.md).</span></span>
