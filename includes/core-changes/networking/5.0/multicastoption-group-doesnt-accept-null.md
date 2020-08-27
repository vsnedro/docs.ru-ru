---
ms.openlocfilehash: 88a0b7e04c7015ca3fa5abd8a6897dafcbe41c49
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557973"
---
### <a name="multicastoptiongroup-doesnt-accept-a-null-value"></a><span data-ttu-id="339a8-101">MulticastOption.Group не принимает значение null</span><span class="sxs-lookup"><span data-stu-id="339a8-101">MulticastOption.Group doesn't accept a null value</span></span>

<span data-ttu-id="339a8-102"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> больше не принимает значение `null`.</span><span class="sxs-lookup"><span data-stu-id="339a8-102"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> no longer accepts a value of `null`.</span></span> <span data-ttu-id="339a8-103">Если задать для свойства значение `null`, вызывается исключение <xref:System.ArgumentNullException>.</span><span class="sxs-lookup"><span data-stu-id="339a8-103">If you set the property to `null`, an <xref:System.ArgumentNullException> is thrown.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="339a8-104">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="339a8-104">Version introduced</span></span>

<span data-ttu-id="339a8-105">5.0</span><span class="sxs-lookup"><span data-stu-id="339a8-105">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="339a8-106">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="339a8-106">Change description</span></span>

<span data-ttu-id="339a8-107">В предыдущих версиях .NET для свойства <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> можно было задать значение `null`.</span><span class="sxs-lookup"><span data-stu-id="339a8-107">In previous versions of .NET, you can set the <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> property to `null`.</span></span> <span data-ttu-id="339a8-108">Если впоследствии <xref:System.Net.Sockets.MulticastOption> передается в <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>, среда выполнения вызывает исключение <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="339a8-108">If the <xref:System.Net.Sockets.MulticastOption> is later passed to <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>, the runtime throws a <xref:System.NullReferenceException>.</span></span>

<span data-ttu-id="339a8-109">В .NET 5.0 и более поздних версиях исключение <xref:System.ArgumentNullException> вызывается, если для этого свойства задано значение `null`.</span><span class="sxs-lookup"><span data-stu-id="339a8-109">In .NET 5.0 and later, an <xref:System.ArgumentNullException> is thrown if you set the property to `null`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="339a8-110">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="339a8-110">Reason for change</span></span>

<span data-ttu-id="339a8-111">Для соответствия рекомендациям по проектированию платформы свойство было обновлено для создания исключения <xref:System.ArgumentNullException>, если значение равно `null`.</span><span class="sxs-lookup"><span data-stu-id="339a8-111">To be consistent with the Framework Design Guidelines, the property has been updated to throw an <xref:System.ArgumentNullException> if the value is `null`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="339a8-112">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="339a8-112">Recommended action</span></span>

<span data-ttu-id="339a8-113">Убедитесь, что для <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> не задается значение `null`.</span><span class="sxs-lookup"><span data-stu-id="339a8-113">Make sure that you don't set <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> to `null`.</span></span>

#### <a name="category"></a><span data-ttu-id="339a8-114">Категория</span><span class="sxs-lookup"><span data-stu-id="339a8-114">Category</span></span>

<span data-ttu-id="339a8-115">Сети</span><span class="sxs-lookup"><span data-stu-id="339a8-115">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="339a8-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="339a8-116">Affected APIs</span></span>

- <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Net.Sockets.MulticastOption.Group`

-->
