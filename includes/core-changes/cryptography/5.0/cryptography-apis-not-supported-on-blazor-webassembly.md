---
ms.openlocfilehash: 6c2aff4abf558307d599ff7533c82286e037bc71
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406156"
---
### <a name="systemsecuritycryptography-apis-not-supported-on-blazor-webassembly"></a><span data-ttu-id="8db00-101">Blazor WebAssembly не поддерживает интерфейсы API System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="8db00-101">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>

<span data-ttu-id="8db00-102">API <xref:System.Security.Cryptography> выдают исключение <xref:System.PlatformNotSupportedException> при выполнении в браузере.</span><span class="sxs-lookup"><span data-stu-id="8db00-102"><xref:System.Security.Cryptography> APIs throw a <xref:System.PlatformNotSupportedException> at run time when run on a browser.</span></span>

#### <a name="change-description"></a><span data-ttu-id="8db00-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="8db00-103">Change description</span></span>

<span data-ttu-id="8db00-104">В предыдущих версиях .NET большинство API <xref:System.Security.Cryptography> были недоступны приложениям Blazor WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="8db00-104">In previous .NET versions, most of the <xref:System.Security.Cryptography> APIs aren't available to Blazor WebAssembly apps.</span></span> <span data-ttu-id="8db00-105">Начиная с .NET 5.0, приложения Blazor WebAssembly предназначены для использования в полной контактной зоне API .NET 5, но из-за ограничений песочницы браузера поддерживаются не все API .NET 5.</span><span class="sxs-lookup"><span data-stu-id="8db00-105">Starting in .NET 5.0, Blazor WebAssembly apps target the full .NET 5 API surface area, however, not all .NET 5 APIs are supported due to browser sandbox constraints.</span></span> <span data-ttu-id="8db00-106">В .NET 5.0 и более поздних версиях неподдерживаемые API <xref:System.Security.Cryptography> выдают исключение <xref:System.PlatformNotSupportedException> при выполнении в WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="8db00-106">In .NET 5.0 and later versions, the unsupported <xref:System.Security.Cryptography> APIs throw a <xref:System.PlatformNotSupportedException> when running on WebAssembly.</span></span>

> [!TIP]
> <span data-ttu-id="8db00-107">[Анализатор совместимости платформ](../../../../docs/core/compatibility/code-analysis.md#ca1416-platform-compatibility) помечает все вызовы затронутых API при сборке проекта, который поддерживает платформу браузера.</span><span class="sxs-lookup"><span data-stu-id="8db00-107">The [Platform compatibility analyzer](../../../../docs/core/compatibility/code-analysis.md#ca1416-platform-compatibility) will flag any calls to the affected APIs when you build a project that supports the browser platform.</span></span> <span data-ttu-id="8db00-108">Этот анализатор выполняется по умолчанию в приложениях .NET 5.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="8db00-108">This analyzer runs by default in .NET 5.0 and later apps.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="8db00-109">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="8db00-109">Reason for change</span></span>

<span data-ttu-id="8db00-110">Корпорация Майкрософт не может предоставить OpenSSL как зависимость в конфигурации Blazor WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="8db00-110">Microsoft is unable to ship OpenSSL as a dependency in the Blazor WebAssembly configuration.</span></span> <span data-ttu-id="8db00-111">Мы пытались решить эту проблему, выполнив интеграцию с API `SubtleCrypto` браузера.</span><span class="sxs-lookup"><span data-stu-id="8db00-111">We attempted to work around this by trying to integrate with the browser's `SubtleCrypto` API.</span></span> <span data-ttu-id="8db00-112">К сожалению, это требует кардинального изменения API, что усложняет интеграцию.</span><span class="sxs-lookup"><span data-stu-id="8db00-112">Unfortunately, it required significant API changes that made it too hard to integrate.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8db00-113">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="8db00-113">Version introduced</span></span>

<span data-ttu-id="8db00-114">5.0 (RC1)</span><span class="sxs-lookup"><span data-stu-id="8db00-114">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8db00-115">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="8db00-115">Recommended action</span></span>

<span data-ttu-id="8db00-116">В настоящее время мы не можем предложить решение.</span><span class="sxs-lookup"><span data-stu-id="8db00-116">There are no good workarounds to suggest at this time.</span></span>

#### <a name="category"></a><span data-ttu-id="8db00-117">Категория</span><span class="sxs-lookup"><span data-stu-id="8db00-117">Category</span></span>

- <span data-ttu-id="8db00-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8db00-118">ASP.NET Core</span></span>
- <span data-ttu-id="8db00-119">Шифрование</span><span class="sxs-lookup"><span data-stu-id="8db00-119">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8db00-120">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="8db00-120">Affected APIs</span></span>

<span data-ttu-id="8db00-121">Все API <xref:System.Security.Cryptography?displayProperty=fullName> за исключением следующих:</span><span class="sxs-lookup"><span data-stu-id="8db00-121">All <xref:System.Security.Cryptography?displayProperty=fullName> APIs except the following:</span></span>

- `System.Security.Cryptography.RandomNumberGenerator`
- `System.Security.Cryptography.IncrementalHash`
- `System.Security.Cryptography.SHA1`
- `System.Security.Cryptography.SHA256`
- `System.Security.Cryptography.SHA384`
- `System.Security.Cryptography.SHA512`
- `System.Security.Cryptography.SHA1Managed`
- `System.Security.Cryptography.SHA256Managed`
- `System.Security.Cryptography.SHA384Managed`
- `System.Security.Cryptography.SHA512Managed`

<!--

#### Affected APIs

- `T:System.Security.Cryptography`

-->
