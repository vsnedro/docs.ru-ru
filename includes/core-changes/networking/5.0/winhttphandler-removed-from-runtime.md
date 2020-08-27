---
ms.openlocfilehash: 115cd6be935ae12a1293f948a0f899c6c3ff0d78
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608485"
---
### <a name="winhttphandler-removed-from-net-runtime"></a><span data-ttu-id="9c65a-101">Класс WinHttpHandler удален из среды выполнения .NET</span><span class="sxs-lookup"><span data-stu-id="9c65a-101">WinHttpHandler removed from .NET runtime</span></span>

<span data-ttu-id="9c65a-102">Класс `WinHttpHandler` был удален из сборки *System.Net.Http.dll*.</span><span class="sxs-lookup"><span data-stu-id="9c65a-102">The `WinHttpHandler` class was removed from the *System.Net.Http.dll* assembly.</span></span> <span data-ttu-id="9c65a-103">Теперь он доступен только как внештатный (OOB) [пакет NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span><span class="sxs-lookup"><span data-stu-id="9c65a-103">It's now available only as an out-of-band (OOB) [NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9c65a-104">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="9c65a-104">Version introduced</span></span>

<span data-ttu-id="9c65a-105">5.0</span><span class="sxs-lookup"><span data-stu-id="9c65a-105">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="9c65a-106">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="9c65a-106">Change description</span></span>

<span data-ttu-id="9c65a-107">В предыдущих версиях .NET класс <xref:System.Net.Http.WinHttpHandler> доступен как часть основных библиотек .NET.</span><span class="sxs-lookup"><span data-stu-id="9c65a-107">In previous .NET versions, the <xref:System.Net.Http.WinHttpHandler> class is available as part of the core .NET libraries.</span></span> <span data-ttu-id="9c65a-108">Начиная с .NET 5.0 класс <xref:System.Net.Http.WinHttpHandler> доступен только как отдельно устанавливаемый [пакет NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span><span class="sxs-lookup"><span data-stu-id="9c65a-108">Starting in .NET 5.0, the <xref:System.Net.Http.WinHttpHandler> class is only available as a separately installed [NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9c65a-109">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="9c65a-109">Recommended action</span></span>

<span data-ttu-id="9c65a-110">Установите пакет NuGet [System.Net.Http.WinHttpHandler](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span><span class="sxs-lookup"><span data-stu-id="9c65a-110">Install the [System.Net.Http.WinHttpHandler NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span> <span data-ttu-id="9c65a-111">Или, если не требуются специфические для WinHTTP функции, используйте вместо этого <xref:System.Net.Http.SocketsHttpHandler>.</span><span class="sxs-lookup"><span data-stu-id="9c65a-111">Or, if you don't require WinHTTP-specific features, use <xref:System.Net.Http.SocketsHttpHandler> instead.</span></span>

#### <a name="category"></a><span data-ttu-id="9c65a-112">Категория</span><span class="sxs-lookup"><span data-stu-id="9c65a-112">Category</span></span>

<span data-ttu-id="9c65a-113">Сети</span><span class="sxs-lookup"><span data-stu-id="9c65a-113">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9c65a-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="9c65a-114">Affected APIs</span></span>

- <xref:System.Net.Http.WinHttpHandler?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Http.WinHttpHandler`

-->
