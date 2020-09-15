---
ms.openlocfilehash: 811b1a91169eeebfa056d9ecdb07d342d3b32d85
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615772"
---
### <a name="icontobitmap-successfully-converts-icons-with-png-frames-into-bitmap-objects"></a><span data-ttu-id="3ba8f-101">Icon.ToBitmap успешно преобразует значки с кадрами PNG в растровые изображения</span><span class="sxs-lookup"><span data-stu-id="3ba8f-101">Icon.ToBitmap successfully converts icons with PNG frames into Bitmap objects</span></span>

#### <a name="details"></a><span data-ttu-id="3ba8f-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="3ba8f-102">Details</span></span>

<span data-ttu-id="3ba8f-103">Начиная с приложений, предназначенных для .NET Framework 4.6, метод <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> успешно преобразует значки с кадрами PNG в объекты Bitmap.</span><span class="sxs-lookup"><span data-stu-id="3ba8f-103">Starting with the apps that target the .NET Framework 4.6, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method successfully converts icons with PNG frames into Bitmap objects.</span></span><p/><span data-ttu-id="3ba8f-104">В приложениях, предназначенных для .NET Framework 4.5.2 и более ранних версий, метод <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> создает исключение <xref:System.ArgumentOutOfRangeException>, если объект Icon содержит кадры PNG.</span><span class="sxs-lookup"><span data-stu-id="3ba8f-104">In apps that target the .NET Framework 4.5.2 and earlier versions, the  <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method throws an <xref:System.ArgumentOutOfRangeException> exception if the Icon object has PNG frames.</span></span><p/><span data-ttu-id="3ba8f-105">Это изменение затрагивает приложения, которые компилируются повторно для платформы .NET Framework 4.6 и в которых реализуется специальная обработка исключения <xref:System.ArgumentOutOfRangeException>, создаваемого при наличии кадров PNG в объекте Icon .</span><span class="sxs-lookup"><span data-stu-id="3ba8f-105">This change affects apps that are recompiled to target the .NET Framework 4.6 and that implement special handling for the <xref:System.ArgumentOutOfRangeException> that is thrown when an Icon object has PNG frames.</span></span> <span data-ttu-id="3ba8f-106">При выполнении в .NET Framework 4.6 преобразование проходит успешно, исключение <xref:System.ArgumentOutOfRangeException> больше не создается, и поэтому обработчик исключений больше не вызывается.</span><span class="sxs-lookup"><span data-stu-id="3ba8f-106">When running under the .NET Framework 4.6, the conversion is successful, an <xref:System.ArgumentOutOfRangeException> is no longer thrown, and therefore the exception handler is no longer invoked.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3ba8f-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="3ba8f-107">Suggestion</span></span>

<span data-ttu-id="3ba8f-108">Если такое поведение нежелательно, можно сохранить прежнее поведение, добавив в раздел `<runtime>` файла app.config следующий элемент:</span><span class="sxs-lookup"><span data-stu-id="3ba8f-108">If this behavior is undesirable, you can retain the previous behavior by adding the following element to the `<runtime>` section of your app.config file:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true&quot; /&gt;&#13;&#10;</code></pre>

<span data-ttu-id="3ba8f-109">Если файл app.config уже содержит элемент `AppContextSwitchOverrides`, новое значение следует объединить с атрибутом значения следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3ba8f-109">If the app.config file already contains the `AppContextSwitchOverrides` element, the new value should be merged with the value attribute like this:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true;&lt;previous key&gt;=&lt;previous value&gt;&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="3ba8f-110">name</span><span class="sxs-lookup"><span data-stu-id="3ba8f-110">Name</span></span>    | <span data-ttu-id="3ba8f-111">Значение</span><span class="sxs-lookup"><span data-stu-id="3ba8f-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3ba8f-112">Область</span><span class="sxs-lookup"><span data-stu-id="3ba8f-112">Scope</span></span>   | <span data-ttu-id="3ba8f-113">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="3ba8f-113">Minor</span></span>       |
| <span data-ttu-id="3ba8f-114">Version</span><span class="sxs-lookup"><span data-stu-id="3ba8f-114">Version</span></span> | <span data-ttu-id="3ba8f-115">4.6</span><span class="sxs-lookup"><span data-stu-id="3ba8f-115">4.6</span></span>         |
| <span data-ttu-id="3ba8f-116">Type</span><span class="sxs-lookup"><span data-stu-id="3ba8f-116">Type</span></span>    | <span data-ttu-id="3ba8f-117">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="3ba8f-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="3ba8f-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="3ba8f-118">Affected APIs</span></span>

- <xref:System.Drawing.Icon.ToBitmap?displayProperty=nameWithType>
