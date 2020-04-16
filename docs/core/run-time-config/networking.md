---
title: Параметры конфигурации сети
description: Сведения о параметрах времени выполнения, определяющих использование сети для приложений .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 8d02087ad7260cc78c096090bf3b06a716d34678
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989107"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="52d13-103">Параметры конфигурации времени выполнения для сети</span><span class="sxs-lookup"><span data-stu-id="52d13-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="52d13-104">Протокол HTTP/2</span><span class="sxs-lookup"><span data-stu-id="52d13-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="52d13-105">Указывает, включена ли поддержка протокола HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="52d13-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>

- <span data-ttu-id="52d13-106">По умолчанию: отключено (`false`).</span><span class="sxs-lookup"><span data-stu-id="52d13-106">Default: Disabled (`false`).</span></span>

- <span data-ttu-id="52d13-107">Представлено в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="52d13-107">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="52d13-108">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="52d13-108">Setting name</span></span> | <span data-ttu-id="52d13-109">Значения</span><span class="sxs-lookup"><span data-stu-id="52d13-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="52d13-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="52d13-110">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="52d13-111">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="52d13-111">`false` - disabled</span></span><br/><span data-ttu-id="52d13-112">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="52d13-112">`true` - enabled</span></span> |
| <span data-ttu-id="52d13-113">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="52d13-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="52d13-114">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="52d13-114">`0` - disabled</span></span><br/><span data-ttu-id="52d13-115">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="52d13-115">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="52d13-116">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="52d13-116">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="52d13-117">Определяет, использует ли <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> или более старые стеки протокола HTTP (<xref:System.Net.Http.WinHttpHandler> в Windows и `CurlHandler` — внутренний класс, реализованный на базе [libcurl](https://curl.haxx.se/libcurl/), в Linux).</span><span class="sxs-lookup"><span data-stu-id="52d13-117">Configures whether <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> uses <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or older HTTP protocol stacks (<xref:System.Net.Http.WinHttpHandler> on Windows and `CurlHandler`, an internal class implemented on top of [libcurl](https://curl.haxx.se/libcurl/), on Linux).</span></span>

  > [!NOTE]
  > <span data-ttu-id="52d13-118">Вместо непосредственного создания экземпляра класса <xref:System.Net.Http.HttpClientHandler> вы можете использовать высокоуровневые сетевые интерфейсы API.</span><span class="sxs-lookup"><span data-stu-id="52d13-118">You may be using high-level networking APIs instead of directly instantiating the <xref:System.Net.Http.HttpClientHandler> class.</span></span> <span data-ttu-id="52d13-119">Этот параметр также влияет на то, какой стек протокола HTTP используется высокоуровневыми сетевыми интерфейсами API, включая <xref:System.Net.Http.HttpClient> и [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).</span><span class="sxs-lookup"><span data-stu-id="52d13-119">This setting also affects which HTTP protocol stack is used by high-level networking APIs, including <xref:System.Net.Http.HttpClient> and [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).</span></span>

- <span data-ttu-id="52d13-120">По умолчанию: используется <xref:System.Net.Http.SocketsHttpHandler> (`true`).</span><span class="sxs-lookup"><span data-stu-id="52d13-120">Default: Use <xref:System.Net.Http.SocketsHttpHandler> (`true`).</span></span>

- <span data-ttu-id="52d13-121">Этот параметр можно настроить программно, вызвав метод <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="52d13-121">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="52d13-122">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="52d13-122">Setting name</span></span> | <span data-ttu-id="52d13-123">Значения</span><span class="sxs-lookup"><span data-stu-id="52d13-123">Values</span></span> |
| - | - | - |
| <span data-ttu-id="52d13-124">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="52d13-124">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="52d13-125">`true` — позволяет использовать <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="52d13-125">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="52d13-126">`false` — позволяет использовать <xref:System.Net.Http.WinHttpHandler> в Windows или [libcurl](https://curl.haxx.se/libcurl/) в Linux</span><span class="sxs-lookup"><span data-stu-id="52d13-126">`false` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |
| <span data-ttu-id="52d13-127">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="52d13-127">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="52d13-128">`1` — позволяет использовать <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="52d13-128">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="52d13-129">`0` — позволяет использовать <xref:System.Net.Http.WinHttpHandler> в Windows или [libcurl](https://curl.haxx.se/libcurl/) в Linux</span><span class="sxs-lookup"><span data-stu-id="52d13-129">`0` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |

> [!NOTE]
> <span data-ttu-id="52d13-130">Начиная с .NET 5 параметр `System.Net.Http.UseSocketsHttpHandler` больше недоступен.</span><span class="sxs-lookup"><span data-stu-id="52d13-130">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>
