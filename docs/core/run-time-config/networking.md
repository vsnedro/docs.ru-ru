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
# <a name="run-time-configuration-options-for-networking"></a>Параметры конфигурации времени выполнения для сети

## <a name="http2-protocol"></a>Протокол HTTP/2

- Указывает, включена ли поддержка протокола HTTP/2.

- Представлено в .NET Core 3.0.

- Только для .NET Core 3.0 Если этот параметр не задан, поддержка протокола HTTP/2 будет отключена. Это эквивалентно присвоению значения `false`.

- Для .NET Core 3.1 и .NET 5 и более поздних версий Если этот параметр не задан, поддержка протокола HTTP/2 будет включена. Это эквивалентно присвоению значения `true`.

| | Имя параметра | Значения |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.SocketsHttpHandler.Http2Support` | `false` — отключено<br/>`true` — включено |
| **Переменная среды** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | `0` — отключено<br/>`1` — включено |

## <a name="usesocketshttphandler"></a>UseSocketsHttpHandler

- Определяет, использует ли <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> или более старые стеки протокола HTTP (<xref:System.Net.Http.WinHttpHandler> в Windows и `CurlHandler` — внутренний класс, реализованный на базе [libcurl](https://curl.haxx.se/libcurl/), в Linux).

  > [!NOTE]
  > Вместо непосредственного создания экземпляра класса <xref:System.Net.Http.HttpClientHandler> вы можете использовать высокоуровневые сетевые интерфейсы API. Этот параметр также влияет на то, какой стек протокола HTTP используется высокоуровневыми сетевыми интерфейсами API, включая <xref:System.Net.Http.HttpClient> и [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118)).

- Если этот параметр не задан, <xref:System.Net.Http.HttpClientHandler> будет использовать <xref:System.Net.Http.SocketsHttpHandler>. Это эквивалентно присвоению значения `true`.

- Этот параметр можно настроить программно, вызвав метод <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.

| | Имя параметра | Значения |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.UseSocketsHttpHandler` | `true` — позволяет использовать <xref:System.Net.Http.SocketsHttpHandler><br/>`false` — позволяет использовать <xref:System.Net.Http.WinHttpHandler> в Windows или [libcurl](https://curl.haxx.se/libcurl/) в Linux |
| **Переменная среды** | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | `1` — позволяет использовать <xref:System.Net.Http.SocketsHttpHandler><br/>`0` — позволяет использовать <xref:System.Net.Http.WinHttpHandler> в Windows или [libcurl](https://curl.haxx.se/libcurl/) в Linux |

> [!NOTE]
> Начиная с .NET 5 параметр `System.Net.Http.UseSocketsHttpHandler` больше недоступен.

## <a name="latin1-headers-net-core-31-only"></a>Заголовки Latin1 (только в .NET Core 3.1)

- Этот параметр позволяет сделать проверку заголовков HTTP менее строгой, благодаря чему <xref:System.Net.Http.SocketsHttpHandler> может передавать в заголовках символы в кодировке ISO-8859-1 (Latin-1).

- Если этот параметр не задан, попытка отправки символа не в кодировке ASCII приведет к исключению <xref:System.Net.Http.HttpRequestException>. Это эквивалентно присвоению значения `false`.

| | Имя параметра | Значения |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.SocketsHttpHandler.AllowLatin1Headers` | `false` — отключено<br/>`true` — включено |
| **Переменная среды** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_ALLOWLATIN1HEADERS` | `0` — отключено<br/>`1` — включено |

> [!NOTE]
> Этот параметр доступен только в .NET Core 3.1, начиная с версии 3.1.9, но не в более ранних или поздних версиях. В .NET 5 рекомендуется использовать <xref:System.Net.Http.SocketsHttpHandler.RequestHeaderEncodingSelector>.
