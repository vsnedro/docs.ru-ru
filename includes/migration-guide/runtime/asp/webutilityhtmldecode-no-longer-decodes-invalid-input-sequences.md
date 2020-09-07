---
ms.openlocfilehash: ef3114a4eb9f62030c3ec36d3b463d07ccd59f6d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496219"
---
### <a name="webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a><span data-ttu-id="a386a-101">Метод WebUtility.HtmlDecode больше не декодирует недопустимую входную последовательность</span><span class="sxs-lookup"><span data-stu-id="a386a-101">WebUtility.HtmlDecode no longer decodes invalid input sequences</span></span>

#### <a name="details"></a><span data-ttu-id="a386a-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="a386a-102">Details</span></span>

<span data-ttu-id="a386a-103">По умолчанию методы декодирования больше не декодируют недопустимую входную последовательность в недопустимую строку UTF-16.</span><span class="sxs-lookup"><span data-stu-id="a386a-103">By default, decoding methods no longer decode an invalid input sequence into an invalid UTF-16 string.</span></span> <span data-ttu-id="a386a-104">Вместо этого они возвращают исходные входные данные.</span><span class="sxs-lookup"><span data-stu-id="a386a-104">Instead, they return the original input.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a386a-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="a386a-105">Suggestion</span></span>

<span data-ttu-id="a386a-106">Изменение в выходных данных декодера может иметь значение, только если в строках хранятся двоичные данные, а не данные UTF-16.</span><span class="sxs-lookup"><span data-stu-id="a386a-106">The change in decoder output should matter only if you store binary data instead of UTF-16 data in strings.</span></span> <span data-ttu-id="a386a-107">Чтобы явно контролировать это поведение, присвойте атрибуту <code>aspnet:AllowRelaxedUnicodeDecoding</code> элемента [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) значение <code>true</code>, чтобы разрешить устаревшее поведение, или значение <code>false</code>, чтобы разрешить текущее поведение.</span><span class="sxs-lookup"><span data-stu-id="a386a-107">To explicitly control this behavior, set the <code>aspnet:AllowRelaxedUnicodeDecoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) element to <code>true</code> to enable legacy behavior or to <code>false</code> to enable the current behavior.</span></span>

| <span data-ttu-id="a386a-108">name</span><span class="sxs-lookup"><span data-stu-id="a386a-108">Name</span></span>    | <span data-ttu-id="a386a-109">Значение</span><span class="sxs-lookup"><span data-stu-id="a386a-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a386a-110">Область</span><span class="sxs-lookup"><span data-stu-id="a386a-110">Scope</span></span>   |<span data-ttu-id="a386a-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="a386a-111">Minor</span></span>|
|<span data-ttu-id="a386a-112">Version</span><span class="sxs-lookup"><span data-stu-id="a386a-112">Version</span></span>|<span data-ttu-id="a386a-113">4.5</span><span class="sxs-lookup"><span data-stu-id="a386a-113">4.5</span></span>|
|<span data-ttu-id="a386a-114">Type</span><span class="sxs-lookup"><span data-stu-id="a386a-114">Type</span></span>|<span data-ttu-id="a386a-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="a386a-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a386a-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="a386a-116">Affected APIs</span></span>

- <xref:System.Net.WebUtility.HtmlDecode(System.String)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.UrlDecode(System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Net.WebUtility.HtmlDecode(System.String)`
- `M:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)`
- `M:System.Net.WebUtility.UrlDecode(System.String)`

-->
