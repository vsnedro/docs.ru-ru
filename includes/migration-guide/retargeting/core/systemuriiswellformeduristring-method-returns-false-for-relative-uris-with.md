---
ms.openlocfilehash: f7dcf9c4c3dc7ea536ddc847769a1a30f1298bb2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617283"
---
### <a name="systemuriiswellformeduristring-method-returns-false-for-relative-uris-with-a-colon-char-in-first-segment"></a><span data-ttu-id="2e391-101">Метод System.Uri.IsWellFormedUriString возвращает значение false для относительных URI с символом двоеточия в первом сегменте</span><span class="sxs-lookup"><span data-stu-id="2e391-101">System.Uri.IsWellFormedUriString method returns false for relative URIs with a colon char in first segment</span></span>

#### <a name="details"></a><span data-ttu-id="2e391-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="2e391-102">Details</span></span>

<span data-ttu-id="2e391-103">Начиная с .NET Framework 4.5 <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> будет рассматривать относительные URI с `:` в первом сегменте как некорректные.</span><span class="sxs-lookup"><span data-stu-id="2e391-103">Beginning with the .NET Framework 4.5, <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> will treat relative URIs with a `:` in their first segment as not well formed.</span></span> <span data-ttu-id="2e391-104">Это отличается от поведения <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> в .NET Framework 4.0. Изменение было внесено, чтобы обеспечить соответствие RFC3986.</span><span class="sxs-lookup"><span data-stu-id="2e391-104">This is a change from <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> behavior in the .NET Framework 4.0 that was made to conform to RFC3986.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2e391-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="2e391-105">Suggestion</span></span>

<span data-ttu-id="2e391-106">Это изменение (как и другие изменения URI) повлияет только на приложения, предназначенные для .NET Framework 4.5 (или более поздней версии).</span><span class="sxs-lookup"><span data-stu-id="2e391-106">This change (like many other URI changes) will only affect applications targeting the .NET Framework 4.5 (or later).</span></span> <span data-ttu-id="2e391-107">Чтобы сохранить старое поведение, необходимо нацелить приложение на .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="2e391-107">To keep using the old behavior, target the app against the .NET Framework 4.0.</span></span> <span data-ttu-id="2e391-108">Кроме того, проверьте URI до вызова метода <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName>, ищущего символы `:`, которые можно удалить в целях проверки, если вы предпочитаете старое поведение.</span><span class="sxs-lookup"><span data-stu-id="2e391-108">Alternatively, scan URI's prior to calling <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> looking for `:` characters that you may want to remove for validation purposes, if the old behavior is desirable.</span></span>

| <span data-ttu-id="2e391-109">name</span><span class="sxs-lookup"><span data-stu-id="2e391-109">Name</span></span>    | <span data-ttu-id="2e391-110">Значение</span><span class="sxs-lookup"><span data-stu-id="2e391-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2e391-111">Область</span><span class="sxs-lookup"><span data-stu-id="2e391-111">Scope</span></span>   | <span data-ttu-id="2e391-112">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="2e391-112">Minor</span></span>       |
| <span data-ttu-id="2e391-113">Version</span><span class="sxs-lookup"><span data-stu-id="2e391-113">Version</span></span> | <span data-ttu-id="2e391-114">4.5</span><span class="sxs-lookup"><span data-stu-id="2e391-114">4.5</span></span>         |
| <span data-ttu-id="2e391-115">Type</span><span class="sxs-lookup"><span data-stu-id="2e391-115">Type</span></span>    | <span data-ttu-id="2e391-116">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="2e391-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="2e391-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="2e391-117">Affected APIs</span></span>

- <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=nameWithType>
