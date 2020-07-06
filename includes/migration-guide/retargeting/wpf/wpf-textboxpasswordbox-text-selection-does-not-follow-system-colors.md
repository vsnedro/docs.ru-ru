---
ms.openlocfilehash: 7c2e80669d9ef27f87cde9442d8eeab0ee31a524
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614979"
---
### <a name="wpf-textboxpasswordbox-text-selection-does-not-follow-system-colors"></a><span data-ttu-id="85956-101">Выделенный текст в текстовом поле или поле пароля WPF не соответствуют системным цветам</span><span class="sxs-lookup"><span data-stu-id="85956-101">WPF TextBox/PasswordBox Text Selection Does Not Follow System Colors</span></span>

#### <a name="details"></a><span data-ttu-id="85956-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="85956-102">Details</span></span>

<span data-ttu-id="85956-103">В .NET Framework 4.7.1 и более ранних версий `System.Windows.Controls.TextBox` и `System.Windows.Controls.PasswordBox` WPF могли отображать выделенный текст только в слое декоративных элементов.</span><span class="sxs-lookup"><span data-stu-id="85956-103">In .NET Framework 4.7.1 and earlier versions, WPF `System.Windows.Controls.TextBox` and `System.Windows.Controls.PasswordBox` could only render a text selection in the Adorner layer.</span></span> <span data-ttu-id="85956-104">В некоторых системных темах это приводило к скрытию текста, что делало его трудно читаемым.</span><span class="sxs-lookup"><span data-stu-id="85956-104">In some system themes this would occlude text, making it hard to read.</span></span>  <span data-ttu-id="85956-105">В .NET Framework 4.7.2 и более поздних версий разработчики имеют возможность включить механизм отрисовки выбранных участков не на основе декоративных элементов, что устраняет эту проблему.</span><span class="sxs-lookup"><span data-stu-id="85956-105">In .NET Framework 4.7.2 and later, developers have an option of enabling a non-Adorner-based selection rendering scheme that alleviates this issue.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="85956-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="85956-106">Suggestion</span></span>

<span data-ttu-id="85956-107">Разработчикам, желающим использовать это изменение, необходимо задать следующий флаг AppContext соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="85956-107">A developer who wants to utilize this change must set the following AppContext flag appropriately.</span></span>  <span data-ttu-id="85956-108">Чтобы использовать эту функцию, должна быть установлена версия .NET Framework 4.7.2 или более поздняя. Для включения выбора не на основе декоративных элементов используйте следующий флаг AppContext.</span><span class="sxs-lookup"><span data-stu-id="85956-108">To utilize this feature, the installed .NET Framework version must be 4.7.2 or greater.To enabled the non-adorner-based selection, use the following AppContext flag.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Text.UseAdornerForTextboxSelectionRendering=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="85956-109">name</span><span class="sxs-lookup"><span data-stu-id="85956-109">Name</span></span>    | <span data-ttu-id="85956-110">Значение</span><span class="sxs-lookup"><span data-stu-id="85956-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="85956-111">Область</span><span class="sxs-lookup"><span data-stu-id="85956-111">Scope</span></span>   | <span data-ttu-id="85956-112">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="85956-112">Edge</span></span>        |
| <span data-ttu-id="85956-113">Version</span><span class="sxs-lookup"><span data-stu-id="85956-113">Version</span></span> | <span data-ttu-id="85956-114">4.7.2</span><span class="sxs-lookup"><span data-stu-id="85956-114">4.7.2</span></span>       |
| <span data-ttu-id="85956-115">Type</span><span class="sxs-lookup"><span data-stu-id="85956-115">Type</span></span>    | <span data-ttu-id="85956-116">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="85956-116">Retargeting</span></span> |
