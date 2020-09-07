---
ms.openlocfilehash: f50022d9a7bacd7be40fe3050ced26e7c25cf7aa
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497783"
---
### <a name="crash-in-selector-when-removing-an-item-from-a-custom-incc-collection"></a><span data-ttu-id="299bb-101">Сбой в селекторе при удалении элемента из пользовательской коллекции INCC</span><span class="sxs-lookup"><span data-stu-id="299bb-101">Crash in Selector when removing an item from a custom INCC collection</span></span>

#### <a name="details"></a><span data-ttu-id="299bb-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="299bb-102">Details</span></span>

<span data-ttu-id="299bb-103"><code>T:System.InvalidOperationException</code> может возникнуть в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="299bb-103">An <code>T:System.InvalidOperationException</code> can occur in the following scenario:</span></span><ul><li><span data-ttu-id="299bb-104">ItemsSource для <code>T:System.Windows.Controls.Primitives.Selector</code> является коллекцией с пользовательской реализацией <code>T:System.Collections.Specialized.INotifyCollectionChanged</code>.</span><span class="sxs-lookup"><span data-stu-id="299bb-104">The ItemsSource for a <code>T:System.Windows.Controls.Primitives.Selector</code> is a collection with a custom implementation of <code>T:System.Collections.Specialized.INotifyCollectionChanged</code>.</span></span></li><li><span data-ttu-id="299bb-105">Выбранный элемент удаляется из коллекции.</span><span class="sxs-lookup"><span data-stu-id="299bb-105">The selected item is removed from the collection.</span></span></li><li><span data-ttu-id="299bb-106">Для <code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code> установлено <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code> = –1 (что указывает на неизвестную позицию).</span><span class="sxs-lookup"><span data-stu-id="299bb-106">The <code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code> has <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code> = -1 (indicating an unknown position).</span></span></li></ul><span data-ttu-id="299bb-107">Стек вызова исключения начинается в System.Windows.Threading.Dispatcher.VerifyAccess() в System.Windows.DependencyObject.GetValue(DependencyProperty dp) в System.Windows.Controls.Primitives.Selector.GetIsSelected(DependencyObject element). Это исключение может возникнуть в .Net Framework 4.5, если у приложения несколько потоков Dispatcher.</span><span class="sxs-lookup"><span data-stu-id="299bb-107">The exception's callstack begins at System.Windows.Threading.Dispatcher.VerifyAccess() at System.Windows.DependencyObject.GetValue(DependencyProperty dp) at System.Windows.Controls.Primitives.Selector.GetIsSelected(DependencyObject element)This exception can occur in .NET Framework 4.5 if the application has more than one Dispatcher thread.</span></span> <span data-ttu-id="299bb-108">В .Net Framework 4.7 исключение также может возникнуть в приложениях с одним потоком Dispatcher.</span><span class="sxs-lookup"><span data-stu-id="299bb-108">In .NET Framework 4.7 the exception can also occur in applications with a single Dispatcher thread.</span></span> <span data-ttu-id="299bb-109">Проблема устранена в .Net Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="299bb-109">The issue is fixed in .NET Framework 4.7.1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="299bb-110">Предложение</span><span class="sxs-lookup"><span data-stu-id="299bb-110">Suggestion</span></span>

<span data-ttu-id="299bb-111">Выполните обновление до .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="299bb-111">Upgrade to .NET Framework 4.7.1.</span></span>

| <span data-ttu-id="299bb-112">Имя</span><span class="sxs-lookup"><span data-stu-id="299bb-112">Name</span></span>    | <span data-ttu-id="299bb-113">Значение</span><span class="sxs-lookup"><span data-stu-id="299bb-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="299bb-114">Область</span><span class="sxs-lookup"><span data-stu-id="299bb-114">Scope</span></span>   |<span data-ttu-id="299bb-115">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="299bb-115">Minor</span></span>|
|<span data-ttu-id="299bb-116">Version</span><span class="sxs-lookup"><span data-stu-id="299bb-116">Version</span></span>|<span data-ttu-id="299bb-117">4.7</span><span class="sxs-lookup"><span data-stu-id="299bb-117">4.7</span></span>|
|<span data-ttu-id="299bb-118">Type</span><span class="sxs-lookup"><span data-stu-id="299bb-118">Type</span></span>|<span data-ttu-id="299bb-119">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="299bb-119">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="299bb-120">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="299bb-120">Affected APIs</span></span>

<span data-ttu-id="299bb-121">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="299bb-121">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
