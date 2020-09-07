---
ms.openlocfilehash: 99a7fa0fcfce6d490a182f85709b5dd0e0e8c86f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497533"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a><span data-ttu-id="f1a08-101">Реализация EventSource.WriteEvent должна передавать WriteEvent те же параметры, которые она получила (плюс идентификатор)</span><span class="sxs-lookup"><span data-stu-id="f1a08-101">EventSource.WriteEvent impls must pass WriteEvent the same parameters that it received (plus ID)</span></span>

#### <a name="details"></a><span data-ttu-id="f1a08-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="f1a08-102">Details</span></span>

<span data-ttu-id="f1a08-103">В среде выполнения теперь реализуется контракт, определяющий следующее: класс, производный от <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> и определяющий метод событий ETW, должен вызвать метод <code>EventSource.WriteEvent</code> базового класса с идентификатором события и теми же аргументами, с которыми был передан метод событий ETW.</span><span class="sxs-lookup"><span data-stu-id="f1a08-103">The runtime now enforces the contract that specifies the following: A class derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> that defines an ETW event method must call the base class <code>EventSource.WriteEvent</code> method with the event ID followed by the same arguments that the ETW event method was passed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f1a08-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="f1a08-104">Suggestion</span></span>

<span data-ttu-id="f1a08-105">Возникает исключение <xref:System.IndexOutOfRangeException?displayProperty=fullName>, если объект <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> считывает данные <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> в процессе для источника события, нарушающего контракт.</span><span class="sxs-lookup"><span data-stu-id="f1a08-105">An <xref:System.IndexOutOfRangeException?displayProperty=fullName> exception is thrown if an <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> reads <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process for an event source that violates this contract.</span></span>

| <span data-ttu-id="f1a08-106">name</span><span class="sxs-lookup"><span data-stu-id="f1a08-106">Name</span></span>    | <span data-ttu-id="f1a08-107">Значение</span><span class="sxs-lookup"><span data-stu-id="f1a08-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f1a08-108">Область</span><span class="sxs-lookup"><span data-stu-id="f1a08-108">Scope</span></span>   |<span data-ttu-id="f1a08-109">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="f1a08-109">Minor</span></span>|
|<span data-ttu-id="f1a08-110">Version</span><span class="sxs-lookup"><span data-stu-id="f1a08-110">Version</span></span>|<span data-ttu-id="f1a08-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="f1a08-111">4.5.1</span></span>|
|<span data-ttu-id="f1a08-112">Type</span><span class="sxs-lookup"><span data-stu-id="f1a08-112">Type</span></span>|<span data-ttu-id="f1a08-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="f1a08-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f1a08-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="f1a08-114">Affected APIs</span></span>

<span data-ttu-id="f1a08-115">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="f1a08-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
