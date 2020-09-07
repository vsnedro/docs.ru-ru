---
ms.openlocfilehash: 2c44c2e1658f8de556d3f7222de3fa6d4594163a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496337"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a><span data-ttu-id="b9d98-101">Десериализация объектов MailMessage, сериализованных в .NET Framework 4.5, может завершиться сбоем</span><span class="sxs-lookup"><span data-stu-id="b9d98-101">Deserialization of MailMessage objects serialized under the .NET Framework 4.5 may fail</span></span>

#### <a name="details"></a><span data-ttu-id="b9d98-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="b9d98-102">Details</span></span>

<span data-ttu-id="b9d98-103">Начиная с версии .NET Framework 4.5, объекты <xref:System.Web.Mail.MailMessage> могут содержать символы, отличные от ASCII.</span><span class="sxs-lookup"><span data-stu-id="b9d98-103">Starting with the .NET Framework 4.5, <xref:System.Web.Mail.MailMessage> objects can include non-ASCII characters.</span></span> <span data-ttu-id="b9d98-104">В .NET Framework 4 поддерживаются только символы ASCII.</span><span class="sxs-lookup"><span data-stu-id="b9d98-104">In the .NET Framework 4, only ASCII characters are supported.</span></span> <span data-ttu-id="b9d98-105">В .NET Framework 4 не могут быть десериализованы объекты <xref:System.Web.Mail.MailMessage>, содержащие отличные от ASCII символы и сериализованные в .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="b9d98-105"><xref:System.Web.Mail.MailMessage> objects that contain non-ASCII characters and that are serialized under the .NET Framework 4.5 or later cannot be deserialized under the .NET Framework 4.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b9d98-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="b9d98-106">Suggestion</span></span>

<span data-ttu-id="b9d98-107">Убедитесь, что в коде реализована обработка исключений при десериализации объекта <xref:System.Web.Mail.MailMessage>.</span><span class="sxs-lookup"><span data-stu-id="b9d98-107">Ensure that your code provides exception handling when deserializing a <xref:System.Web.Mail.MailMessage> object.</span></span>

| <span data-ttu-id="b9d98-108">name</span><span class="sxs-lookup"><span data-stu-id="b9d98-108">Name</span></span>    | <span data-ttu-id="b9d98-109">Значение</span><span class="sxs-lookup"><span data-stu-id="b9d98-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b9d98-110">Область</span><span class="sxs-lookup"><span data-stu-id="b9d98-110">Scope</span></span>   |<span data-ttu-id="b9d98-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="b9d98-111">Minor</span></span>|
|<span data-ttu-id="b9d98-112">Version</span><span class="sxs-lookup"><span data-stu-id="b9d98-112">Version</span></span>|<span data-ttu-id="b9d98-113">4.5</span><span class="sxs-lookup"><span data-stu-id="b9d98-113">4.5</span></span>|
|<span data-ttu-id="b9d98-114">Type</span><span class="sxs-lookup"><span data-stu-id="b9d98-114">Type</span></span>|<span data-ttu-id="b9d98-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="b9d98-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="b9d98-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="b9d98-116">Affected APIs</span></span>

- <xref:System.Web.Mail.MailMessage?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Web.Mail.MailMessage`

-->
