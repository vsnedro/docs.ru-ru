---
title: Параметры конфигурации сети
description: Сведения о параметрах времени выполнения, определяющих использование сети для приложений .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: bda608e83bb1b093d7d9b860de9607f6734720aa
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188306"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="25f67-103">Параметры конфигурации времени выполнения для сети</span><span class="sxs-lookup"><span data-stu-id="25f67-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="25f67-104">Протокол HTTP/2</span><span class="sxs-lookup"><span data-stu-id="25f67-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="25f67-105">Указывает, включена ли поддержка протокола HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="25f67-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>

- <span data-ttu-id="25f67-106">Представлено в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="25f67-106">Introduced in .NET Core 3.0.</span></span>

- <span data-ttu-id="25f67-107">Только для .NET Core 3.0 Если этот параметр не задан, поддержка протокола HTTP/2 будет отключена.</span><span class="sxs-lookup"><span data-stu-id="25f67-107">.NET Core 3.0 only: If you omit this setting, support for the HTTP/2 protocol is disabled.</span></span> <span data-ttu-id="25f67-108">Это эквивалентно присвоению значения `false`.</span><span class="sxs-lookup"><span data-stu-id="25f67-108">This is equivalent to setting the value to `false`.</span></span>

- <span data-ttu-id="25f67-109">Для .NET Core 3.1 и .NET 5 и более поздних версий Если этот параметр не задан, поддержка протокола HTTP/2 будет включена.</span><span class="sxs-lookup"><span data-stu-id="25f67-109">.NET Core 3.1 and .NET 5+: If you omit this setting, support for the HTTP/2 protocol is enabled.</span></span> <span data-ttu-id="25f67-110">Это эквивалентно присвоению значения `true`.</span><span class="sxs-lookup"><span data-stu-id="25f67-110">This is equivalent to setting the value to `true`.</span></span>

| | <span data-ttu-id="25f67-111">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="25f67-111">Setting name</span></span> | <span data-ttu-id="25f67-112">Значения</span><span class="sxs-lookup"><span data-stu-id="25f67-112">Values</span></span> |
| - | - | - |
| <span data-ttu-id="25f67-113">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="25f67-113">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="25f67-114">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="25f67-114">`false` - disabled</span></span><br/><span data-ttu-id="25f67-115">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="25f67-115">`true` - enabled</span></span> |
| <span data-ttu-id="25f67-116">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="25f67-116">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="25f67-117">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="25f67-117">`0` - disabled</span></span><br/><span data-ttu-id="25f67-118">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="25f67-118">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="25f67-119">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="25f67-119">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="25f67-120">Определяет, использует ли <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> или более старые стеки протокола HTTP (<xref:System.Net.Http.WinHttpHandler> в Windows и `CurlHandler` — внутренний класс, реализованный на базе [libcurl](https://curl.haxx.se/libcurl/), в Linux).</span><span class="sxs-lookup"><span data-stu-id="25f67-120">Configures whether <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> uses <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or older HTTP protocol stacks (<xref:System.Net.Http.WinHttpHandler> on Windows and `CurlHandler`, an internal class implemented on top of [libcurl](https://curl.haxx.se/libcurl/), on Linux).</span></span>

  > [!NOTE]
  > <span data-ttu-id="25f67-121">Вместо непосредственного создания экземпляра класса <xref:System.Net.Http.HttpClientHandler> вы можете использовать высокоуровневые сетевые интерфейсы API.</span><span class="sxs-lookup"><span data-stu-id="25f67-121">You may be using high-level networking APIs instead of directly instantiating the <xref:System.Net.Http.HttpClientHandler> class.</span></span> <span data-ttu-id="25f67-122">Этот параметр также влияет на то, какой стек протокола HTTP используется высокоуровневыми сетевыми интерфейсами API, включая <xref:System.Net.Http.HttpClient> и [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118)).</span><span class="sxs-lookup"><span data-stu-id="25f67-122">This setting also affects which HTTP protocol stack is used by high-level networking APIs, including <xref:System.Net.Http.HttpClient> and [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118)).</span></span>

- <span data-ttu-id="25f67-123">Если этот параметр не задан, <xref:System.Net.Http.HttpClientHandler> будет использовать <xref:System.Net.Http.SocketsHttpHandler>.</span><span class="sxs-lookup"><span data-stu-id="25f67-123">If you omit this setting, <xref:System.Net.Http.HttpClientHandler> uses <xref:System.Net.Http.SocketsHttpHandler>.</span></span> <span data-ttu-id="25f67-124">Это эквивалентно присвоению значения `true`.</span><span class="sxs-lookup"><span data-stu-id="25f67-124">This is equivalent to setting the value to `true`.</span></span>

- <span data-ttu-id="25f67-125">Этот параметр можно настроить программно, вызвав метод <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="25f67-125">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="25f67-126">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="25f67-126">Setting name</span></span> | <span data-ttu-id="25f67-127">Значения</span><span class="sxs-lookup"><span data-stu-id="25f67-127">Values</span></span> |
| - | - | - |
| <span data-ttu-id="25f67-128">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="25f67-128">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="25f67-129">`true` — позволяет использовать <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="25f67-129">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="25f67-130">`false` — позволяет использовать <xref:System.Net.Http.WinHttpHandler> в Windows или [libcurl](https://curl.haxx.se/libcurl/) в Linux</span><span class="sxs-lookup"><span data-stu-id="25f67-130">`false` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |
| <span data-ttu-id="25f67-131">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="25f67-131">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="25f67-132">`1` — позволяет использовать <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="25f67-132">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="25f67-133">`0` — позволяет использовать <xref:System.Net.Http.WinHttpHandler> в Windows или [libcurl](https://curl.haxx.se/libcurl/) в Linux</span><span class="sxs-lookup"><span data-stu-id="25f67-133">`0` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |

> [!NOTE]
> <span data-ttu-id="25f67-134">Начиная с .NET 5 параметр `System.Net.Http.UseSocketsHttpHandler` больше недоступен.</span><span class="sxs-lookup"><span data-stu-id="25f67-134">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>

## <a name="latin1-headers-net-core-31-only"></a><span data-ttu-id="25f67-135">Заголовки Latin1 (только в .NET Core 3.1)</span><span class="sxs-lookup"><span data-stu-id="25f67-135">Latin1 headers (.NET Core 3.1 only)</span></span>

- <span data-ttu-id="25f67-136">Этот параметр позволяет сделать проверку заголовков HTTP менее строгой, благодаря чему <xref:System.Net.Http.SocketsHttpHandler> может передавать в заголовках символы в кодировке ISO-8859-1 (Latin-1).</span><span class="sxs-lookup"><span data-stu-id="25f67-136">This switch allows relaxing the HTTP header validation, enabling <xref:System.Net.Http.SocketsHttpHandler> to send ISO-8859-1 (Latin-1) encoded characters in headers.</span></span>

- <span data-ttu-id="25f67-137">Если этот параметр не задан, попытка отправки символа не в кодировке ASCII приведет к исключению <xref:System.Net.Http.HttpRequestException>.</span><span class="sxs-lookup"><span data-stu-id="25f67-137">If you omit this setting, an attempt to send a non-ASCII character will result in <xref:System.Net.Http.HttpRequestException>.</span></span> <span data-ttu-id="25f67-138">Это эквивалентно присвоению значения `false`.</span><span class="sxs-lookup"><span data-stu-id="25f67-138">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="25f67-139">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="25f67-139">Setting name</span></span> | <span data-ttu-id="25f67-140">Значения</span><span class="sxs-lookup"><span data-stu-id="25f67-140">Values</span></span> |
| - | - | - |
| <span data-ttu-id="25f67-141">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="25f67-141">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.AllowLatin1Headers` | <span data-ttu-id="25f67-142">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="25f67-142">`false` - disabled</span></span><br/><span data-ttu-id="25f67-143">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="25f67-143">`true` - enabled</span></span> |
| <span data-ttu-id="25f67-144">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="25f67-144">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_ALLOWLATIN1HEADERS` | <span data-ttu-id="25f67-145">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="25f67-145">`0` - disabled</span></span><br/><span data-ttu-id="25f67-146">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="25f67-146">`1` - enabled</span></span> |

> [!NOTE]
> <span data-ttu-id="25f67-147">Этот параметр доступен только в .NET Core 3.1, начиная с версии 3.1.9, но не в более ранних или поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="25f67-147">This option is only available in .NET Core 3.1 since version 3.1.9, and not in previous or later versions.</span></span> <span data-ttu-id="25f67-148">В .NET 5 рекомендуется использовать <xref:System.Net.Http.SocketsHttpHandler.RequestHeaderEncodingSelector>.</span><span class="sxs-lookup"><span data-stu-id="25f67-148">In .NET 5 we recommend using <xref:System.Net.Http.SocketsHttpHandler.RequestHeaderEncodingSelector>.</span></span>
