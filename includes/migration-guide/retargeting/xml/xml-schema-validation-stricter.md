---
ms.openlocfilehash: 4a22d78f2308aab544d7a7d2e4d05ddc1ad5457d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617299"
---
### <a name="xml-schema-validation-is-stricter"></a><span data-ttu-id="85bfb-101">Более строгая проверка схемы XML</span><span class="sxs-lookup"><span data-stu-id="85bfb-101">XML schema validation is stricter</span></span>

#### <a name="details"></a><span data-ttu-id="85bfb-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="85bfb-102">Details</span></span>

<span data-ttu-id="85bfb-103">В .NET Framework 4.5 проверка схемы XML является более строгой.</span><span class="sxs-lookup"><span data-stu-id="85bfb-103">In the .NET Framework 4.5, XML schema validation is more strict.</span></span> <span data-ttu-id="85bfb-104">При использовании xsd:anyURI для проверки URI, такого как протокол MailTo, при наличии пробелов в URI возникает сбой проверки.</span><span class="sxs-lookup"><span data-stu-id="85bfb-104">If you use xsd:anyURI to validate a URI such as a mailto protocol, validation fails if there are spaces in the URI.</span></span> <span data-ttu-id="85bfb-105">В предыдущих версиях .NET Framework проверка проходила успешно.</span><span class="sxs-lookup"><span data-stu-id="85bfb-105">In previous versions of the .NET Framework, validation succeeded.</span></span> <span data-ttu-id="85bfb-106">Изменение затрагивает только приложения, предназначенные для .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="85bfb-106">The change affects only applications that target the .NET Framework 4.5.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="85bfb-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="85bfb-107">Suggestion</span></span>

<span data-ttu-id="85bfb-108">Если требуется менее строгая проверка .NET Framework 4.0, проверяющее приложение может быть ориентировано на версию 4.0 (или более раннюю) платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="85bfb-108">If looser .NET Framework 4.0 validation is needed, the validating application can target version 4.0 of the .NET Framework.</span></span> <span data-ttu-id="85bfb-109">При изменении целевой платформы на .NET Framework 4.5 необходимо выполнить проверку кода и убедиться, что недопустимые URI (с пробелами) не ожидаются в качестве значений атрибута с типом данных anyURI.</span><span class="sxs-lookup"><span data-stu-id="85bfb-109">When retargeting to .NET Framework 4.5, however, code review should be done to be sure that invalid URIs (with spaces) are not expected as attribute values with the anyURI data type.</span></span>

| <span data-ttu-id="85bfb-110">name</span><span class="sxs-lookup"><span data-stu-id="85bfb-110">Name</span></span>    | <span data-ttu-id="85bfb-111">Значение</span><span class="sxs-lookup"><span data-stu-id="85bfb-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="85bfb-112">Область</span><span class="sxs-lookup"><span data-stu-id="85bfb-112">Scope</span></span>   | <span data-ttu-id="85bfb-113">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="85bfb-113">Minor</span></span>       |
| <span data-ttu-id="85bfb-114">Version</span><span class="sxs-lookup"><span data-stu-id="85bfb-114">Version</span></span> | <span data-ttu-id="85bfb-115">4.5</span><span class="sxs-lookup"><span data-stu-id="85bfb-115">4.5</span></span>         |
| <span data-ttu-id="85bfb-116">Type</span><span class="sxs-lookup"><span data-stu-id="85bfb-116">Type</span></span>    | <span data-ttu-id="85bfb-117">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="85bfb-117">Retargeting</span></span> |
