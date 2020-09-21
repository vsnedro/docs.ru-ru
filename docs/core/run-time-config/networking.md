---
title: Параметры конфигурации сети
description: Сведения о параметрах времени выполнения, определяющих использование сети для приложений .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: d43b68206cc82f4a41df02bd5998702b4f5d0590
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538137"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="a9111-103">Параметры конфигурации времени выполнения для сети</span><span class="sxs-lookup"><span data-stu-id="a9111-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="a9111-104">Протокол HTTP/2</span><span class="sxs-lookup"><span data-stu-id="a9111-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="a9111-105">Указывает, включена ли поддержка протокола HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="a9111-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>

- <span data-ttu-id="a9111-106">Если этот параметр не задан, поддержка протокола HTTP/2 будет отключена.</span><span class="sxs-lookup"><span data-stu-id="a9111-106">If you omit this setting, support for the HTTP/2 protocol is disabled.</span></span> <span data-ttu-id="a9111-107">Это эквивалентно присвоению значения `false`.</span><span class="sxs-lookup"><span data-stu-id="a9111-107">This is equivalent to setting the value to `false`.</span></span>

- <span data-ttu-id="a9111-108">Представлено в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="a9111-108">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="a9111-109">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="a9111-109">Setting name</span></span> | <span data-ttu-id="a9111-110">Значения</span><span class="sxs-lookup"><span data-stu-id="a9111-110">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a9111-111">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a9111-111">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="a9111-112">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="a9111-112">`false` - disabled</span></span><br/><span data-ttu-id="a9111-113">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="a9111-113">`true` - enabled</span></span> |
| <span data-ttu-id="a9111-114">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="a9111-114">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="a9111-115">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="a9111-115">`0` - disabled</span></span><br/><span data-ttu-id="a9111-116">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="a9111-116">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="a9111-117">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="a9111-117">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="a9111-118">Определяет, использует ли <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> или более старые стеки протокола HTTP (<xref:System.Net.Http.WinHttpHandler> в Windows и `CurlHandler` — внутренний класс, реализованный на базе [libcurl](https://curl.haxx.se/libcurl/), в Linux).</span><span class="sxs-lookup"><span data-stu-id="a9111-118">Configures whether <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> uses <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or older HTTP protocol stacks (<xref:System.Net.Http.WinHttpHandler> on Windows and `CurlHandler`, an internal class implemented on top of [libcurl](https://curl.haxx.se/libcurl/), on Linux).</span></span>

  > [!NOTE]
  > <span data-ttu-id="a9111-119">Вместо непосредственного создания экземпляра класса <xref:System.Net.Http.HttpClientHandler> вы можете использовать высокоуровневые сетевые интерфейсы API.</span><span class="sxs-lookup"><span data-stu-id="a9111-119">You may be using high-level networking APIs instead of directly instantiating the <xref:System.Net.Http.HttpClientHandler> class.</span></span> <span data-ttu-id="a9111-120">Этот параметр также влияет на то, какой стек протокола HTTP используется высокоуровневыми сетевыми интерфейсами API, включая <xref:System.Net.Http.HttpClient> и [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118)).</span><span class="sxs-lookup"><span data-stu-id="a9111-120">This setting also affects which HTTP protocol stack is used by high-level networking APIs, including <xref:System.Net.Http.HttpClient> and [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118)).</span></span>

- <span data-ttu-id="a9111-121">Если этот параметр не задан, <xref:System.Net.Http.HttpClientHandler> будет использовать <xref:System.Net.Http.SocketsHttpHandler>.</span><span class="sxs-lookup"><span data-stu-id="a9111-121">If you omit this setting, <xref:System.Net.Http.HttpClientHandler> uses <xref:System.Net.Http.SocketsHttpHandler>.</span></span> <span data-ttu-id="a9111-122">Это эквивалентно присвоению значения `true`.</span><span class="sxs-lookup"><span data-stu-id="a9111-122">This is equivalent to setting the value to `true`.</span></span>

- <span data-ttu-id="a9111-123">Этот параметр можно настроить программно, вызвав метод <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a9111-123">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="a9111-124">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="a9111-124">Setting name</span></span> | <span data-ttu-id="a9111-125">Значения</span><span class="sxs-lookup"><span data-stu-id="a9111-125">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a9111-126">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a9111-126">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="a9111-127">`true` — позволяет использовать <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="a9111-127">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="a9111-128">`false` — позволяет использовать <xref:System.Net.Http.WinHttpHandler> в Windows или [libcurl](https://curl.haxx.se/libcurl/) в Linux</span><span class="sxs-lookup"><span data-stu-id="a9111-128">`false` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |
| <span data-ttu-id="a9111-129">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="a9111-129">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="a9111-130">`1` — позволяет использовать <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="a9111-130">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="a9111-131">`0` — позволяет использовать <xref:System.Net.Http.WinHttpHandler> в Windows или [libcurl](https://curl.haxx.se/libcurl/) в Linux</span><span class="sxs-lookup"><span data-stu-id="a9111-131">`0` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |

> [!NOTE]
> <span data-ttu-id="a9111-132">Начиная с .NET 5 параметр `System.Net.Http.UseSocketsHttpHandler` больше недоступен.</span><span class="sxs-lookup"><span data-stu-id="a9111-132">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>
