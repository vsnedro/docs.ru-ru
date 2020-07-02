---
ms.openlocfilehash: c103dff320ae30d02c12ea5c585a47b589da8237
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621421"
---
### <a name="contentdisposition-datetimes-returns-slightly-different-string"></a><span data-ttu-id="820cf-101">ContentDisposition DateTime возвращает немного другую строку</span><span class="sxs-lookup"><span data-stu-id="820cf-101">ContentDisposition DateTimes returns slightly different string</span></span>

#### <a name="details"></a><span data-ttu-id="820cf-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="820cf-102">Details</span></span>

<span data-ttu-id="820cf-103">Строковые представления <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName> были обновлены, начиная с версии 4.6, чтобы всегда представлять компонент часа <xref:System.DateTime?displayProperty=fullName> с использованием двух цифр.</span><span class="sxs-lookup"><span data-stu-id="820cf-103">String representations of <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName>'s have been updated, beginning in 4.6, to always represent the hour component of a <xref:System.DateTime?displayProperty=fullName> with two digits.</span></span> <span data-ttu-id="820cf-104">Это сделано в соответствии с [RFC822](https://www.ietf.org/rfc/rfc0822.txt) и [RFC2822](https://www.ietf.org/rfc/rfc2822.txt).</span><span class="sxs-lookup"><span data-stu-id="820cf-104">This is to comply with [RFC822](https://www.ietf.org/rfc/rfc0822.txt) and [RFC2822](https://www.ietf.org/rfc/rfc2822.txt).</span></span> <span data-ttu-id="820cf-105">В результате <xref:System.Net.Mime.ContentDisposition.ToString> возвращает немного другую строку в 4.6 в сценариях, где один из элементов времени расположения имел значение, предшествующее 10:00.</span><span class="sxs-lookup"><span data-stu-id="820cf-105">This causes <xref:System.Net.Mime.ContentDisposition.ToString> to return a slightly different string in 4.6 in scenarios where one of the disposition's time elements was before 10:00 AM.</span></span> <span data-ttu-id="820cf-106">Обратите внимание, что ContentDispositions иногда сериализуются посредством преобразования в строки, поэтому следует проверить все операции <xref:System.Net.Mime.ContentDisposition.ToString>, сериализации или вызовы GetHashCode.</span><span class="sxs-lookup"><span data-stu-id="820cf-106">Note that ContentDispositions are sometimes serialized via converting them to strings, so any <xref:System.Net.Mime.ContentDisposition.ToString> operations, serialization, or GetHashCode calls should be reviewed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="820cf-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="820cf-107">Suggestion</span></span>

<span data-ttu-id="820cf-108">Не ожидается, что строковые представления ContentDispositions из разных версий .NET Framework будут правильно сравниваться друг с другом.</span><span class="sxs-lookup"><span data-stu-id="820cf-108">Do not expect that string representations of ContentDispositions from different .NET Framework versions will correctly compare to one another.</span></span> <span data-ttu-id="820cf-109">Если возможно, перед сравнением преобразуйте строки обратно в ContentDispositions.</span><span class="sxs-lookup"><span data-stu-id="820cf-109">Convert the strings back to ContentDispositions, if possible, before conducting a comparison.</span></span>

| <span data-ttu-id="820cf-110">name</span><span class="sxs-lookup"><span data-stu-id="820cf-110">Name</span></span>    | <span data-ttu-id="820cf-111">Значение</span><span class="sxs-lookup"><span data-stu-id="820cf-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="820cf-112">Область</span><span class="sxs-lookup"><span data-stu-id="820cf-112">Scope</span></span>   |<span data-ttu-id="820cf-113">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="820cf-113">Minor</span></span>|
|<span data-ttu-id="820cf-114">Version</span><span class="sxs-lookup"><span data-stu-id="820cf-114">Version</span></span>|<span data-ttu-id="820cf-115">4.6</span><span class="sxs-lookup"><span data-stu-id="820cf-115">4.6</span></span>|
|<span data-ttu-id="820cf-116">Type</span><span class="sxs-lookup"><span data-stu-id="820cf-116">Type</span></span>|<span data-ttu-id="820cf-117">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="820cf-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="820cf-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="820cf-118">Affected APIs</span></span>

-<xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=nameWithType></li><li><xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=nameWithType></li></ul>|
