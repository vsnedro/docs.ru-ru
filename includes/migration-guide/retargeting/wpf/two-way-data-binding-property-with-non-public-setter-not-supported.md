---
ms.openlocfilehash: 5f1a8af37a305ab0904801002dd99e17e8eca62e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616126"
---
### <a name="two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a><span data-ttu-id="d07c9-101">Двусторонняя привязка данных к свойству с не предназначенным для общего доступа методом задания не поддерживается</span><span class="sxs-lookup"><span data-stu-id="d07c9-101">Two-way data-binding to a property with a non-public setter is not supported</span></span>

#### <a name="details"></a><span data-ttu-id="d07c9-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="d07c9-102">Details</span></span>

<span data-ttu-id="d07c9-103">Попытка привязки данных к свойству без общедоступного метода задания никогда не поддерживалась.</span><span class="sxs-lookup"><span data-stu-id="d07c9-103">Attempting to data bind to a property without a public setter has never been a supported scenario.</span></span> <span data-ttu-id="d07c9-104">Начиная с .NET Framework 4.5.1 этот сценарий выдает исключение <xref:System.InvalidOperationException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="d07c9-104">Beginning in the .NET Framework 4.5.1, this scenario will throw an <xref:System.InvalidOperationException?displayProperty=fullName>.</span></span> <span data-ttu-id="d07c9-105">Обратите внимание, что это новое исключение создается только для приложений, которые предназначены специально для .NET Framework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="d07c9-105">Note that this new exception will only be thrown for apps that specifically target the .NET Framework 4.5.1.</span></span> <span data-ttu-id="d07c9-106">Если приложение предназначено для .NET Framework 4.5, вызов будет разрешен.</span><span class="sxs-lookup"><span data-stu-id="d07c9-106">If an app targets the .NET Framework 4.5, the call will be allowed.</span></span> <span data-ttu-id="d07c9-107">Если приложение не предназначено для определенной версии .NET Framework, привязка будет рассматриваться как односторонняя.</span><span class="sxs-lookup"><span data-stu-id="d07c9-107">If the app does not target a particular .NET Framework version, the binding will be treated as one-way.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d07c9-108">Предложение</span><span class="sxs-lookup"><span data-stu-id="d07c9-108">Suggestion</span></span>

<span data-ttu-id="d07c9-109">Приложение следует обновить либо для использования односторонней привязки, либо для предоставления общего доступа к методу задания свойства.</span><span class="sxs-lookup"><span data-stu-id="d07c9-109">The app should be updated to either use one-way binding, or expose the property's setter publicly.</span></span> <span data-ttu-id="d07c9-110">Кроме того, выбор .NET Framework 4.5 в качестве целевой платформы приведет к восстановлению старого поведения приложения.</span><span class="sxs-lookup"><span data-stu-id="d07c9-110">Alternatively, targeting the .NET Framework 4.5 will cause the app to exhibit the old behavior.</span></span>

| <span data-ttu-id="d07c9-111">name</span><span class="sxs-lookup"><span data-stu-id="d07c9-111">Name</span></span>    | <span data-ttu-id="d07c9-112">Значение</span><span class="sxs-lookup"><span data-stu-id="d07c9-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d07c9-113">Область</span><span class="sxs-lookup"><span data-stu-id="d07c9-113">Scope</span></span>   | <span data-ttu-id="d07c9-114">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="d07c9-114">Minor</span></span>       |
| <span data-ttu-id="d07c9-115">Version</span><span class="sxs-lookup"><span data-stu-id="d07c9-115">Version</span></span> | <span data-ttu-id="d07c9-116">4.5.1</span><span class="sxs-lookup"><span data-stu-id="d07c9-116">4.5.1</span></span>       |
| <span data-ttu-id="d07c9-117">Type</span><span class="sxs-lookup"><span data-stu-id="d07c9-117">Type</span></span>    | <span data-ttu-id="d07c9-118">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="d07c9-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d07c9-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="d07c9-119">Affected APIs</span></span>

- <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType>
