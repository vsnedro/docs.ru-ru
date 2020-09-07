---
ms.openlocfilehash: c1793bb51f7da9169e912078fde202d0d62a4183
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497268"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="0dbf9-101">Свойству EnableViewStateMac больше невозможно задавать значение false</span><span class="sxs-lookup"><span data-stu-id="0dbf9-101">No longer able to set EnableViewStateMac to false</span></span>

#### <a name="details"></a><span data-ttu-id="0dbf9-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="0dbf9-102">Details</span></span>

<span data-ttu-id="0dbf9-103">ASP.NET теперь не позволяет разработчикам указывать <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> или <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span><span class="sxs-lookup"><span data-stu-id="0dbf9-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="0dbf9-104">Код проверки подлинности сообщения (MAC) состояния просмотра теперь принудительно применяется для всех запросов со встроенным состоянием просмотра.</span><span class="sxs-lookup"><span data-stu-id="0dbf9-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="0dbf9-105">Затрагиваются только те приложения, в которых для свойства EnableViewStateMac явно задано значение <code>false</code>.</span><span class="sxs-lookup"><span data-stu-id="0dbf9-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0dbf9-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="0dbf9-106">Suggestion</span></span>

<span data-ttu-id="0dbf9-107">Следует считать, что свойство EnableViewStateMac имеет значение true, и возникающие ошибки MAC должны быть устранены (как описано в [этом](https://support.microsoft.com/kb/2915218) руководстве, содержащем несколько решений в зависимости от причины ошибки MAC).</span><span class="sxs-lookup"><span data-stu-id="0dbf9-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>

| <span data-ttu-id="0dbf9-108">name</span><span class="sxs-lookup"><span data-stu-id="0dbf9-108">Name</span></span>    | <span data-ttu-id="0dbf9-109">Значение</span><span class="sxs-lookup"><span data-stu-id="0dbf9-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0dbf9-110">Область</span><span class="sxs-lookup"><span data-stu-id="0dbf9-110">Scope</span></span>   |<span data-ttu-id="0dbf9-111">Значительно</span><span class="sxs-lookup"><span data-stu-id="0dbf9-111">Major</span></span>|
|<span data-ttu-id="0dbf9-112">Version</span><span class="sxs-lookup"><span data-stu-id="0dbf9-112">Version</span></span>|<span data-ttu-id="0dbf9-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="0dbf9-113">4.5.2</span></span>|
|<span data-ttu-id="0dbf9-114">Type</span><span class="sxs-lookup"><span data-stu-id="0dbf9-114">Type</span></span>|<span data-ttu-id="0dbf9-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="0dbf9-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0dbf9-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="0dbf9-116">Affected APIs</span></span>

<span data-ttu-id="0dbf9-117">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="0dbf9-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
