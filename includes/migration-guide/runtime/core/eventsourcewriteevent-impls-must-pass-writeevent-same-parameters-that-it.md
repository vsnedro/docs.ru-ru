---
ms.openlocfilehash: 662c140f019add66ff6605d47ad1f32c3f50d711
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620576"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a><span data-ttu-id="25b70-101">Реализация EventSource.WriteEvent должна передавать WriteEvent те же параметры, которые она получила (плюс идентификатор)</span><span class="sxs-lookup"><span data-stu-id="25b70-101">EventSource.WriteEvent impls must pass WriteEvent the same parameters that it received (plus ID)</span></span>

#### <a name="details"></a><span data-ttu-id="25b70-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="25b70-102">Details</span></span>

<span data-ttu-id="25b70-103">В среде выполнения теперь реализуется контракт, определяющий следующее: класс, производный от <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> и определяющий метод событий ETW, должен вызвать метод <code>EventSource.WriteEvent</code> базового класса с идентификатором события и теми же аргументами, с которыми был передан метод событий ETW.</span><span class="sxs-lookup"><span data-stu-id="25b70-103">The runtime now enforces the contract that specifies the following: A class derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> that defines an ETW event method must call the base class <code>EventSource.WriteEvent</code> method with the event ID followed by the same arguments that the ETW event method was passed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="25b70-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="25b70-104">Suggestion</span></span>

<span data-ttu-id="25b70-105">Возникает исключение <xref:System.IndexOutOfRangeException?displayProperty=fullName>, если объект <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> считывает данные <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> в процессе для источника события, нарушающего контракт.</span><span class="sxs-lookup"><span data-stu-id="25b70-105">An <xref:System.IndexOutOfRangeException?displayProperty=fullName> exception is thrown if an <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> reads <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process for an event source that violates this contract.</span></span>

| <span data-ttu-id="25b70-106">name</span><span class="sxs-lookup"><span data-stu-id="25b70-106">Name</span></span>    | <span data-ttu-id="25b70-107">Значение</span><span class="sxs-lookup"><span data-stu-id="25b70-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="25b70-108">Область</span><span class="sxs-lookup"><span data-stu-id="25b70-108">Scope</span></span>   |<span data-ttu-id="25b70-109">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="25b70-109">Minor</span></span>|
|<span data-ttu-id="25b70-110">Version</span><span class="sxs-lookup"><span data-stu-id="25b70-110">Version</span></span>|<span data-ttu-id="25b70-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="25b70-111">4.5.1</span></span>|
|<span data-ttu-id="25b70-112">Type</span><span class="sxs-lookup"><span data-stu-id="25b70-112">Type</span></span>|<span data-ttu-id="25b70-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="25b70-113">Runtime</span></span>|
