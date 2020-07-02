---
ms.openlocfilehash: 3aafb14b65f7c0f9e5d77927809547f9d4b96e1c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620654"
---
### <a name="error-codes-for-maxrequestlength-or-maxreceivedmessagesize-are-different"></a><span data-ttu-id="d6799-101">Коды ошибок для maxRequestLength или maxReceivedMessageSize различаются</span><span class="sxs-lookup"><span data-stu-id="d6799-101">Error codes for maxRequestLength or maxReceivedMessageSize are different</span></span>

#### <a name="details"></a><span data-ttu-id="d6799-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="d6799-102">Details</span></span>

<span data-ttu-id="d6799-103">Если длина сообщений в веб-службах WCF, размещенных в службах IIS или на сервере ASP.NET Development Server, превышает maxRequestLength (в ASP.NET) или maxReceivedMessageSize (в WCF), им присваиваются разные коды ошибок. Код состояния HTTP изменился с 400 (неверный запрос) на 413 (слишком большая сущность запроса), а для сообщений, длина которых превышает maxRequestLength или maxReceivedMessageSize, теперь создается исключение <xref:System.ServiceModel.ProtocolException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="d6799-103">Messages in WCF web services hosted in Internet Information Services (IIS) or ASP.NET Development Server that exceed maxRequestLength (in ASP.NET) or maxReceivedMessageSize (in WCF) have different error codeThe HTTP status code has changed from 400 (Bad Request) to 413 (Request Entity Too Large), and messages that exceed either the maxRequestLength or the maxReceivedMessageSize setting throw a <xref:System.ServiceModel.ProtocolException?displayProperty=fullName> exception.</span></span> <span data-ttu-id="d6799-104">Сюда входят случаи, в которых режимом передачи является Streamed.</span><span class="sxs-lookup"><span data-stu-id="d6799-104">This includes cases in which the transfer mode is Streamed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d6799-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="d6799-105">Suggestion</span></span>

<span data-ttu-id="d6799-106">Это изменение облегчает отладку в тех случаях, когда длина сообщения превышает ограничения, установленные ASP.NET или WCF. Необходимо внести изменения во весь код, который выполняет обработку на основании кода состояния HTTP 400.</span><span class="sxs-lookup"><span data-stu-id="d6799-106">This change facilitates debugging in cases where the message length exceeds the limits allowed by ASP.NET or WCF.You must modify any code that performs processing based on an HTTP 400 status code.</span></span>

| <span data-ttu-id="d6799-107">name</span><span class="sxs-lookup"><span data-stu-id="d6799-107">Name</span></span>    | <span data-ttu-id="d6799-108">Значение</span><span class="sxs-lookup"><span data-stu-id="d6799-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d6799-109">Область</span><span class="sxs-lookup"><span data-stu-id="d6799-109">Scope</span></span>   |<span data-ttu-id="d6799-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="d6799-110">Edge</span></span>|
|<span data-ttu-id="d6799-111">Version</span><span class="sxs-lookup"><span data-stu-id="d6799-111">Version</span></span>|<span data-ttu-id="d6799-112">4.5</span><span class="sxs-lookup"><span data-stu-id="d6799-112">4.5</span></span>|
|<span data-ttu-id="d6799-113">Type</span><span class="sxs-lookup"><span data-stu-id="d6799-113">Type</span></span>|<span data-ttu-id="d6799-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="d6799-114">Runtime</span></span>|
