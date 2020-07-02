---
ms.openlocfilehash: a007022bf32ffe76861f6f9016a7edace17b0f61
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620643"
---
### <a name="data-written-to-printsystemjobinfojobstream-must-be-in-xps-format"></a><span data-ttu-id="5825e-101">Данные, записанные в PrintSystemJobInfo.JobStream, должны иметь формат XPS</span><span class="sxs-lookup"><span data-stu-id="5825e-101">Data written to PrintSystemJobInfo.JobStream must be in XPS format</span></span>

#### <a name="details"></a><span data-ttu-id="5825e-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="5825e-102">Details</span></span>

<span data-ttu-id="5825e-103">Свойство <xref:System.Printing.PrintSystemJobInfo.JobStream> предоставляет поток задания печати.</span><span class="sxs-lookup"><span data-stu-id="5825e-103">The <xref:System.Printing.PrintSystemJobInfo.JobStream> property exposes the stream of a print job.</span></span> <span data-ttu-id="5825e-104">Пользователь может отправить необработанные данные в компоненты печати базовой операционной системы путем записи в этот поток. Начиная с .NET Framework 4.5 в Windows 8 и более поздних версиях операционной системы Windows данные, которые записываются в этот поток, должны быть в формате XPS, как поток пакета.</span><span class="sxs-lookup"><span data-stu-id="5825e-104">The user can send raw data to the underlying operating system printing components by writing to this stream.Starting with the .NET Framework 4.5 on Windows 8 and later versions of the Windows operating system, data written to this stream must be in XPS format as a package stream.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5825e-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="5825e-105">Suggestion</span></span>

<span data-ttu-id="5825e-106">Для вывода содержимого печати выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="5825e-106">To output print content, you can do either of the following:</span></span><ul><li><span data-ttu-id="5825e-107">Используйте класс <xref:System.Windows.Xps.XpsDocumentWriter> класса для вывода содержимого печати.</span><span class="sxs-lookup"><span data-stu-id="5825e-107">Use the <xref:System.Windows.Xps.XpsDocumentWriter> class to output print content.</span></span> <span data-ttu-id="5825e-108">Это рекомендуемый вариант.</span><span class="sxs-lookup"><span data-stu-id="5825e-108">This is the recommended alternative.</span></span></li><li><span data-ttu-id="5825e-109">Убедитесь, что данные, отправляемые в поток, возвращенный свойством <xref:System.Printing.PrintSystemJobInfo.JobStream>, находятся в формате XPS, как поток пакета.</span><span class="sxs-lookup"><span data-stu-id="5825e-109">Ensure that the data sent to the stream returned by the <xref:System.Printing.PrintSystemJobInfo.JobStream> property is in XPS format as a package stream.</span></span></li></ul>

| <span data-ttu-id="5825e-110">name</span><span class="sxs-lookup"><span data-stu-id="5825e-110">Name</span></span>    | <span data-ttu-id="5825e-111">Значение</span><span class="sxs-lookup"><span data-stu-id="5825e-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5825e-112">Область</span><span class="sxs-lookup"><span data-stu-id="5825e-112">Scope</span></span>   |<span data-ttu-id="5825e-113">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="5825e-113">Minor</span></span>|
|<span data-ttu-id="5825e-114">Version</span><span class="sxs-lookup"><span data-stu-id="5825e-114">Version</span></span>|<span data-ttu-id="5825e-115">4.5</span><span class="sxs-lookup"><span data-stu-id="5825e-115">4.5</span></span>|
|<span data-ttu-id="5825e-116">Type</span><span class="sxs-lookup"><span data-stu-id="5825e-116">Type</span></span>|<span data-ttu-id="5825e-117">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="5825e-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5825e-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="5825e-118">Affected APIs</span></span>

-<xref:System.Printing.PrintSystemJobInfo.JobStream?displayProperty=nameWithType></li></ul>|
