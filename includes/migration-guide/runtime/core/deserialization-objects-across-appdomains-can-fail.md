---
ms.openlocfilehash: 5c949b79eefa68ea6f8d4ad27c716c438e24f170
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620559"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a><span data-ttu-id="c8f8a-101">Десериализация объектов между доменами приложений может завершиться сбоем</span><span class="sxs-lookup"><span data-stu-id="c8f8a-101">Deserialization of objects across appdomains can fail</span></span>

#### <a name="details"></a><span data-ttu-id="c8f8a-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="c8f8a-102">Details</span></span>

<span data-ttu-id="c8f8a-103">В некоторых случаях, когда приложение использует два или большее количество доменов с разными базовыми папками приложения, при попытке выполнить десериализацию объектов в логическом контексте вызова между доменами приложения возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="c8f8a-103">In some cases, when an app uses two or more app domains with different application bases, trying to deserialize objects in the logical call context across app domains throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c8f8a-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="c8f8a-104">Suggestion</span></span>

<span data-ttu-id="c8f8a-105">См. статью [Устранение рисков: десериализация объектов между доменами приложений](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span><span class="sxs-lookup"><span data-stu-id="c8f8a-105">See [Mitigation: Deserialization of Objects Across App Domains](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span></span>

| <span data-ttu-id="c8f8a-106">name</span><span class="sxs-lookup"><span data-stu-id="c8f8a-106">Name</span></span>    | <span data-ttu-id="c8f8a-107">Значение</span><span class="sxs-lookup"><span data-stu-id="c8f8a-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c8f8a-108">Область</span><span class="sxs-lookup"><span data-stu-id="c8f8a-108">Scope</span></span>   |<span data-ttu-id="c8f8a-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="c8f8a-109">Edge</span></span>|
|<span data-ttu-id="c8f8a-110">Version</span><span class="sxs-lookup"><span data-stu-id="c8f8a-110">Version</span></span>|<span data-ttu-id="c8f8a-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="c8f8a-111">4.5.1</span></span>|
|<span data-ttu-id="c8f8a-112">Type</span><span class="sxs-lookup"><span data-stu-id="c8f8a-112">Type</span></span>|<span data-ttu-id="c8f8a-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="c8f8a-113">Runtime</span></span>|
