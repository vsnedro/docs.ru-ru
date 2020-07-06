---
ms.openlocfilehash: 349854b0dec5a585990b9c5e7c0b575df5bf70f3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615778"
---
### <a name="xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a><span data-ttu-id="0c7df-101">Проверка схемы XSD теперь правильно обнаруживает нарушения уникальных ограничений, если используются составные ключи и один ключ пуст</span><span class="sxs-lookup"><span data-stu-id="0c7df-101">XSD Schema validation now correctly detects violations of unique constraints if compound keys are used and one key is empty</span></span>

#### <a name="details"></a><span data-ttu-id="0c7df-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="0c7df-102">Details</span></span>

<span data-ttu-id="0c7df-103">В версиях платформы .NET Framework, предшествовавших версии 4.6, была ошибка, из-за которой проверка XSD не могла обнаруживать уникальные ограничения по составным ключам, если один из ключей был пуст.</span><span class="sxs-lookup"><span data-stu-id="0c7df-103">Versions of the .NET Framework prior to 4.6 had a bug that caused XSD validation to not detect unique constraints on compound keys if one of the keys was empty.</span></span> <span data-ttu-id="0c7df-104">Эта проблема решена в .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="0c7df-104">In the .NET Framework 4.6, this issue is corrected.</span></span> <span data-ttu-id="0c7df-105">Это приведет к выполнению более правильной проверки, но также может привести к невозможности проверки некоторого XML-кода, которая осуществлялась раньше.</span><span class="sxs-lookup"><span data-stu-id="0c7df-105">This will result in more correct validation, but it may also result in some XML not validating which previously would have.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0c7df-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="0c7df-106">Suggestion</span></span>

<span data-ttu-id="0c7df-107">Если требуется менее строгая проверка .NET Framework 4.0, проверяющее приложение может быть предназначено для версии 4.5 (или более ранней) платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0c7df-107">If looser .NET Framework 4.0 validation is needed, the validating application can target version 4.5 (or earlier) of the .NET Framework.</span></span> <span data-ttu-id="0c7df-108">Однако при изменении целевой платформы на .NET Framework 4.6 следует выполнить проверку кода, чтобы не проверять повторяющиеся составные ключи (как указано в описании этой проблемы).</span><span class="sxs-lookup"><span data-stu-id="0c7df-108">When retargeting to .NET Framework 4.6, however, code review should be done to be sure that duplicate compound keys (as described in this issue's description) are not expected to validate.</span></span>

| <span data-ttu-id="0c7df-109">name</span><span class="sxs-lookup"><span data-stu-id="0c7df-109">Name</span></span>    | <span data-ttu-id="0c7df-110">Значение</span><span class="sxs-lookup"><span data-stu-id="0c7df-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0c7df-111">Область</span><span class="sxs-lookup"><span data-stu-id="0c7df-111">Scope</span></span>   | <span data-ttu-id="0c7df-112">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="0c7df-112">Edge</span></span>        |
| <span data-ttu-id="0c7df-113">Version</span><span class="sxs-lookup"><span data-stu-id="0c7df-113">Version</span></span> | <span data-ttu-id="0c7df-114">4.6</span><span class="sxs-lookup"><span data-stu-id="0c7df-114">4.6</span></span>         |
| <span data-ttu-id="0c7df-115">Type</span><span class="sxs-lookup"><span data-stu-id="0c7df-115">Type</span></span>    | <span data-ttu-id="0c7df-116">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="0c7df-116">Retargeting</span></span> |
