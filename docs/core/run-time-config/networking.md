---
title: Параметры конфигурации сети
description: Сведения о параметрах времени выполнения, определяющих использование сети для приложений .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: f5ea47f0444a911dc2347a66817cabf585fd8e70
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635428"
---
# <a name="run-time-configuration-options-for-networking"></a>Параметры конфигурации времени выполнения для сети

## <a name="http2-protocol"></a>Протокол HTTP/2

- Указывает, включена ли поддержка протокола HTTP/2.
- По умолчанию: отключено (`false`).
- Представлено в .NET Core 3.0.

| | Имя параметра | Значения |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.SocketsHttpHandler.Http2Support` | `false` — отключено<br/>`true` — включено |
| **Переменная среды** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | `0` — отключено<br/>`1` — включено |

## <a name="usesocketshttphandler"></a>UseSocketsHttpHandler

- Указывает, используют ли высокоуровневые API сети, такие как <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> или реализацию <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> на основе [libcurl](https://curl.haxx.se/libcurl/).
- По умолчанию: используется <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`).
- Этот параметр можно настроить программно, вызвав метод <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.

| | Имя параметра | Значения |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.UseSocketsHttpHandler` | `true` — позволяет использовать <xref:System.Net.Http.SocketsHttpHandler><br/>`false` — позволяет использовать <xref:System.Net.Http.HttpClientHandler> |
| **Переменная среды** | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | `1` — позволяет использовать <xref:System.Net.Http.SocketsHttpHandler><br/>`0` — позволяет использовать <xref:System.Net.Http.HttpClientHandler> |

> [!NOTE]
> Начиная с .NET 5 параметр `System.Net.Http.UseSocketsHttpHandler` больше недоступен.
