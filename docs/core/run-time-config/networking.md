---
title: Параметры конфигурации сети
description: Сведения о параметрах времени выполнения, определяющих использование сети для приложений .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 6b5e03b127f95911b712b66c0be8a4f5a2929fc2
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761945"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="d532c-103">Параметры конфигурации времени выполнения для сети</span><span class="sxs-lookup"><span data-stu-id="d532c-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="d532c-104">Протокол HTTP/2</span><span class="sxs-lookup"><span data-stu-id="d532c-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="d532c-105">Указывает, включена ли поддержка протокола HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="d532c-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>

- <span data-ttu-id="d532c-106">Если этот параметр не задан, поддержка протокола HTTP/2 будет отключена.</span><span class="sxs-lookup"><span data-stu-id="d532c-106">If you omit this setting, support for the HTTP/2 protocol is disabled.</span></span> <span data-ttu-id="d532c-107">Это эквивалентно присвоению значения `false`.</span><span class="sxs-lookup"><span data-stu-id="d532c-107">This is equivalent to setting the value to `false`.</span></span>

- <span data-ttu-id="d532c-108">Представлено в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d532c-108">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="d532c-109">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="d532c-109">Setting name</span></span> | <span data-ttu-id="d532c-110">Значения</span><span class="sxs-lookup"><span data-stu-id="d532c-110">Values</span></span> |
| - | - | - |
| <span data-ttu-id="d532c-111">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d532c-111">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="d532c-112">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="d532c-112">`false` - disabled</span></span><br/><span data-ttu-id="d532c-113">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="d532c-113">`true` - enabled</span></span> |
| <span data-ttu-id="d532c-114">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="d532c-114">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="d532c-115">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="d532c-115">`0` - disabled</span></span><br/><span data-ttu-id="d532c-116">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="d532c-116">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="d532c-117">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="d532c-117">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="d532c-118">Определяет, использует ли <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> или более старые стеки протокола HTTP (<xref:System.Net.Http.WinHttpHandler> в Windows и `CurlHandler` — внутренний класс, реализованный на базе [libcurl](https://curl.haxx.se/libcurl/), в Linux).</span><span class="sxs-lookup"><span data-stu-id="d532c-118">Configures whether <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> uses <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or older HTTP protocol stacks (<xref:System.Net.Http.WinHttpHandler> on Windows and `CurlHandler`, an internal class implemented on top of [libcurl](https://curl.haxx.se/libcurl/), on Linux).</span></span>

  > [!NOTE]
  > <span data-ttu-id="d532c-119">Вместо непосредственного создания экземпляра класса <xref:System.Net.Http.HttpClientHandler> вы можете использовать высокоуровневые сетевые интерфейсы API.</span><span class="sxs-lookup"><span data-stu-id="d532c-119">You may be using high-level networking APIs instead of directly instantiating the <xref:System.Net.Http.HttpClientHandler> class.</span></span> <span data-ttu-id="d532c-120">Этот параметр также влияет на то, какой стек протокола HTTP используется высокоуровневыми сетевыми интерфейсами API, включая <xref:System.Net.Http.HttpClient> и [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).</span><span class="sxs-lookup"><span data-stu-id="d532c-120">This setting also affects which HTTP protocol stack is used by high-level networking APIs, including <xref:System.Net.Http.HttpClient> and [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).</span></span>

- <span data-ttu-id="d532c-121">Если этот параметр не задан, <xref:System.Net.Http.HttpClientHandler> будет использовать <xref:System.Net.Http.SocketsHttpHandler>.</span><span class="sxs-lookup"><span data-stu-id="d532c-121">If you omit this setting, <xref:System.Net.Http.HttpClientHandler> uses <xref:System.Net.Http.SocketsHttpHandler>.</span></span> <span data-ttu-id="d532c-122">Это эквивалентно присвоению значения `true`.</span><span class="sxs-lookup"><span data-stu-id="d532c-122">This is equivalent to setting the value to `true`.</span></span>

- <span data-ttu-id="d532c-123">Этот параметр можно настроить программно, вызвав метод <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d532c-123">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="d532c-124">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="d532c-124">Setting name</span></span> | <span data-ttu-id="d532c-125">Значения</span><span class="sxs-lookup"><span data-stu-id="d532c-125">Values</span></span> |
| - | - | - |
| <span data-ttu-id="d532c-126">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d532c-126">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="d532c-127">`true` — позволяет использовать <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="d532c-127">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="d532c-128">`false` — позволяет использовать <xref:System.Net.Http.WinHttpHandler> в Windows или [libcurl](https://curl.haxx.se/libcurl/) в Linux</span><span class="sxs-lookup"><span data-stu-id="d532c-128">`false` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |
| <span data-ttu-id="d532c-129">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="d532c-129">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="d532c-130">`1` — позволяет использовать <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="d532c-130">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="d532c-131">`0` — позволяет использовать <xref:System.Net.Http.WinHttpHandler> в Windows или [libcurl](https://curl.haxx.se/libcurl/) в Linux</span><span class="sxs-lookup"><span data-stu-id="d532c-131">`0` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |

> [!NOTE]
> <span data-ttu-id="d532c-132">Начиная с .NET 5 параметр `System.Net.Http.UseSocketsHttpHandler` больше недоступен.</span><span class="sxs-lookup"><span data-stu-id="d532c-132">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>
