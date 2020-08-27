---
ms.openlocfilehash: 115cd6be935ae12a1293f948a0f899c6c3ff0d78
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608485"
---
### <a name="winhttphandler-removed-from-net-runtime"></a>Класс WinHttpHandler удален из среды выполнения .NET

Класс `WinHttpHandler` был удален из сборки *System.Net.Http.dll*. Теперь он доступен только как внештатный (OOB) [пакет NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).

#### <a name="version-introduced"></a>Представленная версия

5.0

#### <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET класс <xref:System.Net.Http.WinHttpHandler> доступен как часть основных библиотек .NET. Начиная с .NET 5.0 класс <xref:System.Net.Http.WinHttpHandler> доступен только как отдельно устанавливаемый [пакет NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).

#### <a name="recommended-action"></a>Рекомендованное действие

Установите пакет NuGet [System.Net.Http.WinHttpHandler](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/). Или, если не требуются специфические для WinHTTP функции, используйте вместо этого <xref:System.Net.Http.SocketsHttpHandler>.

#### <a name="category"></a>Категория

Сети

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Net.Http.WinHttpHandler?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Http.WinHttpHandler`

-->
