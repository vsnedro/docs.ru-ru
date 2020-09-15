---
ms.openlocfilehash: a44458484ea09c566defeabc9b604bd55d994e93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617548"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="f6476-101">Вызовы System.Windows.Input.PenContext.Disable в системах с поддержкой сенсорного ввода могут вызвать исключение ArgumentException</span><span class="sxs-lookup"><span data-stu-id="f6476-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

#### <a name="details"></a><span data-ttu-id="f6476-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="f6476-102">Details</span></span>

<span data-ttu-id="f6476-103">В некоторых случаях вызовы внутреннего метода **System.Windows.Intput.PenContext.Disable** в системах с поддержкой сенсорного ввода могут вызывать необработанное исключение `T:System.ArgumentException` из-за повторного входа.</span><span class="sxs-lookup"><span data-stu-id="f6476-103">Under some circumstances, calls to the internal **System.Windows.Intput.PenContext.Disable** method on touch-enabled systems may throw an unhandled `T:System.ArgumentException` because of reentrancy.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f6476-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="f6476-104">Suggestion</span></span>

<span data-ttu-id="f6476-105">Эта проблема была устранена в .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="f6476-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="f6476-106">Чтобы это исключение не возникало, выполните обновление до версии платформы .NET Framework 4.7 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="f6476-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>

| <span data-ttu-id="f6476-107">name</span><span class="sxs-lookup"><span data-stu-id="f6476-107">Name</span></span>    | <span data-ttu-id="f6476-108">Значение</span><span class="sxs-lookup"><span data-stu-id="f6476-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f6476-109">Область</span><span class="sxs-lookup"><span data-stu-id="f6476-109">Scope</span></span>   | <span data-ttu-id="f6476-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="f6476-110">Edge</span></span>        |
| <span data-ttu-id="f6476-111">Version</span><span class="sxs-lookup"><span data-stu-id="f6476-111">Version</span></span> | <span data-ttu-id="f6476-112">4.6.1</span><span class="sxs-lookup"><span data-stu-id="f6476-112">4.6.1</span></span>       |
| <span data-ttu-id="f6476-113">Type</span><span class="sxs-lookup"><span data-stu-id="f6476-113">Type</span></span>    | <span data-ttu-id="f6476-114">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="f6476-114">Retargeting</span></span> |
