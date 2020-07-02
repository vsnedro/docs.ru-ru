---
ms.openlocfilehash: af10716fe5f4c07091e8605cdf620e4a499fb1e8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620183"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a><span data-ttu-id="a9484-101">Не следует использовать iPad в файле пользовательских возможностей, так как теперь это функция браузера</span><span class="sxs-lookup"><span data-stu-id="a9484-101">IPad should not be used in custom capabilities file because it is now a browser capability</span></span>

#### <a name="details"></a><span data-ttu-id="a9484-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="a9484-102">Details</span></span>

<span data-ttu-id="a9484-103">Начиная с версии .NET Framework 4.5 iPad является идентификатором в файле возможностей браузера ASP.NET по умолчанию, поэтому его не следует использовать в файле пользовательских возможностей</span><span class="sxs-lookup"><span data-stu-id="a9484-103">Beginning in .NET Framework 4.5, iPad is an identifier in the default ASP.NET browser capabilities file, so it should not be used in a custom capabilities file</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a9484-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="a9484-104">Suggestion</span></span>

<span data-ttu-id="a9484-105">Если требуются определенные возможности iPad, необходимо изменить поведение iPad, настроив возможности на предварительно определенном шлюзе refID &quot;IPad&quot; или создав новый идентификатор &quot;IPad&quot; путем сопоставления агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="a9484-105">If iPad-specific capabilities are required, it is necessary to modify iPad behavior by setting capabilities on the pre-defined gateway refID &quot;IPad&quot; instead of by generating a new &quot;IPad&quot; ID by user agent matching.</span></span>

| <span data-ttu-id="a9484-106">name</span><span class="sxs-lookup"><span data-stu-id="a9484-106">Name</span></span>    | <span data-ttu-id="a9484-107">Значение</span><span class="sxs-lookup"><span data-stu-id="a9484-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a9484-108">Область</span><span class="sxs-lookup"><span data-stu-id="a9484-108">Scope</span></span>   |<span data-ttu-id="a9484-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="a9484-109">Edge</span></span>|
|<span data-ttu-id="a9484-110">Version</span><span class="sxs-lookup"><span data-stu-id="a9484-110">Version</span></span>|<span data-ttu-id="a9484-111">4.5</span><span class="sxs-lookup"><span data-stu-id="a9484-111">4.5</span></span>|
|<span data-ttu-id="a9484-112">Type</span><span class="sxs-lookup"><span data-stu-id="a9484-112">Type</span></span>|<span data-ttu-id="a9484-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="a9484-113">Runtime</span></span>|
