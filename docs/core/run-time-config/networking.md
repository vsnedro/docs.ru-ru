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
# <a name="run-time-configuration-options-for-networking"></a>Параметры конфигурации времени выполнения для сети

## <a name="http2-protocol"></a>Протокол HTTP/2

- Указывает, включена ли поддержка протокола HTTP/2.

- Если этот параметр не задан, поддержка протокола HTTP/2 будет отключена. Это эквивалентно присвоению значения `false`.

- Представлено в .NET Core 3.0.

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
