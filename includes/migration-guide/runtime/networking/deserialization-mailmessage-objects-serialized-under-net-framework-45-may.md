---
ms.openlocfilehash: ad953a1562db407c04d7860c60eb5964fe6fe2ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620637"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a><span data-ttu-id="65474-101">Десериализация объектов MailMessage, сериализованных в .NET Framework 4.5, может завершиться сбоем</span><span class="sxs-lookup"><span data-stu-id="65474-101">Deserialization of MailMessage objects serialized under the .NET Framework 4.5 may fail</span></span>

#### <a name="details"></a><span data-ttu-id="65474-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="65474-102">Details</span></span>

<span data-ttu-id="65474-103">Начиная с версии .NET Framework 4.5, объекты <xref:System.Web.Mail.MailMessage> могут содержать символы, отличные от ASCII.</span><span class="sxs-lookup"><span data-stu-id="65474-103">Starting with the .NET Framework 4.5, <xref:System.Web.Mail.MailMessage> objects can include non-ASCII characters.</span></span> <span data-ttu-id="65474-104">В .NET Framework 4 поддерживаются только символы ASCII.</span><span class="sxs-lookup"><span data-stu-id="65474-104">In the .NET Framework 4, only ASCII characters are supported.</span></span> <span data-ttu-id="65474-105">В .NET Framework 4 не могут быть десериализованы объекты <xref:System.Web.Mail.MailMessage>, содержащие отличные от ASCII символы и сериализованные в .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="65474-105"><xref:System.Web.Mail.MailMessage> objects that contain non-ASCII characters and that are serialized under the .NET Framework 4.5 or later cannot be deserialized under the .NET Framework 4.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="65474-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="65474-106">Suggestion</span></span>

<span data-ttu-id="65474-107">Убедитесь, что в коде реализована обработка исключений при десериализации объекта <xref:System.Web.Mail.MailMessage>.</span><span class="sxs-lookup"><span data-stu-id="65474-107">Ensure that your code provides exception handling when deserializing a <xref:System.Web.Mail.MailMessage> object.</span></span>

| <span data-ttu-id="65474-108">name</span><span class="sxs-lookup"><span data-stu-id="65474-108">Name</span></span>    | <span data-ttu-id="65474-109">Значение</span><span class="sxs-lookup"><span data-stu-id="65474-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="65474-110">Область</span><span class="sxs-lookup"><span data-stu-id="65474-110">Scope</span></span>   |<span data-ttu-id="65474-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="65474-111">Minor</span></span>|
|<span data-ttu-id="65474-112">Version</span><span class="sxs-lookup"><span data-stu-id="65474-112">Version</span></span>|<span data-ttu-id="65474-113">4.5</span><span class="sxs-lookup"><span data-stu-id="65474-113">4.5</span></span>|
|<span data-ttu-id="65474-114">Type</span><span class="sxs-lookup"><span data-stu-id="65474-114">Type</span></span>|<span data-ttu-id="65474-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="65474-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="65474-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="65474-116">Affected APIs</span></span>

-<xref:System.Web.Mail.MailMessage?displayProperty=nameWithType></li></ul>|
