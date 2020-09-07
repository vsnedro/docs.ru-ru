---
ms.openlocfilehash: 3f82a4daac3b5d8981532f0c82e9a76f13c68b6e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497625"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a><span data-ttu-id="f555d-101">Десериализация объектов между доменами приложений может завершиться сбоем</span><span class="sxs-lookup"><span data-stu-id="f555d-101">Deserialization of objects across appdomains can fail</span></span>

#### <a name="details"></a><span data-ttu-id="f555d-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="f555d-102">Details</span></span>

<span data-ttu-id="f555d-103">В некоторых случаях, когда приложение использует два или большее количество доменов с разными базовыми папками приложения, при попытке выполнить десериализацию объектов в логическом контексте вызова между доменами приложения возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="f555d-103">In some cases, when an app uses two or more app domains with different application bases, trying to deserialize objects in the logical call context across app domains throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f555d-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="f555d-104">Suggestion</span></span>

<span data-ttu-id="f555d-105">См. статью [Устранение рисков: десериализация объектов между доменами приложений](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span><span class="sxs-lookup"><span data-stu-id="f555d-105">See [Mitigation: Deserialization of Objects Across App Domains](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span></span>

| <span data-ttu-id="f555d-106">name</span><span class="sxs-lookup"><span data-stu-id="f555d-106">Name</span></span>    | <span data-ttu-id="f555d-107">Значение</span><span class="sxs-lookup"><span data-stu-id="f555d-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f555d-108">Область</span><span class="sxs-lookup"><span data-stu-id="f555d-108">Scope</span></span>   |<span data-ttu-id="f555d-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="f555d-109">Edge</span></span>|
|<span data-ttu-id="f555d-110">Version</span><span class="sxs-lookup"><span data-stu-id="f555d-110">Version</span></span>|<span data-ttu-id="f555d-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="f555d-111">4.5.1</span></span>|
|<span data-ttu-id="f555d-112">Type</span><span class="sxs-lookup"><span data-stu-id="f555d-112">Type</span></span>|<span data-ttu-id="f555d-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="f555d-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f555d-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="f555d-114">Affected APIs</span></span>

<span data-ttu-id="f555d-115">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="f555d-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
